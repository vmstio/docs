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

## Defederation

vmst.io does not restrict federation with Threads, although we may take action to restrict some Threads users or limit some Threads posts from appearing in federated timelines depending on their content, just as we would with any other server.
Mastodon provides controls for individual users to block any domain they choose, so if this is a concern, you can defederate yourself from Threads at any time while remaining a member of vmst.io.

### Survey Results

We conducted a survey of members in the first week of January 2025, relating to our continued federation with Threads.
At the time of the survey there were 7,680 Threads users visible by our server, with 505 follow relationships.

The survey was prompted mainly by Meta's announcement of [changes to their moderation policies](https://www.theverge.com/2025/1/7/24338471/meta-hate-speech-hateful-conduct-policy-moderation).

Users were given the following options to consider:

1. "Suspend" (aka Defederate) the `threads.net` domain which would completely block any interaction between `vmst.io` and Threads users.
2. "Limit" the domain so that Threads posts would not appear in public (Live Feeds > Other Servers) timelines, viewing Threads user profiles in the Web UI would have an additional notice added that the domain is limited, and Threads users would not be able to follow vmst.io accounts without user approval.
3. Take no action against Threads at this time. Administrators and moderators continue to evaluate changes to Threads and take action against any individual users as needed.

Users can block the `threads.net` domain on an individual basis without an instance-wide limitation.
However, if an instance-wide suspension were implemented, individual vmst.io users would not be able to federate or interact with Threads users.

The survey was anonymous unless members chose to share their name as part of the submission.
Named users were not specifically considered as part of any final decision (just because a popular account wanted us to do a thing we didn't necessarly do that thing) and the survey itself was used only to guide administrator decision making in the policy, not dictate any final outcome.

- 55% favored making no changes to vmst.io policy at this time.
- 36% would favor limiting the `threads.net` domain, with the impacts explained above.
- 17% would like us to completely suspend (aka Defederate) from Threads.

#### Key Themes

##### Individual Choice & User Autonomy

Most respondents emphasized the importance of personal choice in federation:

> "I still think the decision to block/not block should be left to individual users."

Users value the ability to make granular decisions about their Threads interactions, with some maintaining separate accounts for different purposes.

##### Content Access & Platform Value

Several respondents highlighted unique content benefits from Threads federation:

> "I don't feel as if mastodon has a ton of casual content (non-tech content or meta-fediverse content) to consider shutting off the firehose that is Threads entirely."

This perspective was echoed by others who noted the value of access to public figures and diverse content types.

##### Meta/Privacy Concerns

Strong concerns about Meta's corporate behavior appeared frequently:

> "Meta's complicity in the Myanmar genocide, their association with the Cambridge Analytica data scandal and indeed their proposed policies on generative AI and moderation mean they should not be given any further benefit of the doubt."

##### Current Experience & Practical Considerations

Users often referenced their direct experience:

> "Hasn't been a problem so far and I do follow a couple of Threads accounts."

Some questioned whether blocking would actually prevent Meta from accessing content, suggesting a focus on practical rather than symbolic actions.

##### Overall Sentiment

The feedback suggests a nuanced community position:

- Strong support for maintaining individual choice in federation decisions
- Openness to implementing limitations rather than full defederation
- Recognition of both Meta's problematic history and Threads' potential value
- Preference for evidence-based decisions over preemptive actions

Many users indicated they would support administrative decisions either way, but the majority favored maintaining some level of federation while implementing appropriate safeguards.

#### Administrator Decision

At this time vmst.io will not be making any changes reguarding our federation with Threads.