---
title: "My Homelab Journey...So Far"
date: 2023-08-17
tags: [homelab]
---

Diving into the world of Linux naturally led me to discover the vibrant homelab community. What began as casual curiosity soon became a genuine fascination, fuelled by countless YouTube videos showcasing everything from compact, single-board computers to sprawling, business-grade server racks. The creativity and technical depth on display resonated with my own desire to experiment and learn by doing. But as I watched, a set of questions began to form: Did I actually need a homelab? What would I use it for? Did it require a significant investment in hardware? And, crucially, how should I even begin?

## Finding My Purpose

Before rushing out to buy new kit, I took a step back to consider my goals. My main device was already a capable M1 Pro MacBook Pro (2021), and I had a cloud-based Ubuntu VPS with Contabo for remote Linux and Docker tinkering. Parallels on macOS let me run Fedora and Ubuntu desktop VMs, scratching the distro-hopping itch. Still, I felt the urge to build something physical, something I could break and fix in my own space.

Reflecting on what I wanted from a homelab, my aims became clear:

- Sharpen my Linux skills
- Improve my networking know-how
- Explore new apps and services
- Boost my overall technical ability through hands-on practice

## Starting With What I Had

The temptation to splurge on shiny new hardware was strong, but ultimately I chose to start with what I already owned: a trusty HP small form factor PC (Intel Core i5-7500 @ 3.40GHz, 8GB DDR4 RAM, 128GB SSD). This machine had been gathering dust under my desk for years, only seeing occasional use for Windows tasks. To give it a new lease of life, I upgraded the RAM to 32GB and swapped in a 500GB SSD.

For the hypervisor, I opted for Proxmox VE—a powerful, open-source platform that’s perhaps a bit overkill for a single-node setup, but perfect for learning and future expansion. The [Learn Linux TV Proxmox course](https://www.youtube.com/playlist?list=PLT98CRl2KxKHnlbYhtABg6cF50bYa8Ulo) proved invaluable for getting up to speed with installation and configuration.

## My Current Homelab Setup

Compared to the racks and clusters you’ll see online, my setup is modest, but it’s more than enough for my needs right now. Here’s what I’m running:

**Virtual Machines:**

- 2 x Ubuntu Server
- 1 x Fedora Server
- 1 x Windows 11

**Containers:**

- [Nginx Proxy Manager](https://nginxproxymanager.com)
- [Portainer](https://www.portainer.io)
- [Authentik](https://goauthentik.io)
- [Glance](https://github.com/glanceapp/glance)
- [Miniflux](https://miniflux.app)
- [Change Detection](https://changedetection.io)
- [Up Vote RSS](https://github.com/johnwarne/upvote-rss)
- [IT Tools](https://github.com/CorentinTh/it-tools)

Proxmox makes it easy to manage both VMs and containers, and I’m already planning to experiment with clustering in the future.

## Lessons Learned and Next Steps

The biggest lesson so far? Just get started. There’s no need for enterprise hardware or a sprawling rack to begin learning and experimenting. My homelab has already helped me discover new services, reinforce my Linux skills, and gain confidence with networking and self-hosted apps. As my needs evolve, I can always add more resources or try new things—homelabs are, by nature, endlessly adaptable.

## Recommended Resources

If you’re looking to expand your knowledge or stay up to date with the homelab and self-hosting world, here are some resources I’ve found especially helpful:

**Newsletter:**

- [Selfh.st](https://selfh.st) – A great newsletter for discovering the latest news, tools, and updates in the self-hosting community.

**YouTube Channels:**

- [Jim’s Garage](https://youtube.com/@jims-garage?si=RKvNDxvR4T-GvEoE) – Practical homelab builds and deep dives.
- [Christian Lempa](https://youtube.com/@christianlempa?si=enm70wFPAh0qDGLE) – Tutorials and walkthroughs for self-hosting and open-source projects.
- [Servers at Home](https://youtube.com/@serversathome?si=N1Bxmbxau8t94fy7) – Focused on building and running servers at home.
- [Techno Tim](https://youtube.com/@technotim?si=MI9C-eWSD2GZJuYg) – In-depth guides on homelab setups, networking, and automation.
- [DB Tech](https://youtube.com/@dbtechyt?si=aAFrkHDELZk3wEuu) – Easy-to-follow tutorials on Docker, containers, and self-hosted applications.
- [TechHut](https://youtube.com/@techhut?si=BTzsFuSeNqMoE_gq) – Covers Linux, open-source software, and homelab projects.

## Final Thoughts

Building a homelab doesn’t require a massive budget or a dedicated server room, if you have the resources to start with that then by all means go for it. Otherwise, start with what you have, define your goals, and let curiosity lead the way. My journey is only just beginning, but the hands-on experience has already proven invaluable—and, most importantly, it’s been a lot of fun. If you’re on the fence about starting your own homelab, my advice is simple: take the plunge and see where it leads.
