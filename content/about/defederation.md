---
title: Defederation
---

# Defederation

We defederate (aka Fediblock) vmst.io from other servers that are incompatible with our fundamental rules, in an effort to protect our users and limit our liability.
We would rather be proactive in blocking bad actors versus waiting for abuse to happen.

The fill list of defederated servers is available [from Mastodon](https://vmst.io/about).

## Sources

As of December 9, 2024, we leverage the [IFTAS FediCheck](https://connect.iftas.org/library/iftas-documentation/fedicheck/) platform to automatically manage our defederations.

- We choose to use the high-consensus 66% threshold setting for our suspension (blocked) list to prevent breaking connections from users unnecessarily.
- We may also choose to manually issue limitations (mute) servers, outside of what FediCheck will issue.
- We also have a handful of manually issued blocked servers to aid in enforcement of our [anti-Bridging](/rules/bridges) policy.

## Threads

Some Mastodon servers proactively defederate from the entire `threads.net` domain, and some have gone further and agreed to defederate from any server that does not also defederate from Threads.

While we are supportive of administrators choosing to disconnect themselves from whatever servers they choose, we would take exception to this second-order level of defederation and consider it harmful to the health of the entire Fediverse.

At this time, vmst.io does not plan to defederate from Threads, although we may take action to restrict some Threads users or limit some Threads posts from appearing in federated timelines depending on their content, just as we would with any other server.
Additionally, Mastodon provides controls for individual users to block any domain they choose, so if this is a concern, you can defederate yourself from Threads at any time while remaining a member of vmst.io.