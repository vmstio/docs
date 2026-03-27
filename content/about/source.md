---
title: Source
description: The majority of Mastodon servers are running the standard "tagged" releases from the Mastodon project, but we do things a little differently here.
navigation:
  icon: i-material-symbols-deployed-code-outline
---

Our goal is to provide the best possible Mastodon experience for our members.
One way to deliver on that is by delivering the most up-to-date Mastodon code.
We "run off main", which means using the latest commits to the `main` branch of the Mastodon codebase found on the project's official [GitHub](https://github.com/mastodon/mastodon) repository.

We take a clean copy of the latest Mastodon code and then apply a limited set of modifications with a custom script.
We then build the modified code inside a Docker container and publish it to our internal container registry for consumption by our Kubernetes cluster.

Among other things, our server-specific customizations include:

- Raising the post character count limit
- Raising the poll option limit from 4 to 6

Individual container builds may include additional changes which are being tested on vmst.io, and may be sourced from PR's in the [official project repository](https://github.com/mastodon/mastodon).
These can be identified by the included PR number in the version string.

All of the local custom code can be identified the [vmst.io development fork](https://github.com/vmstio/mastodon/pulls).
