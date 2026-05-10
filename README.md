# Mews / XR Mews

Mews is an OpenClaw-native news agent that turns industry noise into a readable publication.

Think of it as a reusable editorial system:

- **collect signal** from the web, feeds, inboxes, and submitted links
- **choose what matters** for a specific audience
- **write in a distinct voice** instead of generic summary sludge
- **publish in multiple formats**: site posts, newsletter blurbs, social posts, podcast scripts, and audio

This repo currently contains **XR Mews**, a reference vertical built around spatial computing. The goal is to make the core system easy to fork into other industries.

## What Mews is

Mews is not just a chatbot persona.

It is a repeatable pipeline for building an industry publication powered by OpenClaw:

1. **Source gathering** — search, monitor, and ingest relevant links
2. **Signal detection** — pick the handful of developments that actually matter
3. **Editorial framing** — explain why each item matters for a real audience
4. **Format conversion** — turn the same core signal into article, newsletter, social, and podcast outputs
5. **Publishing** — push to a site, audio feed, or messaging surface

## Core product shape

A strong Mews instance usually does four things well:

- **Daily brief**: short “what moved today” coverage
- **Deeper takes**: opinionated explainers on meaningful shifts
- **Audio**: a lightweight podcast or narrated briefing
- **Distribution**: newsletter, Telegram/Slack/WhatsApp, or web publishing

## Fork model

The clean model is:

- **Mews** = generic core skill for any industry
- **XR Mews** = one vertical fork with its own voice, sources, and audience

That means a future fork could be:

- **Bio Mews** for biotech
- **Climate Mews** for climate tech
- **Commerce Mews** for Shopify / retail ops
- **Defense Mews** for defense tech
- **AI Infra Mews** for models, chips, and tooling

Each fork keeps the same operating system but swaps:

- source list
- audience
- editorial angle
- publication cadence
- voice/persona
- call to action

## What to connect during onboarding

A useful Mews setup should ask for only the minimum needed to start.

### Required

- **Industry / beat** — what world are we covering?
- **Audience** — founders, operators, investors, consumers, developers?
- **Editorial promise** — what does this publication help people notice faster?
- **Voice** — sharp, warm, skeptical, playful, institutional, etc.

### Strongly recommended

- **Web search** for discovery
- **A GitHub repo** for the publication site and assets
- **One delivery surface**: website, newsletter, Telegram, Slack, or WhatsApp
- **A short starter source list**: 10–30 URLs, publications, companies, or keywords

### Optional but powerful

- **AgentMail** for newsletter workflows and inbound tips
- **TTS / audio tooling** for podcast generation
- **Image generation** for episode art and social cards
- **Messaging channels** for approvals, drafts, and daily digests
- **Analytics** for deciding what formats resonate

## Suggested onboarding flow

### 1. Define the publication

Ask:

- What industry are we covering?
- Who is the reader/listener?
- What counts as signal versus noise?
- What outputs matter most: articles, newsletter, podcast, social, or alerts?

### 2. Seed the source graph

Start small:

- 10–30 trusted publications, companies, analysts, and recurring search terms
- known competitors / adjacent players
- a blacklist of low-signal sources if needed

### 3. Define editorial rules

Decide:

- optimistic vs skeptical tone
- aggregation only vs original takes
- short daily cadence vs fewer higher-quality pieces
- whether the publication should quote sources directly, summarize, or synthesize

### 4. Pick distribution

Choose one primary channel first:

- website
- newsletter
- podcast/audio feed
- internal brief to Slack/Telegram/WhatsApp

### 5. Run a live pilot

Before automating heavily, ship 3–10 real items manually.

That reveals:

- whether the voice works
- whether the source mix is good
- whether the output format is actually useful
- what should become a reusable skill or cron

## What makes Mews useful outside XR

The value is not “XR but for another niche.”

The value is:

- a **curated signal layer** for a busy industry
- a **point of view**, not just link dumping
- a **publication engine** that can run daily with light oversight
- **multi-format output** from one editorial core

The best verticals are ones where people are drowning in updates but starved for interpretation.

## Quick start for forking

1. Fork this repo.
2. Keep `skills/mews/` as the reusable core.
3. Either use `skills/xr-mews/` as your starting point or replace it with your own vertical fork.
4. Connect web search, a content repo/site destination, and one delivery surface.
5. Run a manual pilot on 3–10 stories before automating recurring runs.

## Repo structure

- `skills/mews/` — generic OpenClaw skill
- `skills/xr-mews/` — XR-specific vertical overlay
- `dist/` — packaged `.skill` files generated from the skills above
- site files at repo root and subdirectories — current XR Mews publishing surface

## What still needs product decisions

Before making this fully public, the biggest open questions are:

1. **Is Mews primarily a skill, a starter repo, or a hosted service?**
2. **What is the minimum publishable stack?** Web only? Web + newsletter? Web + audio?
3. **How much human approval is expected before publish?**
4. **Do we want one canonical persona model, or encourage totally different brand voices per fork?**
5. **What should the first three non-XR vertical examples be?**

## Current recommendation

My take: position **Mews** as a **forkable OpenClaw publication system for niche industry media**.

That’s more concrete than “AI news aggregator,” and more interesting than “podcast bot.” It says:

- there is a system
- it has an editorial opinion layer
- it is meant to be adapted
- it can publish, not just summarize

If you want, next I can:

1. turn this into a cleaner public GitHub landing README,
2. create a sharper `xr-mews` fork README/positioning layer,
3. and prep the actual commits so the repo is ready to push.

## Generate public shelves

Mews includes a safe static shelf generator for selected bookmark exports:

```bash
python3 tools/generate_shelf.py
```

See `GENERATOR.md` for details. The generator is intentionally separate from hand-designed pages so it can be tested without overwriting your custom site.

