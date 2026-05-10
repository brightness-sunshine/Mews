# Mews Shelf Generator

`tools/generate_shelf.py` is a safe public-template version of the shelf generator.

It is intentionally separate from any live hand-designed site pages. Use it to generate new shelves from selected bookmark exports, not to overwrite custom pages.

## Try it

```bash
python3 tools/generate_shelf.py
```

This reads `examples/sample-bookmarks.json` and writes:

```text
shared-shelf/generated/sample-shelf.html
```

## Use with a Magpie export

Export a selected set of bookmarks from Magpie, then point the generator at that file:

```bash
python3 tools/generate_shelf.py \
  --input exports/my-topic.json \
  --output shared-shelf/generated/my-topic.html \
  --title "My Topic Shelf" \
  --description "A curated public shelf from my private bookmark archive."
```

## Safety rule

Keep raw/private bookmark data local. Commit only selected exports and generated public shelves.
