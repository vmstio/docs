---
title: Moderation
---

# Moderation

In the spirit of full disclosure, we have decided to make our moderation process open to public viewing.
The purpose is to guide our staff in their decisions to take action on a member.

There may be times where moderators and administrators deviate from this document as needed, specifically when new issues arise that have not been covered by existing processes.
Ultimately, our staff may take action on any account they deem necessary to protect the health and safety of the server and other users.

If you feel you have been treated unfairly by our staff, you may file an appeal or contact an Administrator.

## Staff

There are two levels of moderation staff with different abilities:

* Administrator
* Moderator

### Moderators

Moderators are vmst.io community members with additional permissions to take action on any reported or observed user account in violation of our rules.
They also have the ability to help maintain the trending functions of the Explore page.

Our moderators are volunteers who contribute their time, energy, and knowledge.

### Administrators

Administrators have full infrastructure level access.
They also act as senior moderators and community leaders.

The Administrators are **the final authority** on any appeals, moderation issues, or rule interpretations.

## Reports

When a post is reported, all members of the staff receive an email alert and an alert in the Mastodon user interface.

Reports about members of the staff cannot be seen by that staff member in the Mastodon UI.

### Confidentiality

All internal discussion of reports should be considered confidential.

The exact source of a report should never be revealed to a user, unless there are extenuating legal circumstances, and then only at the discretion of an Administrator.

Communication of disciplinary actions against user accounts should be done outside of the public view, such as through Mastodon's built-in warning/appeals system, email, private mention, or other secure means.
All private communication regarding actions should be documented in appropriate internal channels.

Our staff will use discretion in moderating our users, and we expect the same from our members who have been subject to Moderator actions.
Users who push back or question in public moderation decisions made against an account should be directed to an Administrator for a public response, if it is warranted.

Should the situation escalate towards harassment of staff, the member will be asked to leave vmst.io.

## Rules

All [Rules](/rules) are not created equal.

At a high level, reports will generally fall into a few different categories.

* "I don't like it"
* SPAM
* Illegal Content
* Rule Violation
* Something Else

These are based on the default options for the Mastodon UI and are set by the user who files the report.
Keep in mind that third-party clients may have fewer options based on their usage of the API.

Moderators can determine if a report is classified incorrectly and then reclassify it, but failure to properly classify a report is not grounds to dismiss the report.
We should always err on the side of trusting the user making the report that there is a problem to address.

### "I don't like it"

The Mastodon UI will direct users who choose "I don't like it" to mute or block the user.
If this is insufficient, and a report is still generated, it must be classified differently.

### SPAM

Clear and obvious SPAM should be actioned by suspending the offending account.

Examples of clear and obvious might be new accounts or accounts from other servers that:

* Post links to external sites for pornography, cryptocurrency, gambling, or illegal content.
* Posts in excess, particularly if they appear automated.
* Use excessive mentions or hashtags.

Please refer to our rules on [Advertising & Excessive Promotion](/rules/spam) for items which might run afoul of this rule but are less clear and obvious.

### Extremism

We have a zero tolerance policy for violations of our bigotry or extremism policies.
If you find users posting openly hateful content, you are authorized to immediately suspend the user’s account.

If the account has just signed up or their time on the server has only been used for such content, reach out to an Administrator for immediate deletion of the account profile.

### NSFW/Sexual Content

Please refer to our rules on [NSFW](/rules/spam) content for items which might run afoul of this rule.

Sexual content might generally fall into one of three categories:

* 18+
* Explicit
* Illegal

18+ content must be posted with a content warning so it is not visible by default.
Users should not use their vmst.io accounts for posting sexually explicit or pornographic content.
Illegal content, such as CSAM or content that violates the consent of others, will be actioned by account deletion and referral to the appropriate law enforcement agency.

### Brand Accounts

Brands who create accounts in violation of our [policies](/rules/brands) will generally be asked to migrate their account to a different server.
These types of violations should be handled by Administrators.

## Report Types

There are three main types of reports on Mastodon:

* vmst.io user vs vmst.io user (intra-server)
* vmst.io user vs federated server user (inter-server)
* federated server user vs vmst.io user (inter-server)

### Intra-Server Reports

When our users report our users, we are only accountable to ourselves.
In this case, it’s likely that someone will be unhappy with the results of the reporting and subsequent action.
We must do what is right and in the best interest of the community.

While members can appeal, they also have the ability to migrate their account to another server if the resulting moderation actions do not satisfy them.

### Inter-Server Reports

When reports involve other servers, we must always be mindful that there is a moderation team involved in both places.
Our team is responsible for the enforcement of our rules on our server, and other servers may have rules and interests that are different from our own.

#### vmst.io vs The Federation

When our members report another server user, we have the ability to prohibit the remote user from interacting with our members, but we cannot control what the moderation team of the other server does with their report.
If we take action to limit their account and its abilities, those only impact its interaction with OUR users.

If there are entire servers that are engaging in behaviors that are putting our users at risk, or where the user-base is consistently in violation of our rules, then we may take action to defederate the entire server.

#### The Federation vs vmst.io

When users of another server report our users, we must be mindful of two things:

* Are they violating OUR server rules?
* Are they making us look like a bunch of jerks?

If we have members who are continually getting reported by other servers, those administrators and moderators may eventually take action to defederate our server.

If what our members are doing are not in violation of our rules, but are deemed inappropriate for the community of another server, then that’s their prerogative to take action to limit that user from interacting with their users, just as we can do the same.

## Available Actions

There are a few options available for any reported content.

* Mark as resolved (Dismiss)
* Delete posts
* Limit user
* Suspend user
* Send a warning
* Freeze user
* Set content Sensitive

The most common types of moderation events are expected to be Mark as Resolved or Send a Warning to the member.

Freezing or suspending local users should be done when there are either escalating or egregious violations of site policy.

All default user moderation decisions (aside from Mark as Resolved) will notify the impacted local user by email.
Remote user accounts are not notified of decisions made by our staff.
Some of the options accessible under Custom have the ability to disable the user notification settings, but sending email notices is still considered standard practice.

### Action Summary

Please refer to the following chart as a quick reference for appropriate actions to take against a user account based on the type of user.

| **User**   | Warn | Freeze | Limit | Suspend |
|------------|------|--------|-------|---------|
| **Local**  |   🟢  |    🟢   |   🔴   |    🟢    |
| **Remote** |   🔴  |    🔴   |   🟢   |    🟢    |

### Warning Presets

All major rule categories have warning presets available for Moderators to leverage when actioning on an account.
Moderators are expected to use these presets and only send a custom message to a user through the moderation portal if approved by an Administrator.

### Mark as Resolved (Dismiss)

Marking as resolved generally means you’re dismissing the report, because it’s determined to be not worthy of Moderator action.

Many times this is the appropriate action where an [individual can take action](https://docs.joinmastodon.org/admin/moderation/#individual-moderation) to mute or block another account if it's content that they don't personally like.

For vmst.io users, no mark is left against the user's profile.
The reporter, the account being reported, or the federated server (if applicable) are not notified of the decision to dismiss the report.

### Send a Warning

Sending a warning to a local user is preferable when they run afoul of our rules, but don't require any specific corrective action.

If a user has had multiple warnings issued, especially for the same type of behaviors, then additional corrective actions may be required.

### Set Content Sensitive

Set content Sensitive could be useful for posts that should probably have a content warning but were not initially set (NSFW type materials, or other things that may be offensive to other members).

Warnings can be sent in addition to taking this action.

### Freeze User

Freezing a local user prevents a user from posting with their account but does not hide or delete any previous posts. Useful for folks who need a time out, although there’s currently not a time-based mechanism for enforcement.

Freezing a user does not prevent them from exporting their data and moving to another server.
This is preferable for long-term user removal, where the content does not need to be removed but the user is no longer compatible with the vmst.io community.

### Limit User

Limit user prevents the user from being able to post with public visibility, meaning anything they do in the future is hidden from anyone who’s not already following.

This is useful for federated users, to limit their access to vmst.io members through direct interaction or the federated timeline.
The use against vmst.io members directly is not generally effective.

### Suspend User

Suspending a user is equivalent to a ban, as this prevents any interaction with the account and sets their account to be deleted by the server in 30 days unless other actions are taken.

## Call for Backup

If you’re unsure of what to do, ask for a second set of eyes.
If no one else is available, then you’re empowered to take action against the account to freeze it if you feel that it will stop a further escalation of the issue, until we can further assess the issue and make a determination as to what action is appropriate long-term.

## Appeals

Users can appeal actions of moderators.
In such cases, actions of moderators will be reviewed by an Administrator, and after additional discussion or deliberation, the appeal may be accepted or denied.

## Contributors

While we greatly appreciate folks who have paid subscriptions to vmst.io, or made one-time contributions, their financial contributions do not bring special favor from the staff for moderation issues.
At no time should this factor into the decision to take action against a member.

Subscribers are free to cancel their contribution to vmst.io at any time.
Administrators may, at their own discretion, refund subscriptions for members who have their account access restricted or terminated.
