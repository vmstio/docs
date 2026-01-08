---
title: Backups
description: We backup the persistent data storage of vmst.io multiple times per day/week and to different locations.
navigation:
  icon: i-material-symbols-storage
---

## Databases

Posts made to [vmst.io](https://vmst.io) are stored in a backend PostgreSQL.
Valkey (as a replacement for Redis) is used as a key-value store and timeline cache.
Search index data is stored in Elasticsearch.

- The primary backup method for our database clusters is via Digital Ocean's managed backups, which provide transaction-level rollback functionality in addition to nightly backups.
- In addition we use `pg_dump` with some custom scripts that performs additional full PostgreSQL backups, as-needed, which is then saved across geographies.

## Media

Media data is stored on DigitalOcean Spaces, an S3-compatible object storage.

- The primary backup method is via `rclone` copy operations, which duplicates the latest copy of media data to Backblaze B2 via `rclone` commands.
- Media backups currently run once per day, every day.

## Configuration

- All configuration files for core applications, documentation, and web clients are stored on GitHub with changes committed there before being applied to servers.
