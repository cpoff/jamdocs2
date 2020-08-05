---
title: Domain/DNS
date: 2020-04-11
slug: domain-dns
---

## PAG/RTA Host

Since we're running WordPress as multisite, we can have several sub-sites running on a single WP installation. We created a single PAG/RTA Host as the 'network' parent, then put RTA, RTA Next, PAG, and any subsequent sites as children.

The [network home](http://rtaproduction.kinsta.cloud/wp-admin/network/) appears as a standalone site in the WP interface but has no Post/Pages capability. Plug-ins, themes, and other admin features are added/managed at the network level and activated/utilized at the site level.

## Update a child site to the PAG/RTA network

On GoDaddy, create A records in the DNS pointing to the site IP address. Jeff has sole access to GoDaddy.

When logged in as a network/site admin in WordPress, update the Site Address URL\* to match the new A record:

- [RTA Main](http://rtaproduction.kinsta.cloud/wp-admin/network/site-info.php?id=4)
- [RTA Next](http://rtaproduction.kinsta.cloud/wp-admin/network/site-info.php?id=2)
- [PAG Main](http://rtaproduction.kinsta.cloud/wp-admin/network/site-info.php?id=3)

\*This should be the final URL you want to appear in the location bar.

[Kinsta domain/DNS listing](https://my.kinsta.com/sites/domains/d2ae23d3-d63a-43ee-8216-76ce7939e45f/live?idCompany=7c2b91cf-4854-46b5-b063-03a9ae38f98c) is auto-generated once you fill in the domains in the previous step.
