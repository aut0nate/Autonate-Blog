---
title: Fixing Bugs from an iPhone with Codex
date: 2026-05-09
tags: [ai, llm, chatgpt, codex, github, automation, cicd, prompt engineering, agentic-ai]
---

I was casually browsing the gallery on my [AI Art Hub app](https://images.autonate.dev), on my iPhone when I noticed something slightly off. Whenever I tapped on an image to enlarge it, the image wasn’t properly centred on screen.

It wasn’t a critical issue. Just one of those small UI details that immediately stands out once you notice it.

Normally, this would have meant waiting until I was back at my desk with my Mac nearby. Instead, I decided to try fixing it entirely from my phone using Codex inside the ChatGPT iPhone app.

## The Workflow

I opened ChatGPT on my iPhone, launched Codex, and described the issue in plain English, along with some screenshots of the issue:

> Upon tapping an image on mobile, centralise the image to make it the focal point in the centre of the viewport. Add a subtle transition as the prompt metadata panel fades out of view and the image is pushed to the centre of the screen. Remove any drop shadow effects behind the image.

![Codex-Prompt](./Codex-Prompt)

That was essentially it.

Codex then:

- Spun up a development container automatically
- Downloaded the repository
- Analysed the existing codebase
- Made the required frontend changes
- Ran its validation and test steps
- Presented the completed diff back to me

All from my phone.

No SSH sessions.
No VS Code.
No terminal.
No laptop.

What made this feel different is that I wasn’t remotely controlling another machine or manually patching things together. The entire development workflow existed around the request itself.

Just natural language instructions from an iPhone.

![Codex-Action](./Codex-Action)

## Reviewing the Changes

Codex didn’t just blindly edit files and stop there. I was able to:

- Review the exact code changes
- Check the modified files
- Verify the logic made sense
- Create a pull request directly from the generated changes

Once I was happy, I merged the PR into my main branch.

![Codex-Complete](./Codex-Complete)

![GitHub](./GitHub)

## CI/CD Took Care of the Rest

From there, the rest of the workflow was fully automated.

Merging the PR triggered my GitHub Actions pipelines which:

- Built the updated application
- Ran the deployment workflow
- Pushed the changes live automatically

Within a few minutes, the fix was deployed.

I reopened the app on my iPhone, tapped an image again, and the issue was gone.

Codex had handled it perfectly.

The images now displayed perfectly centred exactly as I wanted.

![The-Fix](./The-Fix)

## Why This Felt Different

The really interesting part wasn’t the UI fix itself.

It was the fact that I was able to go from:

- discovering an issue
- to implementing a fix
- to reviewing a PR
- to deploying to production

…entirely from a mobile phone while away from my computer.

That changes the friction involved in maintaining side projects.

Small fixes no longer need to wait until you are back at your desk. If you spot something while using your own app in the real world, you can often resolve it immediately.

## The Bigger Shift

What struck me afterwards is that the UI fix itself almost became secondary to the workflow.

AI-assisted development tools are often discussed in terms of generating large amounts of code, but I think workflows like this are where they become genuinely transformative.

Codex effectively acted as:

- a development environment
- a coding assistant
- a test runner
- and an implementation agent

while still keeping me in control of reviewing and approving the final changes.

The combination of:

- natural language instructions
- ephemeral cloud development environments
- GitHub integration
- and automated CI/CD pipelines

creates a workflow that feels surprisingly seamless.

## Final Thoughts

I came away from this genuinely impressed.

Being able to make changes to a real application from an iPhone felt slightly surreal, but also incredibly practical.

For quick fixes, small UI tweaks, and lightweight maintenance tasks, this is an extremely useful workflow when you are away from your main machine.

And honestly, the fact that the entire fix started because I casually noticed a misaligned image while browsing on my iPhone makes it even better.