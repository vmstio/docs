---
title: Infrastructure
description: Running a full-featured, highly available, and performant Mastodon server, costs money.
navigation:
  icon: i-material-symbols-cloud-lock-outline
---

The purpose of these documents is to provide an overview of the infrastructure used to operate the Mastodon server, [vmst.io](https://vmst.io).

It should help provide some assurance to our current and potential members that care has been taken in architecting and operating this Mastodon instance, with the goal of providing better than 99.9% availability, each month, for our users.

## Architecture Goals

- Be easily recoverable in the event of failure.
- Be easily scalable, both vertically and horizontally.
- Provide a highly performant experience for our users.
- Don't operate what we're not best suited to operating.
- Automate as much as possible.

## Layout

![Server Layout](/vmstio-simple.png)

[DigitalOcean](https://www.digitalocean.com) is our primary hosting provider.
We have workloads in the TOR1 and NYC3 data centers, with Toronto being our primary compute workloads, and New York providing media hosting.

## Service Providers

This list represents the cloud provider dependencies to which vmst.io has a direct relationship.
If any of these providers have issues, it may create issues for vmst.io services.
Some of these services are paid for, while others are free to use.

| Vendor        | Service                                                                                                                                            |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| DigitalOcean  | Managed Kubernetes, Managed Databases (PostgreSQL, Valkey & OpenSearch), Object Storage with CDN, Container Registry, App Platform and Nameservers |
| AWS           | Simple Email Service                                                                                                                               |
| DeepL         | Translation Services                                                                                                                               |
| DNSimple      | Domain Registrar                                                                                                                                   |
| Let's Encrypt | SSL Certificates                                                                                                                                   |
| GitHub        | Configuration/Settings                                                                                                                             |
| hCaptcha      | Bot Detection                                                                                                                                      |
| Apivoid       | IP Information                                                                                                                                     |
| Grafana       | Infrastructure Logging & Metrics, Monitoring                                                                                                       |
| Backblaze     | Object Store Backups                                                                                                                               |
| n8n Cloud     | Automation Platform                                                                                                                                |

Other vendors or open-source projects that we consume or utilize but do not have an ongoing external API or system connection to are not included in this list.

## Compute Resources

### Kubernetes

We use the DigitalOcean managed Kubernetes service.
Our primary Kubernetes cluster ([Mulgrew](https://memory-alpha.fandom.com/wiki/Kate_Mulgrew)) uses virtual machines provisioned automatically by the control plane to be consumed as Kubernetes nodes.
There are multiple nodes with 4 vCPUs and 8 GB of memory each.
The total number of nodes can be scaled up or down based on overall demand.

All of the required Mastodon components are run in Kubernetes deployments, which create pods.
Each pod is a Docker container running a given service (Puma, Sidekiq, etc.)
Pods are distributed across multiple nodes in the cluster.

## Required Components

The following reflect the required software components to have a functional deployment of Mastodon:

### Mastodon

What users perceive as "Mastodon" is a [Ruby on Rails](https://rubyonrails.org) application with a [React](https://react.dev) front end, served by [Puma](https://puma.io).
This provides the Mastodon API, web user interface, as well as ActivityPub federation.

The Streaming API is a separate [Node.js](https://nodejs.org/en/) application which provides a background WebSockets connection between your browser session and the Mastodon server to provide real-time "streaming" updates as new posts are loaded to your timeline.

### Sidekiq

[Sidekiq](https://sidekiq.org) is the background job processing library used in Mastodon for federated content delivery, push notifications, media processing, and scheduled tasks.

In the vmst.io environment, Sidekiq processes nearly two million tasks per day.

vmst.io has multiple Sidekiq processes running, with separation of the workloads based on priority and to efficiently process user requests.

![Queue Design](/sidekiq-queues.png)

The exact number of processes and their assigned threads varies from time to time as workloads change.

### PostgreSQL

[PostgreSQL](https://www.postgresql.org) is an open-source relational database management system.
In Mastodon, it is used as the primary database to store and manage various types of data required for the functioning of the platform.

We use the DigitalOcean managed PostgresSQL database service, which delivers a highly available database backend.
Updates and maintenance are performed by DigitalOcean, independent of our administration efforts.

We have one database server ([Majel](https://memory-alpha.fandom.com/wiki/Majel_Barrett_Roddenberry)) running PostgreSQL 18.x, with 2 vCPU and 16GB of memory.

We leverage the integrated "Connection Pool" feature of the DigitalOcean hosted SQL, which in practice puts [PgBouncer](https://www.pgbouncer.org) in front of the database, to ensure that connections to the database by Mastodon cannot stay open and consume resources longer than needed.

### Redis

[Redis](https://redis.io) is an open-source, in-memory data structure store that is used as a database, cache, and message broker.
In Mastodon, Redis is used for various purposes to improve the performance, scalability, and reliability of the platform.

Starting in Mastodon 4.4, Redis forks (such as [Valkey](https://valkey.io)) or alternatives that implement the Redis API (such as [Dragonfly](https://www.dragonflydb.io)) are supported for use.

We use the DigitalOcean managed Valkey database service, which delivers a highly available database backend.

We have one database server ([Crusher](https://memory-alpha.fandom.com/wiki/Beverly_Crusher)) with 1 vCPU and 2GB of memory.

Updates and maintenance are performed by DigitalOcean, independent of our administration efforts.

### Ingress

The idea of "ingress" covers the routing of inbound HTTP requests.
We use DigitalOcean managed software defined network objects like load balancers and Kubernetes gateway objects to distribute user traffic across our frontend pods.

The managed load balancer service performs TLS termination at the Internet edge.
This edge supports IPv4 and IPv6 connectivity as of March 2026.

The load balancer hands off traffic to managed instances of [Envoy](https://www.envoyproxy.io) running on our Kubernetes nodes.
We use the [Gateway API](https://gateway-api.sigs.k8s.io) provided by DigitalOcean's managed [Cilium](https://cilium.io) deployment to manage the network configuration and HTTP routing.

From there, traffic is passed to the Mastodon pods, which run a custom implemention of the Mastodon networking stack to include [Thruster](https://github.com/basecamp/thruster) to perform caching of static assets as well as native HTTP/2 connectivity between pods.
Within the pods, traffic is then proxied directly to [Puma](https://puma.io), which is the native Mastodon web service.

Streaming traffic is passed from Envoy directly to the Node.js provided [Websocket](https://github.com/websockets/ws) running on those pods without any additional customization.

![Reverse Proxy Diagram](/reverse-proxy.png)

### Elasticsearch

On vmst.io we have full text search back-ended by our dedicated search indexing server ([Khan](https://memory-alpha.fandom.com/wiki/Khan_Noonien_Singh)) which is a managed OpenSearch instance hosted at DigitalOcean with 2 vCPU x 4GB RAM.

### [Translation API →](/about/translation)

[DeepL](https://www.deepl.com/whydeepl) is used as the translation API for our main web interface and client API.
It is known for its accuracy and ability to grasp nuances in language better than many other translation services.
For a list of languages that DeepL is able to process, please refer to [their documentation](https://developers.deepl.com/docs/getting-started/supported-languages).

### Object Storage

Object storage is a scalable and cost-effective storage solution that is used in Mastodon to store and manage large volumes of unstructured data, such as media files (images, videos, and audio) and static assets.
In Mastodon, object storage plays a crucial role in efficiently handling and serving user-uploaded media content.

We use the DigitalOcean Spaces service, which is an S3-compatible object storage provider and includes a content delivery network (CDN) to distribute attached media to multiple points, reducing access latency for users and federated servers.

Our Spaces is in the DigitalOcean NYC3 data center, which is separate from the rest of the workloads which exist in the TOR1 (Toronto) data center.

### SMTP Relay

All email notifications associated with the vmst.io Mastodon server should come from: `no-reply@vmst.io`.

- We use [Amazon Simple Email Service](https://aws.amazon.com/ses/) as our managed SMTP service, used for sending new user sign-up verifications, and other account notifications.
- We leverage industry technologies like `SPF` and `DKIM` to help verify we are the only ones sending you emails.

When you sign up for an account, and you provide us with an email address, we promise to only contact you there regarding your Mastodon account.
For more details, refer to our [Privacy Policy](https://vmst.io/privacy-policy)

## Networking

The local IP space used between systems on our virtual private cloud (VPC) network is issued by DigitalOcean, with static IP addresses that are assigned at the creation of the Droplet and persist throughout the lifecycle of the virtual machines.

Where possible, any communication between internal nodes is encrypted even though the communication takes place on the VPC network.

There are a few cases where traffic leaves our VPC but still communicates within the DigitalOcean network, such as when data is moved between Droplets in Toronto and the Object Storage in NYC, or during replication between NYC and SFO data centers.

### Public IPs

The public IP addresses assigned to our load balancer, CDN, and virtual machines are IP addresses issued and owned by DigitalOcean.

### DNS Resolution

We use [DNSimple](https://dnsimple.com/) for our domain registrar and use DigitalOcean for our nameservers.

## Security

In order to protect our users’ privacy and data, we implement a number of different security measures on our systems.

They include:

- Preventing unnecessary external access to systems through OS and service provider firewalls, and limiting communication between internal systems only to the source/destination ports and protocols required for functionality.
- Blocking any access to the system from known problematic networks.
- Leveraging an intrusion detection system to detect and deny access to active bad actors.
- Using updated versions—from trusted sources—of the source code and binaries downloaded to our systems.
- Requiring encrypted connections to all public facing elements, deprecating insecure ciphers, and using secure connections where possible—even on private networks—for communication between internal systems.

### Certificates

We use [Let's Encrypt](https://letsencrypt.org/) as our primary certificate authority.
