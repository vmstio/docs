# docs.vmst.io

Documentation site for [vmst.io](https://vmst.io) - a member-funded Mastodon server for respectful technologists.

## About

This repository contains the public documentation for vmst.io, a professionally-operated Mastodon instance that prioritizes community, transparency, and technical excellence. The site documents our infrastructure, policies, funding model, and provides resources for current and prospective members.

## What is vmst.io?

vmst.io is a member-funded Mastodon server with:

- **100% Member Funded** - No ads, no investors, no data selling
- **Professional Infrastructure** - Kubernetes-based deployment with 99.9%+ uptime
- **Latest Technology** - Running Mastodon from the main branch
- **Respectful Community** - Clear rules and active moderation

## Documentation Content

The site includes comprehensive documentation on:

- **Funding & Operations** - Subscription tiers and cost transparency
- **Community Rules** - Guidelines following the Mastodon Server Covenant
- **Infrastructure** - Technical architecture and deployment details
- **Federation** - How we federate with other instances
- **Moderation** - Our moderation processes and policies
- **vmcrawl** - Instance reporting and discovery tool

## Development

Built with [Nuxt 4](https://nuxt.com) and [Docus](https://docus.dev) for a fast, modern documentation experience.

### Prerequisites

- Node.js (compatible with Nuxt 4)
- npm or your preferred package manager

### Quick Start

```bash
# Install dependencies
npm install

# Start development server
npm run dev
```

Visit `http://localhost:3000` to view the local development site.

### Build for Production

```bash
npm run build
```

The built site will be in the `.output` directory.

## Project Structure

```
docs/
├── content/              # Markdown documentation files
│   ├── index.md         # Homepage
│   ├── 1.funding.md     # Funding information
│   ├── 2.rules.md       # Server rules
│   ├── 3.vmcrawl.md     # vmcrawl documentation
│   └── about/           # Detailed documentation pages
├── public/              # Static assets (logos, images)
├── nuxt.config.ts       # Nuxt configuration
└── app.config.ts        # UI theme configuration
```

## Tech Stack

- **Framework**: Nuxt 4 with Docus theme layer
- **Content**: Nuxt Content (file-based markdown CMS)
- **Styling**: Tailwind CSS 4
- **UI Components**: Nuxt UI
- **Hosting**: DigitalOcean App Platform

## Contributing

Documentation updates and improvements are welcome. Please ensure changes maintain accuracy regarding vmst.io's actual infrastructure and policies.

## License

[MIT License](https://opensource.org/licenses/MIT)

## Links

- **Main Server**: [vmst.io](https://vmst.io)
- **Documentation**: [docs.vmst.io](https://docs.vmst.io)
- **Funding**: [Patreon](https://www.patreon.com/vmstan)
