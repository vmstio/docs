# Source Code

Our goal is to provide the best possible Mastodon experience for our members.
One way to deliver on that is by delivering the most up-to-date Mastodon code.
We "run off main", which means using the latest commits to the `main` branch of the Mastodon codebase found on the project's official [GitHub](https://github.com/mastodon/mastodon) repository.

We take a clean copy of the latest Mastodon code and then apply a limited set of modifications with a custom script.
We then build the modified code inside a Docker container, publish it to GitHub Container Registry, for consumption by our Kubernetes cluster.

Our server-specific customizations include:

- Customizing the Mastodon logo colors (if needed) for events like Pride Month, etc.
- Raising the post character count limit from 500 to 640 ([vmstan/mastodon #36](https://github.com/vmstan/mastodon/pull/36))
- Fixing the hide pill on images by hiding it ([vmstan/mastodon #45](https://github.com/vmstan/mastodon/pull/45))
- Fixing the alt/gif indicator visibility ([vmstan/mastodon #48](https://github.com/vmstan/mastodon/pull/48))
- Adding Docs link to the sidebar ([vmstan/mastodon #53](https://github.com/vmstan/mastodon/pull/53))
- Raising image attachment maximums from 8MP to 48MP ([vmstan/mastodon #54](https://github.com/vmstan/mastodon/pull/54))
- Raising the poll option limit from 4 to 6 ([vmstan/mastodon #55](https://github.com/vmstan/mastodon/pull/55))
- Fixing YouTube link previews by modifying the User-Agent for youtube.com ([vmstan/mastodon #57](https://github.com/vmstan/mastodon/pull/57))

Individual container builds may include additional changes which are being tested on vmst.io, and may be sourced from PR's in the [official project repository](https://github.com/mastodon/mastodon) or in the [vmst.io development fork](https://github.com/vmstan/mastodon/pulls?q=is%3Aopen+is%3Apr+label%3Avmst.io%2Fdeployed%2Cvmst.io%2Ftesting).
