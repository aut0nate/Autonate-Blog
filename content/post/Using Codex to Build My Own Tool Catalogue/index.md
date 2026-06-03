---
title: "Using Codex to Build My Own Tool Catalogue"
date: 2026-05-15
tags: [ai, llm, chatgpt, codex, productivity, github, cicd, docker, agentic-ai]
---

I’ve always liked finding useful apps, command line tools, and resources. Some are things I use every day, while others are more situational, but still worth remembering and sharing when the right moment comes up.

For a while, I kept that list in [Craft](https://www.craft.do/) as a simple table. That worked well enough at the start. Craft is still where a lot of my knowledge lives, and it is excellent for notes, documents, and personal knowledge management.

But over time I realised this particular idea needed something different.

The list was becoming less like a private note and more like a small public catalogue. I wanted people to be able to browse it, search it, filter it, and use it without needing access to my personal workspace. That is what led me to build [The Collection](https://github.com/aut0nate/The-Collection), a public catalogue of apps, command line tools, and resources I use, trust, and recommend.

## Why I Wanted to Build It

The original Craft table was useful because it gave me one place to capture things. If I found an interesting tool, I could add it quickly and move on.

The problem was that a table inside a notes app has limits.

It is fine for personal reference, but it is not ideal when you want to present something publicly. It does not give you a proper browsing experience, it is harder to shape around search and filtering, and it is not really designed to become a small product in its own right.

What I wanted was simple:

- A public catalogue of useful tools and resources
- Search across names, descriptions, tags, platforms, and categories
- Filters for platforms and categories
- Tool cards that link directly to the relevant website or GitHub repository
- An admin area where I can add and manage entries myself
- Draft and published states, so unfinished entries do not appear publicly

It did not need to be complicated. It just needed to be more intentional than a table in my notes.

## What The Collection Does

The Collection is a public interface for tools I recommend.

It includes a homepage where published tools can be searched and filtered. Each tool belongs to a category, can have tags, and can be marked for one or more platforms such as macOS, Linux, Windows, iOS, Android, or Web.

The admin area lets me manage the catalogue without editing data by hand. I can add tools, save them as drafts, publish them when they are ready, edit existing entries, and upload or link logos.

That separation matters. Public visitors only see published tools, while the admin side gives me a controlled place to keep building the catalogue over time.

For me, that is the difference between a static list and something I can keep maintaining properly.

## How Codex Helped Shape the Project

This is another project where Codex made the idea feel much more achievable.

I did not start with a fully formed technical plan. I started with the problem:

> "I want a centralised place to share useful apps, tools, and resources, with a public catalogue and a private admin area."

From there, Codex helped turn the idea into a more structured project:

- What pages the app needed
- How the public and admin areas should be separated
- What the database model should look like
- How drafts and published tools should behave
- What environment variables were needed
- How authentication should work for a single owner
- How to package the app with Docker
- What commands should be documented for future work

The useful part was not just code generation. It was the planning and the iteration.

I could describe the outcome I wanted in plain language, review the suggested approach, and then work through the implementation step by step. That makes a big difference when you are not approaching the project as a full-time developer.

## Building and Testing Locally First

One pattern I keep coming back to is building and testing locally before thinking too much about deployment.

I do not want to make a change, push it to GitHub, and only then find out that something obvious is broken on the server. That is stressful, and it makes troubleshooting harder because you are dealing with the application, the deployment process, and the VPS environment all at once.

For The Collection, I use Codex to help make changes, then I test the application locally first. Once the app behaves as expected, I test it through Docker as well. That gives me more confidence that the same containerised version of the app will behave properly when it runs on my VPS.

That local Docker step is important to me. It means I am not just checking that the app works in a development environment. I am checking something much closer to how it will actually run in production.

The rough flow is:

- Work with Codex on the change
- Test the application locally
- Run it locally with Docker
- Check the public catalogue and admin workflow
- Push the finished change to GitHub
- Let GitHub Actions build and deploy it to the VPS

This keeps the process controlled. Codex helps me build and refine the app, Docker helps me test it in a realistic way, and GitHub Actions handles the deployment once the change is ready.

## Treating the Admin Area Carefully

Because The Collection has a private admin area, I wanted the security basics to be taken seriously from the beginning.

The app is owner-only rather than a multi-user platform. Authentication is backed by environment variables, with a bcrypt password hash rather than a plain password. Sessions use signed HTTP-only cookies, and the login flow includes throttling after repeated failed attempts.

That does not make the app magically perfect, but it does mean the obvious mistakes are avoided:

- No plain passwords in the repository
- No committed `.env` file
- No public access to draft tools
- No admin controls mixed into the public browsing experience
- Production secrets kept outside the codebase

These details are easy to overlook when building a small personal tool, but they are exactly the kind of thing Codex is useful for. It can keep asking the boring but important questions.

## Why This Is Better Than My Original Table

The Craft table was a good starting point because it helped me prove the idea.

But The Collection is better suited to what I actually want this to become.

It gives the list a proper home. It makes browsing easier. It gives me an admin workflow. It keeps unpublished entries private. It also gives me a codebase I can keep extending as new ideas come up.

That last point is important. I do not see this as finished. I see it as a foundation.

I will keep adding tools as I find useful and interesting things. Over the coming months, I also want to expand the app based on a few ideas I have, especially around making the catalogue more useful as it grows.

## What I Learned

The biggest lesson from this project is that not every personal tool needs to start as software.

Sometimes the right first version is a note, a spreadsheet, a table, or a folder full of links. That gives you a low-friction way to understand the shape of the problem.

But if the idea keeps growing, it might need a more dedicated home.

That is what happened here. Craft helped me collect the information, but Codex helped me turn the idea into an application with structure, search, filtering, admin controls, Docker packaging, and a GitHub repository.

The workflow felt natural:

1. Start with the simple version.
2. Notice where it starts to strain.
3. Define what the dedicated tool should do.
4. Use Codex to plan the build.
5. Test locally.
6. Package it properly.
7. Keep improving it over time.

That is becoming one of my favourite ways to build.

## Final Thoughts

The Collection started as a table in Craft, but it has become something more useful.

It is now a small public catalogue that I can manage myself, extend over time, and share with others. More importantly, it solves a real problem in my own workflow: keeping track of useful tools without burying them inside private notes.

Codex made the build approachable by helping me move from a rough idea to a working application in manageable steps. It did not remove the need to think clearly, test changes, or understand the basics, but it did make the whole process feel far more achievable.

For me, that is where these personal tools become interesting. You do not need to start with a big product idea. Sometimes a useful app begins as a table that outgrows its original home.
