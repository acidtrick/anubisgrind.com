# Anubis Grind — Project Guide for Claude

## About Fee (the user)

- **Name:** Fee
- **Background:** Linux Systems Administrator, 30 years experience
- **Also:** Musician, animal lover, physically fit
- **Approach:** Experienced and technical — no need to over-explain fundamentals

## Fee's Systems

| Machine | OS | Role |
|---|---|---|
| Laptop | macOS | Primary dev machine (current session) |
| Server | Ubuntu 18 | Runs VirtualBox with various Linux VMs |
| Node.js | v24.14.1 | Installed on macOS |
| npm | v11.11.0 | Installed on macOS |

## Project: anubisgrind.com

- **Band name:** Anubis Grind
- **Genre:** AI grunge rock — 4 members, female lead vocalist
- **Concept:** Songs written by Fee, performed by AI using Suno
- **Music release:** ~May 1st 2026 to all platforms
- **Domain:** anubisgrind.com (owned, managed via Cloudflare)
- **Goal:** Build a band website, run locally first, then deploy to Cloudflare Pages
- **Repo location:** `/Users/rmarches/Documents/null-interval/working-eight/null-music/anubis-grind/anubisgrind.com`

## Tech Stack

- **Framework:** Astro (static site generator, ideal for Cloudflare Pages)
- **Hosting:** Cloudflare Pages (static, free tier)
- **DNS:** Already on Cloudflare

## Design & Aesthetic

- **Vibe:** Dark, heavy, grungy — reference: soundgardenworld.com
- **Color palette (from logo):**
  - Background: near-black / dark charcoal
  - Accent: sandy ochre / stone tones
  - Pop: blood red / rust (from logo smoke)
  - Text: off-white / aged parchment
- **Font:** Rough hand-painted brush stroke style (matching the logo) — approximate with a dark/metal web font
- **Logo:** Stone cartouche with Anubis head, hieroglyphics border — has logo file

## Assets

- Logo: YES (stone cartouche design)
- Band member images: YES (AI-generated band member photos)
- Music: .wav files available pre-release; streaming platforms ~May 1st

## Pages Planned

| Page | Status |
|---|---|
| Home | Build first — full content |
| Music | Placeholder now, populate ~May 1st |
| About | Placeholder |
| Merch | Placeholder |
| Contact | Placeholder |

## Music Strategy (pre vs post release)

**Pre-release (now → May 1):**
- Embed .wav previews using HTML5 audio player styled to match site aesthetic
- "Coming Soon" teaser approach — build hype

**Post-release (May 1+):**
- Embed Spotify / Apple Music / SoundCloud widgets
- Link to all platforms

**Note on .wav hosting:**
- Cloudflare Pages has a 25MB file size limit — large .wav files need an alternative
- Options: Cloudflare R2 (object storage), or just link out to streaming once live
- For now, compress previews or use short clips

## Social Media

- Instagram: TBD (handle not yet set)
- TikTok: TBD
- YouTube: eventual / TBD

## AI Music Marketing Notes

- Transparency about AI performance may be an asset (novelty/concept) vs liability
- Framing: "AI as instrument, Fee as composer/artist" — positions Fee as the creative force
- AI music community is growing — potential niche audience
- Monitor platform policies (Spotify, etc.) as they evolve on AI-generated content

## Decisions Log

| Date | Decision |
|---|---|
| 2026-03-20 | Project initialized |
| 2026-03-25 | Tech stack: Astro + Cloudflare Pages |
| 2026-03-25 | Aesthetic: dark/grungy, logo-driven palette |
| 2026-03-25 | Start with Home page only, other pages as placeholders |
| 2026-03-25 | Pre-release music: .wav previews via HTML5 audio |

## Open Questions

- Social media handles (Instagram, TikTok, YouTube URLs)
- Band member names / bios (for About page)
- Any copy/text for the Home page (tagline, description)
- Merch plans (print-on-demand service? Existing store?)
- What to call the .wav preview section ("Listen" / "Preview" / "First Listen")
