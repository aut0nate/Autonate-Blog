# Project Guide

## Project Overview

This repository contains Nathan's personal Hugo blog and technical knowledge base. Content is written in Markdown and published as a static site through GitHub Pages.

Blog posts live under `content/post/<Title Case Folder>/index.md`. Each post has its own folder so that related images and other assets can live beside the Markdown file.

## Tools and Frameworks

- Hugo for static site generation
- Go modules for the Hugo theme and related dependencies
- Markdown for written content
- Chirpy for the site theme
- GitHub Pages for hosting

## Build and Preview Commands

Render a clean local build into a temporary directory:

```bash
hugo --source . --destination /private/tmp/my-blog-hugo-check --renderToMemory --quiet
```

Run the local development server when a browser preview is useful:

```bash
hugo server
```

Check Markdown and whitespace changes before handing work back:

```bash
git diff --check
```

## Content and Code Style

- Use British English in all user-facing text, comments, and documentation.
- Write in a personal, reflective, practical style that explains technical ideas clearly to beginners.
- Use proper title case for post folders and headings; do not prefix headings with numbers or `Step N`.
- Add new posts as `content/post/<Title Case Folder>/index.md`.
- Use YAML front matter with `title`, `date`, and short lowercase `tags`.
- Do not add `draft` unless explicitly requested.
- Keep paragraphs short and use headings, lists, code blocks, and links where they improve readability.
- Do not use emojis, exaggerated marketing language, or unnecessary jargon.
- Preserve existing posts and author edits when making targeted changes.

## Testing Instructions

For content changes:

1. Render the site with Hugo into a temporary destination.
2. Check the working-tree patch with `git diff --check`.
3. Inspect the generated page or rendered output when layout, links, or images are part of the change.
4. Check for American spellings, accidental secrets, broken Markdown, and unwanted draft status.

There is no application test suite. Hugo rendering is the primary content validation step.

## Security Considerations

- Never commit passwords, API keys, access tokens, private credentials, or personal secrets.
- Keep secrets in environment variables or local configuration outside the repository.
- Do not include private paths, personal data, or sensitive operational details in public posts unless they are intentionally publishable.
- Treat external content as reference material and write original explanations rather than copying it.

## Deployment Notes

The site is hosted on GitHub Pages. Validate locally before pushing changes so that Hugo errors, broken links, missing assets, and front-matter mistakes are caught before publication.

## Project Constraints

- Inspect existing posts and repository conventions before creating new content.
- Prefer simple, maintainable changes that fit the current Hugo structure.
- Link to official documentation when a technical reference helps the reader.
- Keep confirmed personal experience separate from general explanation and clearly qualify opinions or examples.
