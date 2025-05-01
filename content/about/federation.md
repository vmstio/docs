# Federation

Mastodon is built on open standards, using sustainable technologies (i.e. no blockchain) that have powered the web for decades.
ActivityPub is what makes social networks like Mastodon work across different servers, kind of like how email lets you message people regardless of whether they use Gmail or Outlook.

Think of each server as a community hub that stores messages for its members.
When you follow someone on another server, the servers communicate to exchange information and establish a trusted connection.
When you post, your server shares it with the servers of your followers, ensuring they see it.
This allows you to interact seamlessly with friends on different servers, as the servers handle all the behind-the-scenes communication.

![Federation](/federation.png)

The actual process of delivering content between servers, often referred to as federation, isn't anywhere near as clean looking as the chart above might suggest, with 9,000 active servers running Mastodon, and thousands of other servers running Pixelfed, Lemmy, Misskey, Akkoma, Gotosocial, micro.blog, Threads, Mbin and [so much more](https://fedidb.org/software).

vmst.io handles millions of these federation jobs per day.

Federation is a privilege, not a right.
Each server must carefully curate the actors it federates with.

## Defederation

vmst.io curates the servers with which it federates.
Our goal provide a space for people to use for all manner of topics and conversations, while observing the general etiquette of being in a public space.

We defederate (aka Fediblock) vmst.io from other servers that are incompatible with our [Rules](/rules), in an effort to protect our users and limit our liability.

The full list of defederated servers is available [from Mastodon](https://vmst.io/about).

The decision to defederate from another server is not one we take lightly, as it may be disruptive to user relationships.
We have two levels of defederation action that we may take against other servers.

### Limit

Any server that consistently fails to moderate their general membership and can be demonstrated to host individual accounts that would contravene our [Rules](/rules) may be Limited.

- All past and future accounts from the remote server are silenced and will not be visible in public timelines, but can be found and followed.
- Followed accounts will show up in the home timeline of the member following those accounts.

### Suspend

Any server that consistently fails to moderate their general membership and can be demonstrated to host a preponderance of accounts that contravene our [Rules](/rules) will be Suspended.

Any server that consistently delivers illegal or explicit content, gore, or other media that is forbidden on our server will be Suspended.

- All past and future accounts from the server are disconnected and undeliverable.
- No content from the remote server will be stored locally except for usernames.
- Accounts cannot be found nor followed.

## Sources

In addition to servers which are manually added by our administrative staff, we regularly import from the following sources:

- [IFTAS DNI](https://connect.iftas.org/library/iftas-documentation/iftas-dni-list/)
- [IFTAS CARIAD](https://cariad.fedicheck.iftas.org/)

We would rather be proactive in blocking bad actors versus waiting for abuse to happen.
