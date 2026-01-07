---
title: "Moving from Portainer to Dockge"
date: 2025-11-16
tags: [homelab, docker, containers]
---

I first dived into containerisation around 2020, eventually settling on a Virtual Private Server (VPS) setup where the focus shifted from managing hardware to mastering software and services. For a long time, the backbone of that software setup was Portainer. Portainer served as the graphical interface for managing the 20+ services I run in stacks on my VPS, handling everything from my reverse proxy to monitoring tools.

Portainer is a robust GUI for managing containers and stacks, and I want to make it clear that my migration wasn't driven by any failing on its part; it’s an excellent piece of kit. However, as my homelab evolved, I started looking for something that offered an even **simpler and easier management experience**. I wanted a dedicated tool that stripped back the complexity, allowing me to focus entirely on tweaking my Docker Compose files and stacks. That search led me straight to [**Dockge**.](https://dockge.kuma.pet/)

## Discovering Dockge

The appeal of Dockge was immediate. It met my need for a lighter touch in stack management and quickly proved to be a powerful tool with some genuinely useful features, such as:

- **Comprehensive Stack Management:** Dockge provides tools to manage your `compose.yaml` files, allowing you to create, edit, start, stop, restart, delete, and update Docker images.

- **Interactive Editor and Terminal:** It features an interactive editor for `docker-compose.yaml` files and includes an interactive web terminal for stack interaction.

- **Reactive and Real-time:** The interface is reactive, meaning progress (such as pulling images or deploying stacks) and terminal output are displayed in real-time.

- **Multiple Agent Support:** Dockge supports multiple agents, enabling you to manage stacks located on different Docker hosts within a single unified interface.

Moving between Docker management tools is often straightforward because of the fundamental concept of container portability. Whether you're moving to a new server or switching GUIs, the ability to copy a compose file and run `docker compose up -d` makes transitions far smoother. Dockge allows me to manage the stacks containing my various services like my automation hub, n8n, and my RSS reader, Miniflux - with the simplicity I was seeking.

## A Familiar Face for Homelabbers

If you, use [**Uptime Kuma**](https://github.com/louislam/uptime-kuma) to monitor the status of your services, you will instantly feel at home using Dockge because they are both created by the same developer, [Louis Lam](https://github.com/louislam?tab=repositories). The clean, intuitive user interface shares the same aesthetic sensibilities as Uptime Kuma, making the learning curve negligible

Dockge focuses on the core task of managing Docker Compose files, allowing you to edit, deploy, and monitor your stacks with minimal fuss. For those who appreciate simplicity and efficiency in their homelab, this tool is well worth exploring, and thank you Louis for developing and maintaining these excellent tools!

## Getting Started

If you’re running services in a Docker environment and are looking for a streamlined, clean interface to manage your stacks, I highly recommend checking out Dockge.

Feel free to use the following `docker-compose.yaml` file and amend the relevant values as needed:

```yaml
services:
  dockge:
    image: louislam/dockge:latest
    container_name: dockge
    restart: unless-stopped
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - ./data:/app/data
      - /opt/stacks:/opt/stacks
    networks:
      - mgmt-net
    ports:
      - "5001:5001"
    security_opt:
      - no-new-privileges:true
    logging:
      options:
        max-size: "10m"
        max-file: "3"
    environment:
      DOCKGE_STACKS_DIR: /opt/stacks
      TZ: Europe/London
      DOCKGE_ENABLE_CONSOLE: "true"
    labels:
      com.centurylinklabs.watchtower.enable: "false"

networks:
  mgmt-net:
    external: true
```

## Final Thoughts

Making the switch from Portainer to Dockge was a decision rooted in seeking simplification, which aligns well with my current homelab philosophy of focusing on the software rather than getting overwhelmed by the architecture. While Portainer is undeniably feature-rich, Dockge provides the focused, easy-to-manage experience I was looking for.

It’s a perfect reminder that the beauty of homelabs lies in their **flexibility** and you should always choose the tools that work best for *you*, whether that means running a complex setup or opting for elegant simplicity. If you're managing containers and value an easy-to-use interface, give Dockge a look and see how it fits into your workflow.
