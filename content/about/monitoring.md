---
title: Monitoring
description: We monitor the health and availability of our infrastructure in a few different ways.
navigation:
  icon: i-material-symbols-chat-error-outline
---

Our administrators use mulitple tools to be notified when there are system issues.

## BetterUptime

[BetterUptime](https://betterstack.com/uptime) powers our [status.vmst.io](https://status.vmst.io) page.
It monitors the status of our external endpoints:

- Mastodon API
- Streaming API

Uptime is calculated for the last 90 days.
Additionally, recent response times are shown.

We regularly report on these statistics from our [@iostat](https://vmst.io/@iostat) bot.

In addition to providing a page for members to check when there might be issues, it actively alerts our team to any issues.

## DigitalOcean

We use integrated metrics available through DigitalOcean's managed services platform to monitor and alert on CPU, memory, disk, and other performance metrics of the host virtual machine and managed database systems.

Additionally, we also use their internal monitoring service as a secondary measurement of network latency and availability reporting.
