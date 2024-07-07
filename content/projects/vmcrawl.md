---
title: vmcrawl
---

# vmcrawl

vmcrawl is a Mastodon-focused version reporting crawler.
It is written in Python, with a SQLite database backend.
It performs perodic polling of known Mastodon instances.

## User Agent

The vmcrawl user agent can be identified as: `python-requests/2.31.0 (vmcrawl/0.1; +https://docs.vmst.io/projects/crawler)`

The specific version of python-request may be different depending on the system vmcrawl runs on.

### robots.txt

If you would like to stop vmcrawl from checking your instance, you can add the following to your `robots.txt` file:

```
User-agent: vmcrawl
Disallow: /
```