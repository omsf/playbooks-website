---
layout: topic
title: Migrating Domains to Cloudflare
weight: 3
---
## Concepts
Cloudflare allows for users to setup their domains in two different ways, managed and owned.
When a domain is managed by Cloudflare it means the control of all DNS records is being down by Cloudflare, but you still pay your registrar for your domain.
This means that if you buy your domain at something like Squarespace, you will pay them for the ownership of your domain, but update and add records in Cloudflare

However, if you can completely migrate your domain to be owned by Cloudflare.
This allows for Cloudflare to manage the domain but also they will be who you pay for registration.
This tutorial aims to explain how to do both of these.

## Managing your domain with Cloudflare
This process is straightforward and can be found using [Cloudflare's docs](https://developers.cloudflare.com/dns/zone-setups/full-setup/setup/).

## Migrating your domain to Cloudflare
This process is documented on [Cloudflare's docs](https://developers.cloudflare.com/registrar/get-started/transfer-domain-to-cloudflare/).
However it does not cover how you set this up for popular hosting services. See below for how to handle this.
Use the following to migrate from common providers:
- [Squarspace](https://support.squarespace.com/hc/en-us/articles/205812338-Transferring-a-domain-away-from-Squarespace)
- [GoDaddy](https://www.godaddy.com/en/help/transfer-my-domain-away-from-godaddy-3560)

This process can take days to complete but is largely hands off. If you have to migrate multiple domains, my advice is to do them one
at a time rather than all at once. Additionally, migrating all of your domains for an organization into a single Cloudflare organizational account is preferable.
