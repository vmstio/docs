---
title: Redis
---

# Redis

[Redis](https://redis.io) is an open-source, in-memory data structure store that is used as a database, cache, and message broker. In Mastodon, Redis is used for various purposes to improve the performance, scalability, and reliability of the platform.

We use the DigitalOcean managed Redis database service, this delivers a highly available database backend. Our primary Redis service has 2 vCPU and 4GB of memory running Redis 7.x.

Our connection to Redis is configured as a `REDIS_URL` variable using a connection string.

```text
REDIS_URL=rediss://default:password@redis.db.ondigitalocean.com:25061
```

Note that the second `s` in `rediss` is not a typo and is used for TLS connections only.
Standard deployments of Mastodon currently cannot use this connection type, due to limitations of the `hiredis` driver.
We disable `hiredis` in our implementation.
