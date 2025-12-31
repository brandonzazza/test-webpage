# Brandon Zazza Tech Blog

A clean, professional tech portfolio and blog built with [Astro](https://astro.build).

## Features

- ⚡ **Fast** — Static site generation
- 🌗 **Dark/Light Mode** — Toggle in header, remembers preference
- 📝 **Markdown Content** — Write blog posts and projects in Markdown
- 📱 **Responsive** — Works on all devices

## Quick Start

```bash
npm install
npm run dev
```

Open [http://localhost:4321](http://localhost:4321)

## Writing Blog Posts

Create a new `.md` file in `src/pages/blog/`:

```markdown
---
layout: ../../layouts/BlogPostLayout.astro
title: "My Post Title"
description: "A brief description"
pubDate: 2025-01-20
tags: ["Cloud", "AWS"]
---

Your content here in Markdown...
```

The filename becomes the URL: `my-post.md` → `/blog/my-post`

## Writing Projects

Create a new `.md` file in `src/pages/projects/`:

```markdown
---
layout: ../../layouts/ProjectLayout.astro
title: "Project Name"
description: "Brief description of the project"
tags: ["Terraform", "AWS", "Kubernetes"]
github: "https://github.com/username/repo"    # Optional!
demo: "https://demo.example.com"               # Optional!
date: 2025-01-20
---

Detailed writeup about the project...
```

### GitHub Link is Optional

If a project doesn't have a public repository (internal/proprietary projects), just omit the `github` field:

```markdown
---
layout: ../../layouts/ProjectLayout.astro
title: "Internal Project"
description: "A proprietary project without public code"
tags: ["Platform Engineering"]
date: 2025-01-15
---
```

The GitHub icon will only appear on projects that have the `github` field.

## Project Structure

```
src/
├── components/
│   ├── Header.astro
│   ├── Footer.astro
│   ├── PostCard.astro
│   └── ProjectCard.astro
├── layouts/
│   ├── BaseLayout.astro
│   ├── BlogPostLayout.astro
│   └── ProjectLayout.astro
├── pages/
│   ├── index.astro
│   ├── about.astro
│   ├── blog/
│   │   ├── index.astro
│   │   └── *.md              # Your blog posts
│   └── projects/
│       ├── index.astro
│       └── *.md              # Your projects
└── styles/
    └── global.css
```

## Customization

### Your Info
- Update social links in `Header.astro`, `Footer.astro`, `about.astro`
- Update email address throughout

### Colors
Edit `src/styles/global.css`:

```css
:root {
  --color-accent: #2563eb;
}

[data-theme="dark"] {
  --color-accent: #60a5fa;
}
```

## Deploy to Cloudflare Pages

1. Push to GitHub
2. Connect to [Cloudflare Pages](https://pages.cloudflare.com)
3. Build command: `npm run build`
4. Output directory: `dist`
5. Add domain: `brandonzazza.blog`

## Commands

| Command | Description |
|---------|-------------|
| `npm run dev` | Dev server at localhost:4321 |
| `npm run build` | Build to `./dist/` |
| `npm run preview` | Preview build |

---

Built with [Astro](https://astro.build)
