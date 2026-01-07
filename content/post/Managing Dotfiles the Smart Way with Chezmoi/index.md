---
title: "Managing Dotfiles the Smart Way with Chezmoi"
date: 2025-03-29
tags: [cli, devops, cli]
---

Managing configuration files across multiple systems can quickly become a mess. From terminal preferences to shell settings, we all have a finely-tuned setup that we rely on day-to-day. But how do you keep those settings consistent across machines? And how do you avoid the chaos of losing them after a reinstall?

That’s where a tool like [Chezmoi](https://www.chezmoi.io/) comes in.

## What is Chezmoi?

Chezmoi is a powerful dotfile manager designed to track, version, and securely deploy your configuration files across multiple operating systems. It helps you manage configuration files such as `~/.zshrc`, `~/.gitconfig`, `~/.config/` and more — all with a simple Git workflow.

Unlike traditional symlink managers like GNU Stow, Chezmoi works by maintaining a source state in a Git repository, which it applies to your home directory. This means you can track your configuration files, safely test changes, and even add logic for different operating systems or hosts.

## Getting Started

To get started with Chezmoi, [install](https://www.chezmoi.io/install/) it using your preferred package manager.

On macOS:

```bash
brew install chezmoi
```

Ubuntu:

```bash
sudo apt install chezmoi
```

Windows:

```powershell
winget install twpayne.chezmoi
```

Then initialise your dotfiles repository:

```bash
chezmoi init --apply <repo>
```

This command clones your dotfiles repository (e.g. [https://github.com/aut0nate/dotfiles](https://github.com/aut0nate/dotfiles)) and immediately applies the configuration to your home directory. You can also start fresh by running:

```bash
chezmoi init
```

And then begin adding files:

```bash
chezmoi add ~/.zshrc
chezmoi add ~/.tmux.conf
```

## The Power of Templates

One of Chezmoi’s most useful features is its powerful templating engine. You can create conditional logic in your config files using [Go templating syntax](https://pkg.go.dev/text/template).

For example, let’s say you want a slightly different `.zshrc` on macOS vs Linux:

```zsh
{if eq .os "darwin"}
echo "Running on macOS"
{else if eq .os "linux"}
echo "Running on Linux"
{end}
```

You can also target OS-specific files by using suffixes in your source directory:

``` bash
~/.local/share/chezmoi/dot_zshrc.tmpl
~/.local/share/chezmoi/dot_gitconfig.tmpl
```

Or host-specific files:

``` bash
dot_gitconfig.tmpl
  └── applies to all systems

dot_gitconfig@workmachine.tmpl
  └── only applies when the hostname is 'workmachine'
```

This allows you to have one unified repository that works intelligently across every system you manage. Click the link to learn more about templates in [Chezmoi](https://www.chezmoi.io/user-guide/templating/).

## Why Backing Up Config Files Matters

Your configuration files represent hours — if not years — of customisation. Losing them can feel like losing a part of your workflow.

By using Chezmoi with Git, you:

- **Track every change** you make to your configs
- **Back up your entire setup** to GitHub or another Git provider
- **Easily restore your environment** after a system wipe or when setting up a new machine
- **Reduce time spent reconfiguring** new environments

Your dotfiles essentially become portable, versioned, and secure — which is especially useful if you work across macOS, Linux, or WSL environments like I do.

## My Dotfiles

If you're curious, you can check out [my dotfiles on GitHub](https://github.com/aut0nate/dotfiles). Feel free to use it for inspiration in your own configuration file management system.

## Final Thoughts

Chezmoi has quickly become one of my essential tools. It removes the friction of managing configuration files and I can rest easy knowing that everything is under source control and available to me whenever I need it. For example I recently received a new laptop at work, and with a simple `chezmoi init` my configuration files were available to me, without the hassle of setting everything up from scratch.

If you are looking for a tool to help you manage your configuration files across multiple platforms, Chezmoi is a great place to begin.
