# Claude Code Project Notes

## Critical Rules

- **Always change all language versions simultaneously.** This site has 3 languages: English (`.en.md`), Simplified Chinese (`.zh-cn.md`), and Japanese (`.ja.md`). Any change to content, templates, config, or i18n must be applied to ALL three language versions. Never change only one language.

## Project Structure

- Hugo static site with LoveIt theme
- Deployed at `https://OkongOyangO.github.io/OkongOyangO.Notes/` (subdirectory deployment)
- Posts live in `content/posts/` with `{name}.en.md`, `{name}.zh-cn.md`, `{name}.ja.md` naming
- Layout overrides in `layouts/` (override theme files from `themes/LoveIt/layouts/`)
- Custom i18n overrides in `i18n/` (en.toml, zh-CN.toml, ja.toml)
- Config: `hugo.toml`
- Build: `rm -rf public/ && hugo` then `git add . && git commit && git push`

## Key Decisions

- Menu items use `pageRef` (not `url`) to avoid subdirectory URL ordering bugs with `relLangURL`
- Asset paths use `relURL` in layout overrides to stay within the subsite
- Custom `layouts/404.html` links back to subsite, not main site
- Custom `layouts/partials/head/link.html` fixes favicon paths for subdirectory deployment
- Custom `layouts/partials/header.html` adds text labels to Search/Theme/Language buttons
- Each post must have a unique `date` to ensure consistent ordering across languages
- KaTeX math enabled with Goldmark passthrough; long `aligned` blocks should be split
