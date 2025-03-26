# Backups

We backup the persistent data storage of vmst.io multiple times per day/week and to different locations.

## Database Backups

Posts made to [vmst.io](https://vmst.io) are stored in backend PostgreSQL databases with Redis used as a key-value store and timeline cache.

- For the backup of PostgreSQL, we use `pg_dump` with some custom scripts that process each task and then fire off notifications to our backend channels.
- Full database backups are currently made every week and replicated twice across geographies.
- In addition to full backups, DigitalOcean provides transaction-level rollback functionality as part of their managed database service.

## Media/CDN Store Backups

- The CDN/media data is synced directly to another DigitalOcean object store via the `rclone` [utility](https://rclone.org).
- This is done using some custom scripts that process each task and then fire off notifications to our backend channels.
- CDN backups currently run every day.
- Only the latest copy of CDN data is retained.

## Configuration Backups

- All configuration files for core applications, documentation, and web clients are stored on GitHub with changes committed there before being applied to servers.

## Backup Image

We have a customized container image available from both Docker and GitHub container registries used for backup purposes.
This image is designed for backup, replication, and maintenance of container-based Mastodon implementations.
It includes rclone, PostgreSQL, and Redis utilities.

- The version tags for the image represent the version of rclone used.
- The image is based on Debian 12.
- PostgreSQL utilities are based on version 16.
- Redis utilities are based on version 7.

There are `/root/backups` and `/root/scripts` directories suitable for mounting and processing relevant files.

In order to use rclone, you'll need to mount an existing `rclone.conf` file to `/root/.config/rclone/rclone.conf`.

- [GitHub](https://github.com/users/vmstan/packages/container/package/rclone)
- [Docker](https://hub.docker.com/r/vmstan/rclone)
