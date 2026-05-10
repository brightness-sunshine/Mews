# Magpie + Mews Integration

Use Magpie to import bookmarks and auto-generate shelves for your Mews site.

## What is Magpie?

Magpie is a local-first bookmark manager. It:
- Imports X bookmarks (and eventually browser bookmarks)
- Stores them locally (SQLite + JSON)
- Searches and groups by theme
- Exports to markdown or HTML

**Repo:** https://github.com/brightness-sunshine/MagPie

## Setup

### 1. Install Magpie

```bash
git clone https://github.com/brightness-sunshine/MagPie
cd MagPie
pip install -r requirements.txt
python3 scripts/magpie.py init-db
```

### 2. Import X bookmarks

Set your X credentials as env vars:

```bash
export X_CLIENT_ID="your_client_id"
export X_CLIENT_SECRET="your_client_secret"
export X_OAUTH2_ACCESS_TOKEN="your_access_token"
export X_OAUTH2_REFRESH_TOKEN="your_refresh_token"
```

Then fetch:

```bash
python3 scripts/fetch_x_bookmarks.py --pages 1 --page-size 100
python3 scripts/magpie.py import-jsonl
```

### 3. View your bookmarks

```bash
python3 scripts/magpie.py stats
python3 scripts/magpie.py search "your query"
python3 scripts/magpie.py groups
```

### 4. Export to Mews shelf

```bash
python3 scripts/magpie.py export-markdown --limit 50 --output ../[your]_Mews/shared-shelf/my-bookmarks.md
```

Or generate HTML:

```bash
# (Coming soon: HTML export with styling)
python3 scripts/magpie.py export-html --theme mews-light --output ../[your]_Mews/shared-shelf/my-bookmarks.html
```

## Workflow

1. **Bookmark on X** — save posts you want to keep
2. **Import monthly** — run `fetch_x_bookmarks.py` to sync
3. **Curate locally** — search/group in Magpie
4. **Export to shelf** — generate markdown/HTML
5. **Commit to Mews** — push to GitHub, site auto-updates

## Example: UFO Shelf

```bash
# Search UFO bookmarks
python3 scripts/magpie.py search "UFO" --limit 50

# Export to HTML
python3 scripts/magpie.py export-html \
  --query "UFO" \
  --output ../ufo_Mews/shared-shelf/ufo-bookmarks.html

# Commit
cd ../ufo_Mews
git add shared-shelf/ufo-bookmarks.html
git commit -m "Add UFO bookmarks"
git push
```

## Private vs Public

- **Private:** Keep bookmarks local (`data/` directory, gitignored)
- **Public:** Export and commit specific shelves to your Mews repo

This way you have a personal research archive and curated public collections.

## Questions?

See MagPie repo for full CLI docs: https://github.com/brightness-sunshine/MagPie
