---
layout: topic
title: Migrating Domains to Cloudflare
weight: 3
---
## Concepts

### DNS
DNS or Domain Name System is how domain names get translated into IP addresses. 
When you buy a domain, you buy the ability to set those IP addresses.
Squarespace, GoDaddy, and Cloudflare are all examples of registrars.
For a technical deep dive, see [this article from Cloudflare](https://www.cloudflare.com/learning/dns/what-is-dns/).

### Registrar
A registrar is who you buy a domain from.
Some examples of this are Squarespace, GoDaddy, and Cloudflare.
They are responsible for your billing.

### Cloudflare Management
Cloudflare supports two approaches to domain configuration: **managed** and **owned**.
Under the *managed* approach, Cloudflare handles all of your DNS records while your domain registration remains with your existing registrar. 
If you purchased your domain through a different registrar, such as Squarespace, you would continue to pay that registrar for the domain itself while managing your DNS records, adding, and updating them as needed, within Cloudflare.
Under the *owned* approach, you migrate your domain registration to Cloudflare directly. 
In this configuration, Cloudflare serves as both your DNS provider and your registrar, meaning Cloudflare handles domain registration and billing.
This tutorial covers how to configure both approaches.


## Management and Migration

### Managing Your Domain with Cloudflare
This process is straightforward and can be found using [Cloudflare's docs](https://developers.cloudflare.com/dns/zone-setups/full-setup/setup/).

### Migrating Your Domain to Cloudflare
This process is documented on [Cloudflare's docs](https://developers.cloudflare.com/registrar/get-started/transfer-domain-to-cloudflare/).
However, it does not cover how you set this up for popular registrars. See below for how to handle this.
Use the following to migrate from common registrars:
- [Squarespace](https://support.squarespace.com/hc/en-us/articles/205812338-Transferring-a-domain-away-from-Squarespace)
- [GoDaddy](https://www.godaddy.com/en/help/transfer-my-domain-away-from-godaddy-3560)

This process can take days to complete but is largely hands off. 
If you have to migrate multiple domains, my advice is to do them one at a time rather than all at once.
Additionally, migrating all of your domains for an organization into a single Cloudflare organizational account is preferable.
