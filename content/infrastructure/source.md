---
title: Source Code
---

# Source Code

Our goal is to provide the best possible Mastodon experience for our members.
One way to deliver on that is by delivering the most up-to-date Mastodon code.
We "run off main", which means using the latest commits to the `main` branch of the Mastodon codebase found on the project's official [GitHub](https://github.com/mastodon/mastodon) repository.

We take a clean copy of the latest Mastodon code and then apply a limited set of modification with a custom script.
We then build the modified code inside a Docker container, publish it to GitHub Container Registry, for consumption by our Kubernetes cluster.

Our server specific customizations include:

- Customizing the Mastodon logo, if needed, for events like Pride Month ([SVG](https://cdn.vmst.io/docs/masto-pride.zip))
- Raising the post character count limit from 500 to 640
- Removing the Hiredis driver in favor of the native Redis driver
- Adding the [Elephant](/clients/elephant) and [Tangerine](/clients/tangerine) themes ([vmstan/mastodon #6](https://github.com/vmstan/mastodon/pull/6))

Individual container builds may include additional changes which are being tested on vmst.io, and may be sourced from PR's in the [project repository](https://github.com/mastodon/mastodon) or in [other development repos](https://github.com/mastodon/vmstan).

## Container Availability

### Primary Image

Our customized container image is available from both Docker and GitHub container registries. This is suitable for the web/Puma and Sidekiq services.

- [GitHub](https://github.com/users/vmstan/packages/container/package/mastodon)

### Streaming Image

Mastodon 4.3-based images and beyond use a seperate container image for the Streaming API.

- [GitHub](https://github.com/users/vmstan/packages/container/package/mastodon-streaming)

## Redis TLS Changes

DigitalOcean requires encrypted/TLS connections to their managed Redis services, however the Mastodon codebase uses a Redis driver ([hiredis](https://github.com/redis/hiredis-rb)) which does not have a native TLS capability.
To accommodate this, we have in the past used [HAProxy](https://www.haproxy.org) or [Stunnel](https://www.stunnel.org) to take the un-encrypted connection requests and encrypt those connections between the Mastodon components and Redis.

We have chosen to remove the hiredis driver from our installation and use redis-rb instead.
Using the native redis-rb driver provides support for TLS connections.
This is done by patching a stock Mastodon installation with the following commands, downloading updated bundles and node components, and recompiling:

```bash
sed -i '/gem '\''hiredis'\'', '\''~> 0.6'\''/d' ./Gemfile
sed -i '/hiredis/d' ./Gemfile.lock
sed -i '/hiredis/d' ./lib/mastodon/redis_config.rb
sed -i '/hiredis/d' ./lib/tasks/mastodon.rake
sed -i 's/, driver: :hiredis//g' ./app/lib/redis_configuration.rb
sed -i 's/, require: \['\''redis'\'', '\''redis\/connection\/hiredis'\''\]//' ./Gemfile
```

Compared to running with hiredis through HAProxy or Stunnel, we have not seen any negative impact in performance by using redis-rb.

## Character Limit Change

Mastodon does not have an individual environment variable that allows this to be easily changed, but as of version 4.3 can be done by changing the hard-coded limit in `app/validators/status_length_validator.rb`

```bash
sed -i '' 's/500/640/g' app/validators/status_length_validator.rb
```