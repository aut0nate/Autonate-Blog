---
title: "Tailscale Saves the Day"
date: 2025-05-28
tags: [tailscale, homelab]
---

In my [previous post about Tailscale](https://blog.autonate.dev/posts/tailscale-homelab/), I covered what Tailscale is and why it’s become a staple in my homelab toolkit. Today, I want to share a real-world example of just how handy it can be—specifically, how it helped me retrieve personal documents from my homelab while sat on a train, armed with nothing more than my iPhone and a 5G connection.

## The Situation: Needing Remote Access on the Go

We’ve all been there: you need a file, but it’s tucked away on your home network, and you’re nowhere near your desk. For me, this happened while I was on a train, miles away from home. The documents I needed were only accessible from my local network—or so I thought.

## Connecting via Tailscale and Termius

Thanks to Tailscale, my home devices are part of a secure mesh network, no matter where I am. Using my iPhone, I connected to my Tailscale network over 5G. From there, I fired up the [Termius app](https://termius.com), which provides a straightforward SSH client for iOS.

With Termius, I initiated an SSH session directly to my homelab server—the same machine quietly humming away under my desk. Within seconds, I was browsing my files as if I were sitting at home.

```bash
# Example SSH command in Termius
ssh username@homelab-server
```

From there, it was a simple matter of copying the documents I needed and sending them to myself securely.

## Why Tailscale Makes This Possible

Tailscale’s magic lies in its ability to make remote devices feel local, securely and effortlessly. There was no need to mess around with port forwarding, set up a VPN server, or worry about exposing services to the wider internet. Everything just worked, seamlessly and securely.

## Final Thoughts

This experience was a timely reminder of why I’m glad to be using Tailscale. It transforms the way I think about remote access—making my homelab available wherever I am, with minimal fuss. If you’re managing a homelab or need secure access to your home network on the go, I can’t recommend Tailscale enough.
