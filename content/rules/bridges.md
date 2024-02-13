---
title: Bridges
---

# Bridges

Problem: Not all the people or organizations you follow may have migrated from Twitter to open social systems like Mastodon, or they moved to a different decentralized network like Bluesky or Nostr which do not use ActivityPub as their federation protocol.

One option is to follow such accounts on other networks using a bridge.

There are a few issues here:

- While some people may intend to follow accounts from another network through a bridge and understand the limitations, these accounts end up federated and searchable by anyone else in the instance.
- These bridges may not respect the original author's privacy, or require them to opt-out of federation, republishing without the original author's permission or consent.
- There are a variety of backend issues when these bridged accounts are followed, unfollowed, replied to, and so on. For example, often the bridge implementations does not respond properly because it's overloaded or incorrectly implemented.

In general, vmst.io does not connect to these services or allow our users' posts to be accessed through these services.

## Twitter

Bridging with Twitter is typically a one-way operation, where software like [bird.makeup](https://sr.ht/~cloutier/bird.makeup/) running on a server connecting to the Twitter API and creates stub accounts of Twitter users, to then mirror their content as accounts on Mastodon.

Although the bridge might work to make Twitter content visible, it can't create real conversation; your likes and replies with the person running the Twitter account are not sent back to Twitter and are never seen by the author.

We have, since late 2022, actively been defederated from all known and active Twitter bridge sites.

### Exceptions

We have not typically defederated from instances and applications where the bridged content is curated, maintained and clearly identified as a Twitter bot, or where the content is being collected from many sources to create a unique product.
An example is content from [sportsbots.xyz](https://www.sportsbots.xyz).

We may re-evaluate this in the future.

## Bluesky

Bluesky intends to be a decentralized and federated service like Mastodon, but using their own [AT Protocol](https://atproto.com) instead of ActivityPub.
While federation is still under development, developers have already created bridges that would create a link between instances running Mastodon and Bluesky.

At this time, we have defederated from the known Bluesky bridge that is being developed, [brid.gy](https://github.com/snarfed/bridgy-fed).

## Nostr

Nostr is another decentralized and federate service that uses their own protocol instead of ActivityPub.

At this time, we have defederated from the known Nostr bridges in operation, based on [Mostr](https://gitlab.com/soapbox-pub/mostr).