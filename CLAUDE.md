# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll static site configured for GitHub Pages deployment. The site uses the default Minima theme and includes a custom Rakefile with Japanese commands for development workflow.

## Development Commands

### Server Management
- **Start development server**: `bundle exec jekyll serve` or `rake dev`
  - The `rake dev` command includes livereload, force polling, and binds to all interfaces on port 4000
- **Build site**: `bundle exec jekyll build`
- **Install dependencies**: `bundle install`

### Content Creation
- **Create new post**: `rake posts:new`
  - Interactive command in Japanese that prompts for title and URL slug
  - Creates posts in `_posts/YYYY/` directory structure
  - Uses format: `YYYY-MM-DD-slug.md`

## Site Architecture

### Directory Structure
- `_posts/`: Blog posts organized by year subdirectories
- `_site/`: Generated static site (build output, should not be edited)
- `_config.yml`: Site configuration including theme, plugins, and metadata
- `index.markdown`: Home page using 'home' layout
- `about.markdown`: About page using 'page' layout

### Content Structure
- Posts require front matter with layout, title, date, and optional categories/tags
- Pages use Jekyll's front matter for layout and permalink configuration
- The site uses Jekyll's liquid templating for dynamic content

### Theme and Styling
- Uses Minima theme (`gem "minima", "~> 2.5"`)
- Theme provides default layouts: home, page, post
- CSS and assets are handled by the theme

### Key Configuration
- Jekyll version: ~4.4.1
- Plugins: jekyll-feed for RSS
- Posts support categories and tags
- Site uses livereload for development

## Development Notes

The Rakefile contains Japanese text and provides convenient shortcuts for common development tasks. The custom post creation task automatically handles file naming conventions and directory structure.