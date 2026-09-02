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

The general process for handling a full migration as follows:
1. Back up your records from your current registrar
2. Change your nameservers to Cloudflare (congrats your domain is now managed by Cloudflare)
3. Transfer your domain registration and pay for domain registration cost
The documentation for this process is found [here](https://developers.cloudflare.com/registrar/get-started/transfer-domain-to-cloudflare/)

### 1. Back up Your Records
Some providers provide a way to download your records as a file for you to import.
However, this is not always the case, a screenshot can be helpful here.

### 2. Change Your Nameservers to Cloudflare
Use the following to migrate your nameservers [https://developers.cloudflare.com/dns/zone-setups/full-setup/setup/](https://developers.cloudflare.com/dns/zone-setups/full-setup/setup/).

### 3. Transfer Your Domain Registration
This process is captured [here](https://developers.cloudflare.com/registrar/get-started/transfer-domain-to-cloudflare/#2-transfer-your-registration). 
However, it does not include how to handle a specific registrar.
Here are a few examples:
- [Squarspace](https://support.squarespace.com/hc/en-us/articles/205812338-Transferring-a-domain-away-from-Squarespace)
- [GoDaddy](https://www.godaddy.com/en/help/transfer-my-domain-away-from-godaddy-3560)

This process can take days to complete but is largely hands off and will not create downtime because your domain is already managed by Cloudflare. 
If you have to migrate multiple domains, my advice is to do them one at a time rather than all at once.
Additionally, migrating all of your domains for an organization into a single Cloudflare organizational account is preferable.
