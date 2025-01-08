---
date: 2025-01-08 23:46:24
layout: post
title: "Add local DNS to system hosts file"
subtitle:
description: Access local sites even when the vpn is active.
image: https://picsum.photos/1200/600 
optimized_image:
category: scraper
tags: vpn scraper hosts dns pihole
author:
paginate: false
---

# Add local DNS to system hosts file

We use pihole to act as our DNS server on our LAN and traefik to route requests to applications. This creates a problem when we want to access local sites when a VPN is active.

To fix this problem we can add our sites to the `/etc/hosts` file on mac and linux.

```bash
192.168.1.xxx site.mysite.internal
```

> This must be done for all subdomains you want to resolve

**Mac**
```bash
sudo dscacheutil -flushcache
```

**Ubuntu** will pick up these changes without needing to manually refresh anything.
