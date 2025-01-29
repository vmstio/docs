---
title: Accounts
---

# Account Sign-Up

In order to keep the number of junk accounts on vmst.io as low as possible, we ask you to:

::list{type="success"}
- [Register for an account](https://vmst.io/auth/sign_up) and provide your intended use case
- Verify your provided email address by clicking a link we'll send to you from [mastodon@ses.vmst.io](/infrastructure/mailer)
- Complete a [hCaptcha](https://www.hcaptcha.com) verification
- Wait while our moderation system approves your account for use
::

::alert{type="danger"}
All new account requests that do not complete email and hCaptcha verification **within 7 days** are automatically deleted.
If our systems identify your account request as a risk, we may decline it or request additional information before approval.
::

## Rejection

Some registration requests may be automatically flagged by our spam detection system.
This automated screening helps us maintain a healthy community by preventing automated signups and potential abuse and may be flagged for one or more of the following reasons:

- The email address used has patterns commonly associated with temporary or disposable email services
- The IP address used for registration has been associated with suspicious activity

In some cases our moderation team may manually reject your registration request, for one of more of the following reasons:

- The registration attempt matched patterns typical of automated bot signups
- Multiple rapid registration attempts were detected from your network
- Your intended use case was unclear or in violation of our site policies

In either case, if you feel we've rejected your account request in error:

- Send an email to [our administrators](/about/staff) with a brief explanation of how you plan to use your vmst.io account
- Include any relevant links to your presence on other Mastodon instances or social media
- Provide additional context about your interest in joining our community

We will review your response and manually provision an account for you, if appropriate.

## Preserving Your Account

Some servers are happy to juice their registration numbers with drive-by registrations.
We want to set a higher bar and advertise folks who are part of our community.
As such, expect that all accounts on vmst.io will be active at some point.
You can be a lurker, but if you sign up and never come back, we reserve the right to delete your account.

The intention is not to delete accounts which fall out of use, only to avoid namesquatting or artificially boosting our registration numbers.
We also feel this helps mitigate against sleeper attacks, where accounts are created and sit idle until activated later, to appear with older registration dates, and hence bypass other anti-abuse migrations built into the platform.

Complete any of the following actions to confirm the account is not abandoned:

- [Set profile information](https://docs.joinmastodon.org/user/profile/), such as by adding an avatar or filling out biography information.
- Add [multi-factor authentication](https://fedi.tips/using-two-factor-authentication-2fa-on-mastodon/) to an account.
- Add a post, boost a post, or reply to any post.

If you join vmst.io and decide it isn't the best home for your Mastodon experience, you also have the ability to [move](https://docs.joinmastodon.org/user/moving/#migration) or [delete](https://docs.joinmastodon.org/user/moving/#delete) your own account at any time.

::alert{type="info"}
Accounts that are created but show no activity within the first 30 days are subject to suspension, pending deletion.
::

## Developers

If you are the developer of a Mastodon client or another ActivityPub/Fediverse project and would like to use an account on vmst.io to test the functionality of your application, please contact [@vmstan](https://vmst.io/@vmstan) before doing so.

While we are generally supportive of such things, we like to know ahead of time should it cause disruptions in service to other members.

Development accounts designed to scrape and/or index user data via our API or other means are prohibited.
