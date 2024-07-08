---
title: vmcrawl
---

# vmcrawl

vmcrawl is a Mastodon-focused version reporting crawler.
It is written in Python, with a SQLite database backend.
It performs perodic polling of known Mastodon instances.

## Crawled Endpoints

vmcrawl may attempt to access the following endpoints of your Fediverse server:

- `/.well-known/host-meta`
- `/.well-known/webfinger`
- `/.well-known/nodeinfo`

Based on those results, if it's determined that your server is running Mastodon, it may contact:

- `/api/v2/instance` for Mastodon 4.x
- `/api/v1/instance` for Mastodon 3.x
- `/api/v1/instance/peers`

## User Agent

The vmcrawl user agent can be identified as: `vmcrawl/0.1 (https://docs.vmst.io/projects/crawler)`

### robots.txt

If you would like to stop vmcrawl from checking your instance, you can add the following to your `robots.txt` file:

```
User-agent: vmcrawl
Disallow: /
```

## Collected Data

vmcrawl collects the following data only from instances that it identifies as Mastodon, or a related fork.

- Domain Name
- Software Version
- Total Users Count
- Active Users Count
- Administrator Email Address
- Source Code Repository

vmcrawl may perodically request a list of peer instances from a server, but only to discover new servers to request the data outlined above.
It does not store peer information for any server.
