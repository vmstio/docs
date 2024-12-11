---
title: Threads
---

# Threads

Threads, the micro-blogging app from Meta, is working towards implementing ActivityPub and join its user base to the rest of the Fediverse.

## Known Issues

At this time, Threads has limited federation abilities:

- **You are only able to follow Threads users that opt-in to Fediverse support, which Meta labels as a "beta" feature.**
- Threads users can only opt-in if they live in counties where Meta has enabled the feature (basically, everywhere except the European Union).
- Threads users can only follow Mastodon accounts that have previously interacted with them.
- Threads users can only like Mastodon posts that federate into their platform, however, Mastodon users can like, boost, bookmark, and reply to any Threads post just like they do with another Mastodon server.
- Meta-imposes a delay to post federation of **fifteen minutes**, which may be visible on your timeline where posts may appear out-of-order as they were displayed when they were received by our server with the original timestamp.

## Privacy Implications

Mastodon servers do not broadcast private data like email or the IP address you use to other servers.
The software is built on the reasonable assumption that third-party servers cannot be trusted.

vmst.io servers download, process, and cache images and videos for you to view. Not only is this more efficient when multiple users want to view the same content from another server, it helps to preserve your privacy by acting as a proxy to that resource.
Unless you choose to click through to the source content, the originating server cannot get your IP address, browser name, or time of access.

Meta, or any other server that we federate with, cannot fingerprint or use other private data or track you across the web simply by us being federated with them.

Some folks are concerned that content posted on their server will be federated to Meta when someone using Threads follows them, allowing Meta to index that content.
While this is a valid concern, if your Mastodon account page (ex: [https://vmst.io/@vmstan](https://vmst.io/@vmstan)) is already publicly accessible, search engines and other systems can already index your posted content.

### Advertising

Nobody on Mastodon can insert advertising into your user interface, unless you use a third-party client app that is funded that way.
Unless you use Threads, you will not see any ads from Threads.

The Mastodon software does not include any functionality to display ads in the web UI or the official mobile app, and vmst.io will never add the ability to do so as we are not funded by advertising.

It is not possible for any third-party server to insert ad-like posts into your home feed, since your home feed is calculated by your own server from the people (and hashtags) that you choose to follow.

If someone you follow makes a sponsored post and you do not want to see it, you can unfollow or mute that person, just as if that other person was on a Mastodon server.
