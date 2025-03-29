# Mastodon

Aside from the various external dependencies, Mastodon has three main applications:

- Mastodon API/UI
- Streaming API
- [Sidekiq](/infrastructure/sidekiq)

## Web Tier

What users perceive as "Mastodon" is a [Ruby on Rails](https://rubyonrails.org) application with a [React](https://react.dev) front end, served by [Puma](https://puma.io).
This provides the Mastodon API, web user interface, as well as ActivityPub federation.

Our web tier runs on the DigitalOcean managed Kubernetes platform.

### Streaming

The Streaming API is a separate [Node.js](https://nodejs.org/en/) application which provides a background WebSockets connection between your browser session and the Mastodon server to provide real-time "streaming" updates as new posts are loaded to your timeline.