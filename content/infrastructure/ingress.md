---
title: Ingress
---

# Ingress

Routing of inbound HTTP requests.

## Load Balancing

We use DigitalOcean managed load balancer objects to distribute user traffic across our frontend reverse proxies.

## Reverse Proxies

We use [Nginx](https://www.nginx.com) as our reverse proxy software.
In our Kubernetes environment this is in the form of the [Ingress Nginx Controller](https://kubernetes.github.io/ingress-nginx/).

![Reverse Proxy Diagram](/reverse-proxy.png)

Our Nginx reverse proxies provide TLS/SSL termination.
