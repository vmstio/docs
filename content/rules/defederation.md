---
title: Defederation
---

# Defederation

We "defederate" vmst.io from other instances that are incompatible with our fundamental rules, in an effort to protect our users and limit our liability.
The decision to defederate can come from reports by our users but is also based on community discussion around such bad actors, including the periodic import of community maintained blocklists.
We would rather be proactive in blocking bad actors versus waiting for abuse to happen.

## Export

We list all defederated instances at [vmst.io/about](https://vmst.io/about), but also periodically post the full listing in CSV format on our GitHub.

:button-link[Download Blocklist]{icon="mdi:file-download-outline" href="https://github.com/vmstan/vmstio/blob/main/domain_blocks.csv" blank}

Posting the list as a CSV file allows other instance administrators to easily import our blocklist or compare it against their own.

### Sensitivity

Our defederated instance list includes domains where the name itself may contain offensive language, or the resulting site contains harmful or illegal materials. As a result the domains are partially redacted when viewing on the [vmst.io/about](https://vmst.io/about) listing.

However, in order to import our list into your own, these domain names are listed on GitHub.

::alert{type="warning"}
When you view this list or visit these sites you do so at your own discretion and/or liability.
::

## Imports

We believe community maintained blocklists serve an important purpose to help jump start instances in providing protection to users from abusive or disruptive individuals.

We choose to use extremely high-consensus threshold lists for our suspension (blocked) list to prevent breaking connections from users unnecessarily.
We have a lower threshold for importing limitation (muted) lists as these changes can be undone without breaking user connections.

### Sources

Suspension Sources:

- [Oliphant Birdsites](https://codeberg.org/oliphant/blocklists/raw/branch/main/blocklists/mastodon/birdsite.csv)
- [Oliphant 100%](https://codeberg.org/oliphant/blocklists/raw/branch/main/blocklists/mastodon/100.percent.csv)
- [Seridy Tier 0](https://seirdy.one/pb/tier0.csv)
- [Gardenfence Tier 0](https://raw.githubusercontent.com/gardenfence/blocklist/main/gardenfence-mastodon.csv)

Limitation Sources:

- [Oliphant Tier 1](https://codeberg.org/oliphant/blocklists/raw/branch/main/blocklists/mastodon/_unified_tier1_blocklist.csv)

_Limitations are processed after suspensions, so if a site appears in multiple sources the more restrictive tier is applied._

Import Filtering:

- As part of our import process we perform an activity check on the domain, if the domain is not currently an ActivityPub endpoint, it is ignored.
- We run this import process on a regular basis, so if a previously failed domain in the blocklist come back online, they are incorporated back into our defederation list.
- We do not import changes to the status of any instance that would suspend another member of the [joinmastodon.org](https://joinmastodon.org) [Server Covenant](/about/covenant), because we believe in allowing portability between member instances, although they can be automatically limited.
- We maintain an internal list of allowed instances that might be automatically limited by importing the raw source list, with rare exception this only applies to the limitation sources.
- Exceptions to this process may made on a case by case basis.

![Import Diagram](/blocksync.png)

## Reporting

If during your use of the platform, you find another instance that you think needs to be restricted from interacting with ours **or** if you feel that another instance may have been blocked by our staff in error, please file an issue on our [GitHub](https://github.com/vmstan/mastodon/issues/new/choose).
If you'd feel more comfortable, you can also reach out to one or more of our staff directly via private mention.

## [Threads →](/rules/threads)