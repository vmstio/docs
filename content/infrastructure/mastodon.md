---
title: Mastodon
---

# Mastodon

Aside from the various external dependencies, Mastodon has three main applications:

- Web UI & API
- Streaming API
- [Sidekiq](/infrastructure/sidekiq)

## Web

The Mastodon Web tier consists of the Mastodon Web UI/API and the separate Streaming API service.
Our Web tier runs on the DigitalOcean managed Kubernetes platform.

### Puma

What users perceive as "Mastodon" is a [Ruby on Rails](https://rubyonrails.org) and [React](https://react.dev) application (with [Puma](https://puma.io) running as the web/presentation layer) providing both ActivityPub/Federation and the web user experience.

Our Puma pods are set to scale with Kubernetes and within Puma itself. We have Puma configured in `.env.production` and as follows:

```text
WEB_CONCURRENCY=4
MAX_THREADS=16
```

### Streaming

The Streaming API is a separate [Node.js](https://nodejs.org/en/) application which provides a background WebSockets connection between your browser session and the Mastodon server to provide real-time "streaming" updates as new posts are loaded to your timeline, to send notifications, etc.

As explained more in-depth in another section, the connection to the DigitalOcean-managed Redis database must be done via TLS.
For the Streaming API, there are additional configuration options that must be set to allow Node.js to connect when it expects a non-encrypted connection by default.

Example of `.env.production` configuration settings relevant to Streaming:

```text
# Streaming
STREAMING_API_BASE_URL=wss://streaming.vmst.io
DB_SSLMODE=require
NODE_EXTRA_CA_CERTS=/path/to/certs/do-internal.crt
```

The `DB_SSLMODE` and `NODE_EXTRA_CA_CERTS` settings are not there by default.
The DigitalOcean databases use self-signed/private certificates, but the variable set will tell the Streaming API to trust that connection based on the CA certs that are downloaded from DigitalOcean and uploaded to the server.
