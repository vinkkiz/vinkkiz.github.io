# AI Coding Assistant Instructions for al-folio Jekyll Theme

## Project Overview
This is a Jekyll-based academic portfolio website using the al-folio theme. It generates a static site from Markdown content, Liquid templates, and YAML data files. The site includes CV, publications, blog posts, projects, and news sections.

## Architecture
- **Static Site Generator**: Jekyll processes Markdown files into HTML using Liquid templating
- **Key Directories**:
  - `_pages/`: Main site pages (about, cv, publications, etc.)
  - `_posts/`: Blog posts with date-based naming (YYYY-MM-DD-title.md)
  - `_layouts/`: Liquid templates (default, post, about, etc.)
  - `_includes/`: Reusable components (header, footer, scripts, etc.)
  - `_data/`: YAML data files (cv.yml, socials.yml, repositories.yml)
  - `_bibliography/`: BibTeX files for publications
  - `_sass/`: SCSS stylesheets
  - `_plugins/`: Custom Ruby plugins for citations and data fetching

## Development Workflow
- **Local Development**: Run `docker compose up` to start Jekyll server at http://localhost:8080
- **Build**: Automatic via Jekyll in Docker; no manual build needed
- **Deployment**: GitHub Actions automatically builds and deploys to gh-pages branch on push to main
- **Debugging**: Use `docker compose logs` to view build errors; `docker compose exec -it jekyll /bin/bash` for container access

## Key Conventions
- **Front Matter**: All Markdown files use YAML front matter for metadata
  - Pages: `layout`, `title`, `permalink`
  - Posts: `layout: post`, `title`, `date`, `tags`, `categories`
  - Example: `layout: about` with `profile`, `selected_papers`, `social` options
- **Data-Driven Content**: Edit `_data/cv.yml` for CV, `_bibliography/papers.bib` for publications
- **Liquid Templating**: Use `{% include file.liquid %}` for reusable components
- **Custom Plugins**: Ruby plugins fetch external data (Google Scholar citations, INSPIRE HEP)
- **Styling**: Modify `_sass/` files; theme colors in `_themes.scss`

## Integration Points
- **Citations**: jekyll-scholar plugin pulls from Google Scholar and INSPIRE HEP APIs
- **Comments**: Giscus integration for GitHub-based comments
- **Social Media**: Configured via `_data/socials.yml` with Font Awesome icons
- **Analytics**: Optional Google Analytics, Pirsch, etc. in `_config.yml`

## Common Patterns
- **Adding Publications**: Edit `_bibliography/papers.bib` with BibTeX entries; use `selected={true}` for highlights
- **Creating Posts**: Name as `YYYY-MM-DD-title.md` in `_posts/`, use `layout: post`
- **Custom Pages**: Add to `_pages/` with appropriate layout and permalink
- **News Items**: Add Markdown files to `_news/` for announcements
- **Projects**: Add to `_projects/` with front matter for GitHub repo integration

## File Examples
- **Post**: [_posts/2015-03-15-formatting-and-links.md](_posts/2015-03-15-formatting-and-links.md) - Standard blog post structure
- **Page**: [_pages/about.md](_pages/about.md) - About page with profile and sections
- **Layout**: [_layouts/default.liquid](_layouts/default.liquid) - Base template with includes
- **Config**: [_config.yml](_config.yml) - Site-wide settings and theme options</content>
<parameter name="filePath">/workspaces/vinkkiz.github.io/.github/copilot-instructions.md