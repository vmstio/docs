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
- Adding the [Bird UI](/about/clients#bird) and [Tangerine](/about/clients#tangerine) themes ([vmstan/mastodon #6](https://github.com/vmstan/mastodon/pull/6))
- Raising the post character count limit from 500 to 640 ([vmstan/mastodon #36](https://github.com/vmstan/mastodon/pull/36))
- Modifying the timeline media indicators ([vmstan/mastodon #45](https://github.com/vmstan/mastodon/pull/45) & [vmstan/mastodon #48](https://github.com/vmstan/mastodon/pull/48))
- Adding some whimsey during the winter holidays ([vmstan/mastodon #51](https://github.com/vmstan/mastodon/pull/51))
- Adding Docs link to the sidebar ([vmstan/mastodon #53](https://github.com/vmstan/mastodon/pull/53))
- Flip the translate button location ([mastodon/mastodon #33619](https://github.com/mastodon/mastodon/pull/33619))

Individual container builds may include additional changes which are being tested on vmst.io, and may be sourced from PR's in the [official project repository](https://github.com/mastodon/mastodon) or in the [vmst.io development fork](https://github.com/vmstan/mastodon/pulls?q=is%3Aopen+is%3Apr+label%3Avmst.io%2Fdeployed%2Cvmst.io%2Ftesting).

## Container Availability

### Primary Image

Our customized container image is available from both Docker and GitHub container registries. This is suitable for the web/Puma and Sidekiq services.

- [GitHub](https://github.com/users/vmstan/packages/container/package/mastodon)

### Streaming Image

Mastodon 4.3-based images and beyond use a seperate container image for the Streaming API.

- [GitHub](https://github.com/users/vmstan/packages/container/package/mastodon-streaming)