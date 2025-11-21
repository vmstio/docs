# Backups

We backup the persistent data storage of vmst.io multiple times per day/week and to different locations.

## Databases

Posts made to [vmst.io](https://vmst.io) are stored in backend PostgreSQL databases with ValkeyDB used as a replacement for Valkey as a key-value store and timeline cache.

- The primary backup method for our PostgreSQL database cluster is via Digital Ocean's managed backups, which provide transaction-level rollback functionality in addition to nightly backups.
- In addition we use `pg_dump` with some custom scripts that performs additional full database backups every weekend, which is then and replicated twice across geographies.

Data in the Valkey databases is mostly ephemeral but to avoid problems a snapshot taken periodically to restore in the event of a service failure.

## Media

- Media data is stored on S3-compatible storage which is then synced directly to another object store via the `rclone` [utility](https://rclone.org).
- This is done using some custom scripts that process each task and then fire off notifications to our backend channels.
- Media backups currently run every day.
- Only the latest copy of media data is retained.

## Configuration

- All configuration files for core applications, documentation, and web clients are stored on GitHub with changes committed there before being applied to servers.

## Docker Image

We have a customized container image available from both Docker and GitHub container registries used for backup purposes.
This image is designed for backup, replication, and maintenance of container-based Mastodon implementations.
It includes rclone, s3cmd, PostgreSQL, and Valkey utilities.

- The version tags for the image represent the version of rclone used.
- The image is based on Debian Trixie.
- PostgreSQL utilities are based on version 17.
- Valkey utilities are based on version 7.

There are `/root/backups` and `/root/scripts` directories suitable for mounting and processing relevant files.

In order to use rclone, you'll need to mount an existing `rclone.conf` file to `/root/.config/rclone/rclone.conf`.

- [GitHub](https://github.com/users/vmstan/packages/container/package/rclone)
