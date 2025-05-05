# Redis

[Redis](https://redis.io) is an open-source, in-memory data structure store that is used as a database, cache, and message broker.
In Mastodon, Redis is used for various purposes to improve the performance, scalability, and reliability of the platform.

Starting in Mastodon 4.4, Redis folks (such as [Valkey](https://valkey.io)) or alternatives that implement the Redis API are supported for use.

We use the [Dragonfly](https://www.dragonflydb.io) controlled by their Kubernetes Operator.
We have three databases, all in a high-availibility configuration.

- Mastodon
- Sidekiq
- Cache

Our connection to Dragonfly is configured as the `REDIS_URL` variable using a connection string.

```text
REDIS_URL=redis://dragonfly-db-mastodon.default.svc.cluster.local
SIDEKIQ_REDIS_URL=redis://dragonfly-db-sidekiq.default.svc.cluster.local
CACHE_REDIS_URL=redis://dragonfly-db-cache.default.svc.cluster.local
REDIS_DRIVER=ruby
```

In addition to the HA-configuration, regular backup operations copy the data to an secure S3 bucket.
