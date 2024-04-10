---
title: Object Storage 
---

# Object Storage

Object storage is a scalable and cost-effective storage solution that is used in Mastodon to store and manage large volumes of unstructured data, such as media files (images, videos, and audio) and static assets.
In Mastodon, object storage plays a crucial role in efficiently handling and serving user-uploaded media content.

Here's how object storage is used in Mastodon:

- Media uploads: When users upload media files, such as images or videos, to Mastodon, these files are stored in object storage. These storage systems provide high availability, durability, and scalability, ensuring that the uploaded media is securely stored and accessible when needed.
- Media processing: After the media files are uploaded, Mastodon performs various processing tasks, such as resizing images, creating thumbnails, and transcoding videos. The processed files are then stored back into the object storage for serving to users.
- Content delivery: Mastodon serves the media content stored in object storage directly to users. Object storage systems typically support content delivery through URLs, which can be used by Mastodon to embed media files in toots or serve them through media previews. This ensures that the media content is efficiently served to users without overloading the Mastodon application server.
- Cache and CDN integration: Object storage systems often support integration with content delivery networks (CDNs) to improve the performance of media delivery. Mastodon can leverage this integration to cache and distribute media content to users from a CDN, reducing the load on the object storage system and improving the user experience.

We use the DigitalOcean Spaces service, which is an S3-compatible object storage provider and includes a content delivery network (CDN) to distribute attached media to multiple points, reducing access latency for users and federated servers.

Example of `.env.production` configuration settings relevant to DigitalOcean Spaces:

```text
# Object Storage
S3_ENABLED=true
S3_PROTOCOL=https
S3_BUCKET=ourbucketname
S3_REGION=nyc3
S3_HOSTNAME=nyc3.digitaloceanspaces.com
S3_ENDPOINT=https://nyc3.digitaloceanspaces.com
AWS_ACCESS_KEY_ID=NOTINAMILLI0NYEARS
AWS_SECRET_ACCESS_KEY=hahahahahahahahahahahahaha
S3_ALIAS_HOST=cdn.vmst.io
CDN_HOST=https://assets.vmst.io
```

Our Spaces is in the DigitalOcean NYC3 data center, which is separate from the rest of the workloads which exist in the TOR1 (Toronto) data center.
By default, the items in the Space are accessible through a non-CDN accessible endpoint, but once that is created on the DigitalOcean side, is set in Mastodon by using the `S3_ALIAS_HOST` variable.