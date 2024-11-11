---
title: Source Code
---

# Source Code

Our goal is to provide the best possible Mastodon experience for our members.
One way to deliver on that is by delivering the most up-to-date Mastodon code.
We "run off main", which means using the latest commits to the `main` branch of the Mastodon codebase found on the project's official [GitHub](https://github.com/mastodon/mastodon) repository.

We take a clean copy of the latest Mastodon code and then apply a limited set of modifications with a custom script.
We then build the modified code inside a Docker container, publish it to GitHub Container Registry, for consumption by our Kubernetes cluster.

Our server-specific customizations include:

- Customizing the Mastodon logo, if needed, for events like Pride Month ([SVG](https://cdn.vmst.io/docs/masto-pride.zip))
- Raising the post character count limit from 500 to 640 ([vmstan/mastodon #36](https://github.com/vmstan/mastodon/pull/36))
- Adding the [Bird UI](/clients/bird) and [Tangerine](/clients/tangerine) themes ([vmstan/mastodon #6](https://github.com/vmstan/mastodon/pull/6))

Individual container builds may include additional changes which are being tested on vmst.io, and may be sourced from PR's in the [official project repository](https://github.com/mastodon/mastodon) or in the [vmst.io development fork](https://github.com/vmstan/mastodon/pulls?q=is%3Apr+is%3Aopen+label%3Avmst.io%2Fdeployed).

## Container Availability

### Primary Image

Our customized container image is available from both Docker and GitHub container registries. This is suitable for the web/Puma and Sidekiq services.

- [GitHub](https://github.com/users/vmstan/packages/container/package/mastodon)

### Streaming Image

Mastodon 4.3-based images and beyond use a seperate container image for the Streaming API.

- [GitHub](https://github.com/users/vmstan/packages/container/package/mastodon-streaming)