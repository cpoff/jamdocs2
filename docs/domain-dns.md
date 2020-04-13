---
title: Domain/DNS
date: 2020-04-11
slug: domain-dns

---
Here's where we'll lay out the domain/subdomain/subdirectory structures. With a multisite WordPress network, it might get a little complex.

## PAG/RTA Host

Since we're running WordPress as multisite, we can have several sub-sites running on a single WP installation. So we'll create a single PAG/RTA Host as the 'network' parent, then put RTA, RTA Next, PAG, and any subsequent sites as children.

Plug-ins, themes, and other admin features are added at the network level and activated/managed at the site level.

Multisite requires child sites be added as either subdomain or subdirectories. So Jeff will build the domain structure and domain map for redirects.