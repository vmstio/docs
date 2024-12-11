---
title: Bridges
---

# Bridges

Problem: Not all the people or organizations you follow may have migrated from Twitter to open social systems like Mastodon, or they moved to a different decentralized network like Bluesky or Nostr, which do not use ActivityPub as their federation protocol.

One option is to follow such accounts on other networks using a bridge.

There are a few issues here:

- While some people may intend to follow accounts from another network through a bridge and understand the limitations, these accounts end up federated and searchable by anyone else on the server.
- These bridges may not respect the original author's privacy or require them to opt-out of federation, republishing without the original author's permission or consent.
- There are a variety of backend issues when these bridged accounts are followed, unfollowed, replied to, and so on. For example, often the bridge implementations do not respond properly because they are overloaded or incorrectly implemented.

In general, vmst.io does not connect to these services or allow our users' posts to be accessed through these services.

## Bluesky

Bluesky intends to be a decentralized and federated service like Mastodon, but using their own [AT Protocol](https://atproto.com) instead of ActivityPub.
While federation is still under development, developers have already created bridges that would create a link between servers running Mastodon and Bluesky.

At this time, we have defederated from the known Bluesky bridge that is being developed, [brid.gy](https://github.com/snarfed/bridgy-fed).

## Nostr

Nostr is another decentralized and federated service that uses their own protocol instead of ActivityPub.

At this time, we have defederated from the known Nostr bridges in operation, based on [Mostr](https://gitlab.com/soapbox-pub/mostr).

## Threads

Threads, the micro-blogging app from Meta, has announced their intent to implement ActivityPub and join their user base to the rest of the Fediverse.
Since this is a native implementation and not a bridge, it is not covered by our general prohibition on these services.

More information can be found [here](/about/threads).

## X-Twitter

From our start in 2022 through late 2024, we blocked federation with X-Twitter applications [bird.makeup](https://sr.ht/~cloutier/bird.makeup/) and similar clones.

After re-evaluating this policy, we now allow limited federation with these types of platforms so they can be directly added by a user but will not appear in general search results.
Users will receive an alert that the domain is limited by our systems before viewing the profiles when they're identified.

Unlike bridging solutions for Bluesky or Nostr, which are two-way, applications that bridge X-Twitter are exclusively a one-way operation.
Your likes and replies with the person running the X-Twitter account are visible to other vmst.io users, but are not sent back and are never seen by the author.
Boosts are shared to your followers, and visible to them only if they are on servers that do not block them.

No vmst.io user data is ever shared with X-Twitter.