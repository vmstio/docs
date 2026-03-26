---
title: Federation
description: Mastodon is built on open standards that have powered the web for decades. ActivityPub is what makes social networks like Mastodon work across different servers.
navigation:
  icon: i-material-symbols-cycle
---

Each Mastodon server is a community hub that stores messages for its members.

When you follow someone on another server, the servers communicate to exchange information and establish a trusted connection.
When you post, your server shares it with the servers of your followers, ensuring they see it.

ActivityPub is the protocol that allows you to interact seamlessly with friends on the over 9,000 active servers running Mastodon, and thousands of other servers running Pixelfed, Lemmy, Misskey, Akkoma, Gotosocial, micro.blog, Threads, Mbin and [so much more](https://fedidb.org/software).

vmst.io handles millions of these federation jobs per day.

## Defederation

vmst.io curates the servers with which it federates.
Our goal provide a space for people to use for all manner of topics and conversations, while observing the general etiquette of being in a public space.

We may block vmst.io resources from interacting with other servers for legal reasons or where they are in conflict with our [Rules](/rules), in an effort to protect our users and limit our liability.

The current list of impacted servers is always available [here](https://vmst.io/about), however in same cases due to the nature of why they are blocked the full domain name may not be visible.

The decision to defederate from another server is not one we take lightly, as it may be disruptive to user relationships.
We have two levels of defederation action that we may take against other servers.

### Limit

Any server that struggles to moderate their general membership or can be demonstrated to host individual accounts that would contravene our [Rules](/rules), may be Limited.

- All past and future accounts from the remote server are silenced and will not be visible in public timelines, but can be found and followed.
- Followed accounts will show up in the home timeline of the member following those accounts.

### Suspend

Any server that consistently fails to moderate their general membership and can be demonstrated to host a preponderance of accounts that contravene our [Rules](/rules) may be Suspended.

- All past and future accounts from the server are disconnected and undeliverable.
- No content from the remote server will be stored locally except for usernames.
- Accounts cannot be found nor followed.

Any server that delivers illegal or prohibited content will be Suspended.

## Sources

In addition to servers which are manually added by our administrative staff, we regularly import from the [IFTAS DNI](https://connect.iftas.org/library/iftas-documentation/iftas-dni-list/) list.

