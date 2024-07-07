---
title: vmcrawl
---

# vmcrawl

vmcrawl is a Mastodon-focused version reporting crawler.
It is written in Python, with a SQLite database backend.
It performs perodic polling of known Mastodon instances.

## Crawled Endpoints

vmcrawl will attempt to access the following endpoints of your Fediverse server:

- `/.well-known/host-meta`
- `/.well-known/webfinger`
- `/.well-known/nodeinfo`

Based on those results, if it's determined that your server is running Mastodon, it will contact:

- `/api/v2/instance` for Mastodon 4.x
- `/api/v1/instance` for Mastodon 3.x

## User Agent

The vmcrawl user agent can be identified as: `python-requests/2.31.0 (vmcrawl/0.1; +https://docs.vmst.io/projects/crawler)`

The specific version of python-request may be different depending on the system vmcrawl runs on.

### robots.txt

If you would like to stop vmcrawl from checking your instance, you can add the following to your `robots.txt` file:

```
User-agent: vmcrawl
Disallow: /
```