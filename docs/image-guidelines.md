# Blog Image Guidelines

The blog automatically makes article images clickable. Selecting an image opens the original in Chirpy's lightbox, so screenshots do not need to fill the reading column to remain useful.

## Add a Single Image

Keep the image in the same folder as the post and use normal Markdown with useful alternative text:

```markdown
![The Codex project screen showing custom instructions](./Codex%20Project.png)
```

The image renderer reads the file dimensions automatically. Portrait images are centred and limited in height, while landscape images can use the available article width. Width and height are also added to the generated HTML to prevent the page jumping while images load.

Use `%20` for spaces in filenames, or use short filenames without spaces. Always include the real file extension.

## Place Related Images Side by Side

Wrap related images in the `image-gallery` shortcode:

```markdown
{{</* image-gallery */>}}
![Project instructions](./Project%20Instructions.png)
![Project conversation list](./Project%20List.png)
{{</* /image-gallery */>}}
```

The gallery adapts to the available space. Images appear side by side on wider screens and stack into one column on a phone. Readers can select either image to open the full-size version.

Use a gallery when the images form a set, comparison, or short sequence. Keep a single image on its own when it needs the full width for legible text.

## Compact Posts With Many Phone Screenshots

If a post contains several portrait screenshots and the normal height still makes the article feel too long, add this optional front-matter value:

```yaml
imageLayout: compact
```

This keeps the images centred and clickable while using a shorter display height. The original image is still shown when the reader selects it.

## Before Publishing

Check the following:

- The filename and letter case match the file exactly.
- The alternative text describes what the reader should notice.
- Related images use the `image-gallery` shortcode.
- Portrait screenshots no longer dominate the reading flow.
- Every image opens correctly in the lightbox.
- The layout works at desktop and mobile widths.

Render the site locally before publishing:

```bash
hugo --source . --destination /private/tmp/my-blog-hugo-check --renderToMemory --quiet
```

Then check the patch for Markdown or whitespace errors:

```bash
git diff --check
```
