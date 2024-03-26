---
title: Monitoring
---

# Monitoring

We monitor the health and availability of our infrastructure in a few different ways.

## BetterUptime

[BetterUptime](https://betterstack.com/uptime) powers our [status.vmst.io](https://status.vmst.io) page.
It monitors the status of our external endpoints:

- Mastodon API
- Streaming API
- Translation API
- Search API
- Media CDN
- Assets CDN
- [Elk](/clients/elk)
- [Phanpy](/clients/phanpy)

Uptime is calculated for the last 30/90 days.
We regularly report on these stastistics from our [@iostat](https://vmst.io/@iostat) bot.

In addition to providing a page for members to check when there might be issues, it actively alerts our team to any issues.

## Uptime Kuma

We utilize [Uptime Kuma](https://github.com/louislam/uptime-kuma) to provide more granular and internal alerting of our various services.
Where as BetterUptime reports on the public endpoints, Kuma reports on the endpoint health as it is visible from within our Kubernetes cluster.

These results are not available to the public.

## DigitalOcean

We use integrated metrics monitoring available through DigitalOcean to monitor and alert on CPU, memory, disk and other performance metrics of the host virtual machine and managed database systems.

![DigitalOcean Alerts](/do-alert.png)

## Community Monitoring

- [FediDB Entry](https://fedidb.org/network/instance?domain=vmst.io)
- [Instances.social](https://instances.social/vmst.io)
