# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **pure static HTML website** for "烙馍网 AI团队" (Luomor.com AI Team) — a personal branding/marketing site for a one-person AI company run by 张春生 (Peter Zhang). There is **no build system, no package.json, no framework, no Node.js** — just standalone `.html` files with inline CSS and third-party JavaScript (Google AdSense, Google Analytics, Baidu Analytics).

## File Inventory

| File | Theme | Description |
|------|-------|-------------|
| `index.html` | Dark sci-fi (purple/indigo) | "One-Person AI Company" concept page — manifesto-style with dark theme, CSS variables `--primary: #6366f1`, `--dark: #0f172a` |
| `about.html` | Corporate blue | Traditional "AI team" introduction page — LLM/NLP/CV/MLOps team, blue theme `--primary-color: #2563eb` |
| `gemini.html` | Orange/pragmatic | Pragmatic "AI landing" page — focus on practical AI implementation, orange theme `--primary: #f97316` |
| `grok.html` | Traditional food culture (red/gold) | "烙馍网" traditional Chinese food culture page (烙馍 = flatbread), red theme with food heritage narrative |
| `luomor_ai_team.html` | Premium corporate (gold/dark) | "AI team" corporate page with scroll-reveal animations, premium typography (ZCOOL XiaoWei, Space Mono), gold/dark theme |
| `docs/` | empty | Empty directory |

## No Build/Lint/Test Commands

This is a static site. Development workflow:
- Edit HTML files directly
- Preview by opening `.html` files in a browser or serving via any static HTTP server
- Deploy by uploading files to the web server at luomor.com

## Shared Patterns Across Pages

All pages share:
- **Google AdSense**: `ca-pub-6096731848877113` (injected at top of each page)
- **Google Analytics**: `G-87JET1FJ65`
- **Baidu Analytics**: `c8281d72e36e9ac47796d3d2d3c0166c`
- **Language**: `zh-CN` (Simplified Chinese)
- **Responsive breakpoints**: `@media (max-width: 768px)` for mobile
- **External link**: All logo links point to `https://www.luomor.com`
- **Contact**: `coupon@luomor.com`, `ai@luomor.com`

## Key Architecture Notes

1. **Each HTML file is completely self-contained** — all CSS is inline in `<style>` tags, no external stylesheets or JS bundles.
2. **No shared assets directory** — icons use emoji characters, images use placeholder services (picsum.photos).
3. **No SPA/router** — pages are independent landing pages, not a multi-page application.
4. **The `gemini-code-*.html` file** (in the listing) is an auto-generated file, likely from a prior AI tool session — not actively maintained.
5. **No existing `.claude/` directory** or Cursor/Copilot rules were found in this project.

## When Modifying Pages

- **CSS scoping**: Each page has its own CSS with `:root` variables. Changes to one page do not affect others.
- **Navigation**: Each page has internal anchor links or links to `luomor.com`. There is no cross-page navigation between the HTML files in this repo.
- **Ad/Analytics scripts**: These are duplicated at the top of every HTML file. When adding a new page, copy them from any existing page.
- **Fonts**: Some pages load Google Fonts (Noto Sans SC, Noto Serif SC, ZCOOL XiaoWei, Space Mono). Check `<link rel="preconnect">` and `@import` in each page's head.
