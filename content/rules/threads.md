---
title: Threads
---

# Threads

Threads, the micro-blogging app from Meta, has announced their intent to implement ActivityPub and join their user base to the rest of the Fediverse.

## Defederation Questions

Some Mastodon servers have announced proactive defederation from the `threads.net` domain, and some have gone further and agreed to defederate from any server that does not also defederate from Threads.

While we are supportive of administrators choosing to disconnect themselves from whatever servers they choose, we would take exception with this second-order level of defederation and consider that harmful to the health of the entire Fediverse.

At this time vmst.io does not plan to defederate from Threads, although we may take action to restrict some Threads users or limit some Threads posts from appearing in federated timelines depending on their content, just as we would with any other server.

### Privacy Implications

Mastodon servers do not broadcast private data like email or the IP address you use to other servers.
The software is built on the reasonable assumption that third party servers cannot be trusted.

vmst.io servers download, process and cache images and videos for you to view. Not only is this more efficient when multiple users want to view the same content from another server, it helps to preserve your privacy by acting as a proxy to that resource. Unless you choose to click through to the source content the originating server cannot get your IP address, browser name, or time of access.

Meta, or any other server that we federate with, cannot fingerprint or use other private data or track you across the web simply by us being federated with them.

Some folks are concerned that content posted on their server will be federated to Meta when someone using Threads follows them, allowing Meta to index that content.
While this is a valid concern, Mastodon provides controls for individual users to block any domain they choose, so if this is a concern you can defederate yourself from Threads at any time while remaining a member of vmst.io.
However, if your Mastodon account page (ex: [https://vmst.io/@vmstan](https://vmst.io/@vmstan)) is already publicly accessible, search engines and other systems can already index your posted content.

### Advertising

Nobody on Mastodon can insert advertising into your user interface, unless you use a third-party client app that is funded that way.
Unless you use Threads, you will not see any ads from Threads.

The Mastodon software does not include any functionality to display ads in the web UI or the official mobile app, and vmst.io will never add the ability to do so as we are not funded by advertising.

It is not possible for any third party server to insert ad-like posts into your home feed, since your home feed is calculated by your own server from the people (and hashtags) that you choose to follow.

If someone you follow makes a sponsored post and you do not want to see it, you can unfollow or mute that person, just as if that other person was on a Mastodon server.

## Known Issues

At this time, Threads has limited federation abilities:

- You are only able to follow Threads users that opt-in to Fediverse support, which Meta labels as a "beta" feature
- Threads users can only opt-in if they live in counties where Meta has enabled the feature (basically, everywhere except the the European Union)
- Threads users cannot follow Mastodon accounts at this time
- Replies you make to Threads user posts look like any other Fediverse reply to vmst.io and other Mastodon users, but on the Threads side can only be see by the post author
- Replies you make can only be liked by the post author
- Meta-imposes a delay to post federation of **fifteen minutes**, this is visible on your timeline where posts may appear out-of-order as they displayed when are received by our server with the original timestamp
- Threads will only federate with servers where their Trust & Saftey teams have the ability to review a public local timeline (see: [https://help.instagram.com/914046486923176/](https://help.instagram.com/914046486923176/))