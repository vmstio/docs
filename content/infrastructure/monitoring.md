# Monitoring

We monitor the health and availability of our infrastructure in a few different ways.

## BetterUptime

[BetterUptime](https://betterstack.com/uptime) powers our [status.vmst.io](https://status.vmst.io) page.
It monitors the status of our external endpoints:

- Mastodon API
- Streaming API
- Automation API
- Media CDN
- Asset CDN
- Documentation (this site)
- Bots & Automation

Uptime is calculated for the last 30/90 days.
We regularly report on these statistics from our [@iostat](https://vmst.io/@iostat) bot.

In addition to providing a page for members to check when there might be issues, it actively alerts our team to any issues.

## DigitalOcean

We use integrated metrics monitoring available through DigitalOcean to monitor and alert on CPU, memory, disk, and other performance metrics of the host virtual machine and managed database systems.
