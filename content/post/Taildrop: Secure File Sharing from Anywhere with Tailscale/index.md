---
title: "Taildrop: Secure File Sharing from Anywhere with Tailscale"
date: 2025-02-02
tags: [tailscale, homelab, networking]
---

Tailscale has transformed the way I manage and access my homelab, providing seamless, secure connectivity between all my devices—wherever I am. In my previous post, ["How Tailscale Transformed Secure Access to My Homelab"](https://blog.autonate.dev/posts/tailscale-homelab/), I shared how Tailscale has become an essential part of my daily workflow, enabling remote access to servers, VMs, and services without exposing anything to the public internet. Today, I want to highlight another standout feature: Taildrop.

## What is Taildrop?

Taildrop is a built-in feature of Tailscale that allows you to securely send files between any devices connected to your Tailnet. Taildrop transfers files over encrypted peer-to-peer connections, using the fastest available path. This makes it a great solution for sending sensitive or large files without third-party servers in the middle.

Taildrop works by leveraging the encrypted tunnels that Tailscale creates between your devices, ensuring that your files are never exposed to the public internet. Whether you’re sending photos from your phone to your desktop, or sharing log files between devices, Taildrop makes it as easy and secure.

## Why Use Taildrop?

- **Security:** All file transfers are encrypted and happen directly between your devices over Tailscale’s secure network.
- **Simplicity:** No need to set up additional software or services. Taildrop is built right into Tailscale.
- **Flexibility:** Works across all major platforms—Windows, macOS, Linux, iOS, and Android.
- **Speed:** File transfers are sent peer-to-peer using the fastest route, maximising transfer speeds.

## How I Use Tailscale (and Taildrop) Every Day

Tailscale is at the heart of my homelab and I use it to:

- **Remotely access my homelab servers and VMs** from anywhere, as if I’m on the same local network.
- **Securely share files between devices** using Taildrop—whether it’s a photo or a log file.

Taildrop, in particular, has saved me countless hours. Instead of using scripts to transfer files between devices, I simply use Taildrop to transfer files quickly and securely. It’s especially handy when I’m troubleshooting issues on remote machines and I want to ensure that files are available on other devices within my Tailnet.

## How Taildrop Works

To use Taildrop, you simply need to have Tailscale installed on both devices. From there, file sharing is straightforward:

- **On desktop platforms**, you can use the built-in sharing capabilities within the OS (usually right clicking a file) to share any file with Taildrop.

- **On mobile devices**, you can use the built-in iOS or Android sharing capabilities to share any file with Taildrop.

For detailed instructions and examples, check out the official [Taildrop documentation](https://tailscale.com/kb/1106/taildrop).

## Example: Sending a File with Taildrop

Here’s a quick example of how you might send a file between devices in your tailnet. In this example, I sent a pdf from macOS to Windows 11:

1. I located the pdf which I wanted to share and right clicked on the file. From the list of options I click **Share** and selected **Tailscale**:

   ![Taildrop macOS 1](./Tailscale%20macOS%201.png)

2. I was presented with a list of devices in my Tailnet, I cicked **Send** on my **arkham-win11** device:

   ![Taildrop macOS 2](./Tailscale%20macOS%202.png)

3. Just like that, the pdf was available to me on my Windows 11 device:

   ![Taildrop macOS 2](./Taildrop%20Win11.png)

## Final Thoughts

Taildrop is a powerful, yet simple tool that exemplifies the best of what Tailscale offers: secure, private, and effortless connectivity between all your devices. As someone who uses Tailscale every day, I can’t recommend Taildrop enough for anyone who needs to share files securely—whether you’re managing a homelab, collaborating with a team, or just moving files between your own devices.

If you haven’t tried Tailscale or Taildrop yet, I highly encourage you to give them a go. For more about how I use Tailscale in my homelab, check out my previous post: [How Tailscale Transformed Secure Access to My Homelab](https://blog.autonate.dev/posts/tailscale-homelab/).
