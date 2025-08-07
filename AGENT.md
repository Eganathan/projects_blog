# Hugo Projects Showcase

This is a Hugo static site designed to showcase projects at projects.eknath.dev with a custom theme called "projectgrid".

## Theme Features

- **Simple Design**: Clean, minimal design inspired by paper boat theme
- **Dark/Light Theme**: Toggle between light and dark themes with a button in the header
- **Theme Persistence**: Remembers your theme preference and respects system theme preference
- **Grid Layout**: Homepage displays projects in a responsive grid instead of full-width strips  
- **Project Cards**: Each project card includes:
  - Title
  - Description
  - Date
  - Tags
  - Optional thumbnail image
- **Project Pages**: Individual project pages with:
  - Header section with title, date, tags, and description
  - Action links (GitHub, demo, website, download, custom actions)
  - Full content area for detailed project information
- **Smooth Transitions**: All theme changes are animated with smooth CSS transitions

## How to Add Projects

Create new project files in `content/projects/` with the following front matter:

```yaml
---
title: "Project Name"
date: 2025-01-07
description: "Brief project description"
tags: ["react", "javascript", "web"]
status: "live"  # live, in-progress, hold, archived
thumbnail: "/images/project-thumb.jpg"  # optional
github: "https://github.com/username/repo"  # optional
demo: "https://demo.example.com"  # optional
website: "https://project.example.com"  # optional
download: "https://releases.com/download"  # optional
actions:  # optional custom actions
  - label: "API Docs"
    url: "/docs/api"
    type: "website"
    icon: "📚"
    external: false
---

Your project content goes here...
```

## Project Status Types

The theme supports four project status indicators:
- `live` - Green badge for active, deployed projects
- `in-progress` - Yellow badge for projects currently being worked on
- `hold` - Orange badge for projects temporarily paused
- `archived` - Gray badge for completed/discontinued projects

## Action Link Types

The theme supports several action link types with different colors:
- `github` - Black background
- `demo` - Blue background  
- `website` - Green background
- `download` - Red background

## Custom Actions

You can define custom actions using the `actions` array in front matter:

```yaml
actions:
  - label: "API Documentation" 
    url: "https://api.project.com/docs"
    type: "website"
    icon: "📚"
    external: true
```

## Development Commands

```bash
# Serve locally
hugo serve -D

# Build for production
hugo --minify

# Create new project
hugo new content/projects/project-name.md
```

## Theme Structure

```
themes/projectgrid/
├── layouts/
│   ├── _default/
│   │   ├── baseof.html     # Base template
│   │   └── single.html     # Project page template
│   └── index.html          # Homepage with grid layout
```

## Dark Theme

The theme includes a built-in dark/light mode toggle:

- **Theme Toggle**: Click the moon/sun icon in the header to switch themes
- **Auto Detection**: Respects your system's dark/light mode preference on first visit
- **Persistence**: Your theme choice is saved in localStorage and remembered across visits
- **Smooth Transitions**: All elements smoothly transition between themes

### Theme Colors

**Light Theme:**
- Background: Light gray (#fafafa)
- Cards: White
- Text: Dark gray (#333)
- Accent: Navy blue (#2c3e50)

**Dark Theme:**
- Background: Dark gray (#1a1a1a) 
- Cards: Medium gray (#2d2d2d)
- Text: Light gray (#e4e4e4)
- Accent: Light blue (#64b5f6)

## Notes

- Thumbnail images should be placed in `static/images/`
- The theme is fully responsive and works on all device sizes
- No external CSS/JS dependencies - everything is self-contained
- Action links open external URLs in new tabs automatically
- Theme switching works without page reload using CSS custom properties