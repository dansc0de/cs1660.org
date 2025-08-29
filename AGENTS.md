# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo-based static website for cs{16,20}60 Intro to Cloud Computing course. The site uses the `hugo-dead-simple` theme and serves as an educational resource with course content and administration pages.

## Architecture

- **Static Site Generator**: Hugo v0.145.0+extended
- **Theme**: hugo-dead-simple (included as Git submodule)
- **Content Structure**: 
  - `/content/post/` - Course lectures and educational content
  - `/content/ad/` - Administrative content (syllabus, etc.)
- **Configuration**: `hugo.yaml` - Main Hugo configuration with menu structure, markup settings, and theme imports
- **Public Directory**: `/public/` - Generated static site output (not tracked in Git)

## Development Commands

### Building and Serving
```bash
# Start development server with live reload
hugo server

# Start development server on specific port
hugo server -p 1313

# Build static site for production
hugo

# Build with drafts and future content
hugo -D -F
```

### Content Management
```bash
# Create new post
hugo new content/post/new-post.md

# Create new admin content
hugo new content/ad/new-page.md
```

## Content Structure

Posts are located in `content/post/` and use Hugo's front matter format:
```yaml
---
title: "Post Title"
date: "YYYY-MM-DD"
tags:
  - tag1
  - tag2
---
```

The site supports:
- KaTeX mathematical equations (inline with `\(` and block with `$$`)
- Code syntax highlighting
- Search functionality (configurable via `params.noSearch` in hugo.yaml)
- Custom shortcodes from the theme

## Theme Configuration

The site uses the `hugo-dead-simple` theme which provides:
- Auto light/dark themes
- Site-wide search
- Keyboard navigation (`h` for home, `t` for tags, `i` for search)
- Mathematical equation rendering
- Mobile-friendly responsive design

## Git Submodules

The theme is managed as a Git submodule. To update:
```bash
git submodule update --remote themes/github.com/barklan/hugo-dead-simple
```

## Site Configuration

Key configuration in `hugo.yaml`:
- Base URL: https://cs1660.org/
- Menu structure with keyboard shortcuts
- Markup settings for code highlighting and math rendering
- Output formats including JSON for search functionality