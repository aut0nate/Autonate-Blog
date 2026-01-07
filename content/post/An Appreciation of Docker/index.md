---
title: "An Appreciation of Docker"
tags: [docker, containers, devops, cli]
date: 2024-08-25
---

Back in **2020** I finally set aside time to learn about containerisation. [Docker](https://www.docker.com/get-started/) had been on my radar for a while, but I kept putting it off, convinced it was strictly developer territory. Determined to challenge that belief, I spun up a modest Virtual Private Server (VPS) with [Contabo](https://contabo.com/en/) and embarked on a learn‑by‑doing journey, self‑hosting a handful of services. The concepts felt tricky at first, but I persevered, and as I grew comfortable with the Docker CLI, the hype began to make sense.

## What Is Docker?

Docker is a virtualisation platform that allows you to **package, distribute and run applications in lightweight, portable containers**. Each container is an isolated environment holding everything the application needs—code, libraries and other dependencies. Docker eliminates the *“it works on my machine”* problem and ensures that software behaves consistently across environments.

## Containers vs Virtual Machines

|                        | **Containers**                                | **Virtual Machines (VMs)**                              |
| ---------------------- | --------------------------------------------- | ------------------------------------------------------- |
| **Abstraction Level**  | Operating‑system level; share the host kernel | Hardware level; virtualise the entire machine           |
| **Isolation**          | Process isolation (namespaces & cgroups)      | Strong isolation with a full guest OS                   |
| **Resource Footprint** | Lightweight; start in seconds                 | Heavier; require more CPU, RAM and storage              |
| **Use‑Cases**          | Cloud‑native, micro‑services, CI/CD pipelines | Legacy workloads, monoliths, strong security boundaries |
| **Boot Time**          | Near‑instant                                  | Tens of seconds to minutes                              |

The key takeaway is that containers virtualise the **operating system**, while VMs virtualise the **hardware**. That makes containers faster to start and more resource‑efficient, whereas VMs offer deeper isolation at the cost of additional overhead.

## Breaking the Myth – Docker Isn’t Just for Developers

As I soon discovered, you don’t need deep programming knowledge to benefit from Docker. If you can follow a recipe and run a few terminal commands, you can run containers. Understanding *how* Docker works does deepen your appreciation, but you don’t have to be a developer to use it effectively. Once that realisation clicked, I started deploying more services and, as a side benefit, became far more comfortable at the command line. For those who prefer a GUI, Docker Desktop offers an excellent alternative.

## The Learning Curve: YouTube, Blog Posts & KodeKloud

My journey was fuelled by countless blog posts and YouTube tutorials. Concepts such as images, containers, volumes and networks felt abstract at first, but hands‑on practice soon turned those abstractions into muscle memory. As the saying goes, practice doesn’t make perfect—it makes permanent.

I first discovered KodeKloud through their excellent two‑hour Docker crash course on YouTube. That single video became my launch‑pad and ultimately convinced me to subscribe to their [Standard Plan](https://learn.kodekloud.com/pricing). The quality of the lessons and interactive labs has further enhanced my knowledge.

If you’re just starting out, here are a few beginner‑friendly videos I still recommend:

[KodeKloud: Learn Docker in 2 hours](https://www.youtube.com/watch?v=zJ6WbK9zFpI)

[TechWorld with Nana: Docker Crash Course for Absolute Beginners](https://www.youtube.com/watch?v=pg19Z8LL06w&t=2384s)

[mCoding: Docker Tutorial for Beginners](https://www.youtube.com/watch?v=b0HMimUb4f0)

[Fireship: 100+ Docker Concepts you Need to Know](https://www.youtube.com/watch?v=rIrNIzy6U_g&t=245s)

## Dockerfiles, Images and Containers – A Quick Tour

A **Dockerfile** is a plain‑text blueprint that lists every command required to assemble an image—think of it as a recipe. A typical Dockerfile begins with a *base image* and layers additional instructions on top:

```Dockerfile
# Dockerfile example
FROM ubuntu:18.04           # Base image
RUN apt-get update && \
    apt-get install -y nginx  # Install software
COPY index.html /var/www/html # Copy project files
CMD ["nginx", "-g", "daemon off;"]  # Default command
```

### Key Components of a Dockerfile

* **Base Image (`FROM`)** – The starting point of your build, e.g. `FROM node:20-alpine`.
* **Instructions** – Commands such as `RUN`, `COPY`, `ENTRYPOINT` and `CMD` that install software, copy files or configure how the container starts.

A **Docker image** is the packaged result of executing a Dockerfile. Images are:

* **Layered** – Each instruction in the Dockerfile adds a new immutable layer, cached for faster rebuilds.
* **Immutable** – To make changes you edit the Dockerfile and *rebuild*; the original image never mutates.
* **Lightweight** – Images do not contain a full OS, only the user‑space libraries needed for your application.

A **container** is a **running instance** of that image—your application brought to life in an isolated environment.

### How They Work Together

1. **Write a Dockerfile** – Describe your environment, dependencies and runtime behaviour.
2. **Build an image** – `docker build -t my‑app .` executes the Dockerfile and produces an image.
3. **Run a container** – `docker run -d --name my‑app my‑app` starts the container from the image.

The flow: **Dockerfile → Image → Container**.

## Useful Commands

Here are some beginner‑friendly Docker commands that you’ll use often. To explore the full range, just run `docker` at the command line.

```bash
# Check Docker version
docker --version

# List all running containers
docker ps

# List all containers (including stopped ones)
docker ps -a

# Pull an image from Docker Hub
docker pull ubuntu

# Run a container
docker run ubuntu

# Run a container interactively
docker run -it ubuntu bash

# Run a container in the background (detached mode)
docker run -d nginx

# Stop a running container
docker stop <container_id>

# Start a stopped container
docker start <container_id>

# Remove a container
docker rm <container_id>

# List all images
docker images

# Remove an image
docker rmi <image_id>

# Build an image from a Dockerfile
docker build -t my-app:1.0 .

# Run a container with port mapping
docker run -p 8080:80 nginx

# View container logs
docker logs <container_id>

# Execute a command in a running container
docker exec -it <container_id> bash
```

## Why I Appreciate Docker

1. **Consistency** – Containers behave identically on my VPS, my laptop and anywhere in between.
2. **Isolation** – Each service has its own sandbox, which is great for performance and security.
3. **Portability** – Moving to a new server is as easy as copying a compose file and running `docker compose up -d`.
4. **Community** – If you can imagine a service, there’s probably an official or community image ready to go on [Docker Hub](https://hub.docker.com/).

## Final Thoughts

I’m really pleased I invested the time to learn about containerisation; it has enhanced my tech skills and complimented my command‑line knowledge. Docker has helped me build a solid cloud lab which hosts a variety of services, and I’m constantly discovering and spinning up new ones. If you’re on the fence, thinking containerisation is only for hardcore developers, give it a try: start small and learn at your own pace. The payoff is well worth it, and it’s a brilliant tool to have in your toolbox.
