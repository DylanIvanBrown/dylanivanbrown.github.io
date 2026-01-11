# Dylan Brown's Blog

A Jekyll-based blog hosted on GitHub Pages.

## Structure

- `_posts/` - Blog posts (named as `YYYY-MM-DD-title.md`)
- `_config.yml` - Site configuration
- `index.md` - Home page (lists all posts)
- `search.md` - Search functionality
- `categories.md` - Posts organized by category
- `tags.md` - Posts organized by tag
- `search.json` - Search index (auto-generated)

## Creating a New Post

Create a new file in `_posts/` with the format `YYYY-MM-DD-title.md`:

```markdown
---
layout: post
title: "Your Post Title"
date: YYYY-MM-DD HH:MM:SS -0000
categories: [category1, category2]
tags: [tag1, tag2, tag3]
---

Your content here...
```

## Local Development

To run the blog locally:

```bash
bundle install
bundle exec jekyll serve
```

Then visit `http://localhost:4000`

## Features

- **Categories & Tags** - Organize posts with categories and tags
- **RSS Feed** - Automatically generated at `/feed.xml`
- **Search** - Client-side search available at `/search/`
- **Archive Pages** - Browse by category (`/categories/`) or tag (`/tags/`)

## Deployment

Push to the `main` branch and GitHub Pages will automatically build and deploy your site.
