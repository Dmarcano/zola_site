# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal website built with [Zola](https://www.getzola.org), a fast static site generator written in Rust. The site uses the "Duckquill" theme, which provides a modern, clean blog interface.

## Key Commands

### Development
- `zola serve` - Start development server with hot reload (typically runs on http://127.0.0.1:1111)
- `zola build` - Build the static site (outputs to `public/` directory)
- `zola check` - Check project for errors without building

### Content Management
- `zola init` - Initialize a new Zola project (if starting fresh)

## Project Structure

```
diego_personal_site/
├── config.toml           # Main site configuration
├── content/              # All content files
│   ├── blog/            # Blog posts (Markdown files)
│   └── landing/         # Landing page content
├── themes/duckquill/    # Theme files (git submodule)
├── templates/           # Custom template overrides
├── sass/                # Custom styling
├── static/              # Static assets
└── public/              # Generated site output (ignored in git)
```

## Content Creation

### Blog Posts
- Create new posts in `content/blog/post-name/index.md`
- Use TOML frontmatter for metadata:
  ```toml
  +++
  title = "Post Title"
  date = 2024-01-01
  +++
  ```

### Pages
- Section pages use `_index.md` files
- Page configuration in frontmatter controls templates and sorting

## Theme Details

- **Theme**: Duckquill (located in `themes/duckquill/`)
- **Theme Source**: https://codeberg.org/daudix/duckquill
- **Features**: Search, syntax highlighting, responsive design, multiple language support
- **Templates**: Uses `article_list.html` for blog listing, `article.html` for individual posts

## Configuration

Main configuration in `config.toml`:
- Site builds for search indexing (`build_search_index = true`)
- Sass compilation enabled (`compile_sass = true`)
- Syntax highlighting enabled (`highlight_code = true`)
- Base URL needs to be updated for production deployment

## Development Notes

- The theme is a git submodule, so updates should be managed carefully
- Generated files go to `public/` directory
- Static assets in `static/` are copied to the root of the built site
- Custom styles can be added in `sass/` directory