---
title: Bridges
---

# Bridges

Problem: Not all the people or organizations you follow may have migrated from Twitter to open social systems like Mastodon, or they moved to a different decentralized network like Bluesky or Nostr which do not use ActivityPub as their federation protocol.

One option is to follow such accounts on other networks using a bridge.

## Twitter

Bridging with Twitter is typically a one-way operation, where software like [bird.makeup](https://sr.ht/~cloutier/bird.makeup/) connect to the Twitter API and create stub accounts for Twitter users, then mirror their content as accounts on Mastodon.

There are a few issues here:

- While some people may intend to follow the stub and understand the limitations, these accounts end up federated and searchable by anyone else in the instance.
- They’re published without the original author's permission or consent.
- Although the bridge might work to make Twitter content visible, it can't create real conversation; your likes and replies with the person running the Twitter account are not sent back to Twitter and are never seen by the author.
- In fact, there are a variety of backend issues when these stubs are followed, unfollowed, replied to, and so on, and their implementations don’t respond properly.
- These instances are typically overloaded or limited by Twitter API issues.

We have, since late 2022, actively been defederated from all known and active Twitter bridge sites.

### Exceptions

We have not typically defederated from instances and applications where the bridged content is curated, maintained and clearly identified as a Twitter bot.
An example is content from [sportsbots.xyz](https://www.sportsbots.xyz).
We may re-evaluate this in the future.

## Bluesky

Bluesky intends to be a decentralized and federated service like Mastodon, but using their own [AT Protocol](https://atproto.com) instead of ActivityPub.
Developers have already created bridges that would create a link between instances running Mastodon and Bluesky.

In addition to privacy concerns with how data would flow in and out of the Bluesky network (and the lack of control that it could provide users of Mastodon) there are also technical/architectural concerns that vmst.io administrators have with being reliant on these bridges for communication to another network.

At this time, we have defederated from the known Bluesky bridge that is being developed, brid.gy.

## Nostr

Nostr is another decentralized and federate service that uses their own protocol instead of ActivityPub.

At this time, we have defederated from the known Nostr bridge in operation, Mostr.