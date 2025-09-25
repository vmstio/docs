# Source Code

Our goal is to provide the best possible Mastodon experience for our members.
One way to deliver on that is by delivering the most up-to-date Mastodon code.
We "run off main", which means using the latest commits to the `main` branch of the Mastodon codebase found on the project's official [GitHub](https://github.com/mastodon/mastodon) repository.

We take a clean copy of the latest Mastodon code and then apply a limited set of modifications with a custom script.
We then build the modified code inside a Docker container, publish it to GitHub Container Registry, for consumption by our Kubernetes cluster.

Among other things, our server-specific customizations include:

- Customizing the Mastodon logo colors (if needed) for events like Pride Month, etc.
- Raising the post character count limit from 500 to 640
- Raising image attachment maximums from 8MP to 48MP
- Raising the poll option limit from 4 to 6

Individual container builds may include additional changes which are being tested on vmst.io, and may be sourced from PR's in the [official project repository](https://github.com/mastodon/mastodon).
These can be identified by the included PR number in the version string.

All of the local custom code can be identified the [vmst.io development fork](https://github.com/vmstan/mastodon/pulls?q=is%3Aopen+is%3Apr+label%3Avmst.io%2Fdeployed%2Cvmst.io%2Ftesting) with the `deployed` or `testing` tags.
