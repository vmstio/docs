---
title: Defederation
---

# Defederation

We defederate (aka Fediblock) vmst.io from other servers that are incompatible with our fundamental rules, in an effort to protect our users and limit our liability.
We would rather be proactive in blocking bad actors versus waiting for abuse to happen.

The full list of defederated servers is available [from Mastodon](https://vmst.io/about).

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

### Survey Results

We conducted a survey of members in the first week of January 2025, relating to our continued federation with Threads.
At the time of the survey there were 7,680 Threads users visible by our server, with 505 follow relationships.

The survey was prompted mainly by Meta's announcement of [changes to their moderation polcies](https://www.theverge.com/2025/1/7/24338471/meta-hate-speech-hateful-conduct-policy-moderation).

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