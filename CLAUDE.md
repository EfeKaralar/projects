# Projects Portfolio — projects.alpkaralar.com

Static portfolio website served at `projects.alpkaralar.com`, hosted on Coolify VPS.

## File Structure

```
index.html       — main listing page: search / sort / filter
project.html     — individual project detail (reads ?id= from URL)
data.js          — single source of truth for all project data
styles.css       — shared terminal-dark stylesheet
assets/
  images/
    projects/    — project images (1200×675 recommended, 16:9, JPEG ~200KB)
```

## Design System

Matches the terminal aesthetic of `alpkaralar.com`:

| Variable        | Value       | Usage               |
|-----------------|-------------|---------------------|
| `--bg`          | `#0b0f14`   | page background     |
| `--bg-soft`     | `#0f1622`   | subtle bg           |
| `--panel`       | `#121a27`   | cards / panels      |
| `--border`      | `#243246`   | borders             |
| `--text`        | `#e6edf3`   | primary text        |
| `--muted`       | `#94a3b8`   | secondary text      |
| `--accent`      | `#34d399`   | green accent        |

Fonts: **IBM Plex Mono** (headings, monospace elements) + **Manrope** (body)

## Adding a New Project

Edit `data.js` and add an object to the `PROJECTS` array:

```js
{
  id:               "project-slug",         // unique, kebab-case, used in URLs
  title:            "Project Title",
  subtitle:         "One-line tagline",     // shown under title on detail page
  shortDescription: "2-3 sentence summary shown on the card",
  fullDescription:  `Multi-paragraph text. Use \n\n for paragraph breaks.`,
  techStack:        ["Tech1", "Tech2", "Tech3"],
  category:         ["ml", "fullstack"],    // array; values: ml | systems | fullstack | devops
  timeline:         "3 weeks",
  date:             "2025-06",              // YYYY-MM — used for "Newest/Oldest" sort
  githubUrl:        "https://github.com/...", // or null
  demoUrl:          "https://...",            // or null; hidden if identical to githubUrl
  blogUrl:          "https://medium.com/...", // or null
  image:            "assets/images/projects/slug.jpg",
  featured:         true,                   // reserved for future "Featured" filter
}
```

## Categories

| id         | Label             |
|------------|-------------------|
| `all`      | All               |
| `ml`       | Machine Learning  |
| `fullstack`| Full-Stack        |
| `systems`  | Systems           |
| `devops`   | DevOps            |

## Project Images

Place images in `assets/images/projects/`. If an image is missing or fails to load,
a styled gradient placeholder is shown automatically (no broken image icons).

Recommended spec: **1200 × 675 px**, JPEG, ~150–250 KB.

## Deployment (Coolify)

Serve as a static site from the repo root.
Domain: `projects.alpkaralar.com`
No build step — pure HTML/CSS/JS.

## Current Projects (10 total)

| id                          | Title                            | Categories         | Date    |
|-----------------------------|----------------------------------|--------------------|---------|
| project-sevanbot            | SevanBOT                         | ml, fullstack      | 2025-02 |
| project-lkml-dashboard      | LKML Dashboard                   | fullstack, ml      | 2024-12 |
| project-research-summarizer | Research Summarizer              | fullstack, ml      | 2024-11 |
| project-rust-load-balancer  | Rust Load Balancer               | systems, devops    | 2024-09 |
| project-cicd-portfolio      | Automated CI/CD Deployment       | devops             | 2024-08 |
| project-avt-autodrive       | Autonomous Vehicle Perception    | ml, systems        | 2024-06 |
| project-music-rnn           | Classical Music Generation       | ml                 | 2024-05 |
| project-mdadm               | Linux RAID Storage System        | systems            | 2024-03 |
| project-lisp-interpreter    | Custom LISP Interpreter          | systems            | 2024-10 |
| project-embedded-audio      | Embedded Linux Audio Processor   | systems            | 2023-08 |
