# Mews Setup Guide

Clone this template to build your own curator site with bookmarks, portfolio, and public/private shelves.

## Pattern

Name your repo: `[industry]_Mews` or `[personal]_Mews`

Examples:
- `xr_Mews` — XR industry curator
- `ai_Mews` — AI researcher
- `ufo_Mews` — UFO/disclosure researcher
- `taron_Mews` — Personal site

## Quick Start

1. **Fork or clone this repo**
   ```bash
   git clone https://github.com/brightness-sunshine/Mews [your-name]_Mews
   cd [your-name]_Mews
   ```

2. **Customize**
   - Edit `index.html` — your name, bio, links
   - Add shelves to `shared-shelf/` (copy `sample-shelf.html` and rename)
   - Update `README.md` with your focus

3. **Add bookmarks via Magpie**
   - See MAGPIE_INTEGRATION.md for setup

4. **Deploy**
   - **GitHub Pages:** Push to main, enable in repo settings
   - **Vercel:** Connect repo, it auto-deploys

## Structure

```
[your]_Mews/
├── index.html              # Home page, bio, shelf links
├── README.md               # About you
├── shared-shelf/           # Public bookmark collections
│   ├── sample-shelf.html   # Example (customize this)
│   └── [topic]-shelf.html  # Add more shelves
├── books/                  # Reading notes, highlights
├── portfolio/              # Your work/projects (optional)
└── data/                   # (gitignored) Local Magpie bookmarks
```

## Features

- **Curated shelves** — public bookmark collections by topic
- **Portfolio** — your work/projects
- **Private notes** — books, reflections (kept local)
- **Magpie integration** — auto-generate shelves from bookmarks

## Next Steps

1. Rename your repo to `[your]_Mews`
2. Edit `index.html` with your details
3. Create your first shelf in `shared-shelf/`
4. Deploy to GitHub Pages or Vercel
5. (Optional) Connect Magpie for bookmark automation

## Questions?

See MAGPIE_INTEGRATION.md for bookmark workflows.
