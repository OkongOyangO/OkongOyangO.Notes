# How to Publish a Note on OkongOyangO.Notes

This guide explains how to transform a regular `.md` note into the publishable multilingual format used in `content/posts/`.

## 1. File Naming Convention

Each post needs **three** files (one per language) placed directly in `content/posts/`:

```
content/posts/
  Your_Post_Name.en.md      # English
  Your_Post_Name.zh-cn.md   # Simplified Chinese
  Your_Post_Name.ja.md      # Japanese
```

- Use underscores or hyphens in the filename (spaces are allowed but underscores are preferred).
- The `.en.md` / `.zh-cn.md` / `.ja.md` suffixes tell Hugo which language each file belongs to.
- All three files share the same base name so Hugo treats them as translations of each other.

## 2. YAML Frontmatter

Replace any existing title line (e.g., `# My Title`) with a YAML frontmatter block at the very top of the file:

```yaml
---
title: "Your Post Title"
date: 2026-01-15T10:00:00-05:00
draft: false
math: true
tags: ["Condensed Matter", "Topology"]
categories: ["Physics Notes"]
---
```

| Field        | Required | Notes |
|--------------|----------|-------|
| `title`      | Yes      | The display title. Translate for each language version. |
| `date`       | Yes      | ISO 8601 format. **Each post must have a unique date** to ensure consistent ordering across languages. |
| `draft`      | Yes      | Set to `false` to publish, `true` to hide. |
| `math`       | Yes      | Set to `true` to enable KaTeX math rendering. |
| `tags`       | No       | List of tags (keep consistent across language versions). |
| `categories` | No       | Typically `["Physics Notes"]`. |

**Important**: Do NOT include a `# Title` heading in the body if you already have `title` in the frontmatter — Hugo renders the title automatically. Having both creates a duplicate heading.

## 3. Summary Truncation

Add a `<!--more-->` tag after the first introductory paragraph. Everything above this tag becomes the post summary shown on the homepage and post list.

```markdown
---
title: "My Post"
...
---

This article discusses X and derives Y from first principles.

<!--more-->

## First Section

Content starts here...
```

## 4. Math Formulas

KaTeX is enabled site-wide with Goldmark passthrough configured. Supported delimiters:

| Type    | Delimiters                 |
|---------|----------------------------|
| Inline  | `$...$` or `\(...\)`       |
| Display | `$$...$$` or `\[...\]`     |

LaTeX environments (`\begin{equation}`, `\begin{align}`, etc.) are also supported.

### Known issues and workarounds

- **Long `aligned` environments**: If a single `$...$` or `$$...$$` block contains a very long `aligned` environment with complex commands like `\underbrace`, it may not render correctly. **Split it into multiple separate display math blocks** instead of one giant block.
- **Underscores in math**: The Goldmark passthrough extension handles this, but if you see unexpected italics inside math, check that the passthrough config in `hugo.toml` is intact.

## 5. Images

Use standard Markdown image syntax. For external images:

```markdown
![Description](https://example.com/image.png)
```

For local images, place them in `static/images/` and reference them with the site base path:

```markdown
![Description](/OkongOyangO.Notes/images/my_figure.png)
```

## 6. Unique Dates for Consistent Ordering

Hugo sorts posts by date. If multiple posts share the same timestamp, the fallback sort is by title — which differs across languages, causing inconsistent ordering. Always assign a **unique date** to each post.

Example spacing for posts published on the same day:

```
Post A: 2026-01-08T21:54:37-05:00
Post B: 2026-01-08T22:00:00-05:00
Post C: 2026-01-08T23:00:00-05:00
Post D: 2026-01-08T23:30:00-05:00
```

## 7. Translation Workflow

1. Write the English version (`.en.md`) first.
2. Translate the frontmatter `title` (and optionally the body) for `.zh-cn.md` and `.ja.md`.
3. Keep `tags`, `categories`, `date`, and `draft` identical across all three files.
4. Place the `<!--more-->` tag at the equivalent position in each translation.

## 8. Quick Checklist

- [ ] Three files created: `.en.md`, `.zh-cn.md`, `.ja.md`
- [ ] YAML frontmatter with `title`, `date`, `draft: false`, `math: true`
- [ ] No duplicate `# Title` heading in body
- [ ] `<!--more-->` tag placed after the introductory paragraph
- [ ] Unique `date` (not shared with any other post)
- [ ] Long `aligned` blocks split into separate math blocks if needed
- [ ] Tags and categories consistent across all three language files

## 9. Build and Deploy

```bash
cd /path/to/OkongOyangO.Notes

# Clean build (recommended when config changed)
rm -rf public/ && hugo

# Or just rebuild
hugo

# Deploy
git add .
git commit -m "Add new post: Your Post Name"
git push
```

The site is served at: `https://OkongOyangO.github.io/OkongOyangO.Notes/`
