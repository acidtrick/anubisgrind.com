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
- **Music release:** TBD — full album (10 songs confirmed), releasing all at once
- **Domain:** anubisgrind.com (owned, managed via Cloudflare)
- **Goal:** Build a band website, run locally first, then deploy to Cloudflare Pages
- **Repo location:** `/Users/rmarches/Documents/null-interval/null-music/anubis-grind/anubisgrind.com`

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
- Album artwork: TBD (new artwork needed — Eleventh Hour track dropped)
- Music: .wav files; to be uploaded to Cloudflare R2 for streaming on site

## Pages

| Page | Status |
|---|---|
| Home | Live — logo hero only |
| Music | Live — "Coming Soon" placeholder; build out when tracks ready |
| Contact | Live — anubisgrind@proton.me, anubisgrind@gmail.com, nullinterval@proton.me |
| Merch | Live — placeholder "Coming soon" |
| About | Removed |

## Music Page Plan

- `/music` — album artwork image, click to go to album page
- `/music/[album-slug]` — full track listing; each track has inline HTML5 audio player + optional Lyrics and Video buttons
- `/music/[album-slug]/[track-slug]` — lyrics page for that track (text rendered in Astro, no extra storage)
- Audio files hosted on Cloudflare R2 (bucket already set up, just needs files uploaded)
- Format: .wav preferred; convert to MP3 if file sizes become an issue
- Videos: link to YouTube (unlisted) — no R2 needed for video; YouTube handles streaming/device compatibility for free
- Video and Lyrics buttons are hidden per-track if not available
- Release strategy: full album (~10 songs) all at once, date TBD

## Music Production Chain

Each song goes through this pipeline from composition to release-ready master:

1. **Write** — Fee writes the song (lyrics, structure, concept)
2. **Suno** — Upload to Suno, generate the song, download final version as .wav + stems
3. **Logic Pro** — Mix using the stems (EQ, compression, arrangement, effects)
4. **LANDR / LANDR plugins** — Master (AI mastering or LANDR plugin chain in Logic)
5. **LUFS / True Peak normalize** — Final loudness pass to streaming targets before release
6. **Release** — Upload to R2, deploy on site, distribute to streaming platforms

**File locations** (all under `/Users/rmarches/anubis-grind/anubis-grind-music/`):

| Stage | Path |
|---|---|
| Suno downloads | `a-suno-mix/` |
| Suno stems | `b-stems/` |
| Mixed & mastered, pre-LUFS/TP | `masters/a-pre-lufs-tp-masters/` |
| Final LUFS/TP masters (all releases) | `masters/final-lufs-masters/` |
| This LP specifically | `masters/final-lufs-masters/anubis-grind-lp/` |

## Music Strategy

- Full album release, all tracks at once, date TBD
- Audio hosted on Cloudflare R2 (free 10GB tier, bucket already configured)
- Site streams directly from R2 via HTML5 audio players
- Lyrics: rendered as Astro pages, no extra storage needed
- Videos: YouTube unlisted links — free, globally cached, handles all devices; no R2 needed for video
- Post-release: add Spotify / Apple Music / SoundCloud embeds/links
- Cloudflare Pages has a 25MB file size limit — R2 sidesteps this for audio

## Social Media

- Instagram: TBD (handle not yet set)
- TikTok: TBD
- YouTube: eventual / TBD

## AI Music Marketing Notes

- Transparency about AI performance may be an asset (novelty/concept) vs liability
- Framing: "AI as instrument, Fee as composer/artist" — positions Fee as the creative force
- AI music community is growing — potential niche audience
- Monitor platform policies (Spotify, etc.) as they evolve on AI-generated content

## Coding Conventions

- Lowercase for all filenames and extensions (e.g. `band-logo2.png` not `band-logo2.PNG`)
- Uppercase only where the language requires it (class names, constants, etc.)

## Decisions Log

| Date | Decision |
|---|---|
| 2026-03-20 | Project initialized |
| 2026-03-25 | Tech stack: Astro + Cloudflare Pages |
| 2026-03-25 | Aesthetic: dark/grungy, logo-driven palette |
| 2026-03-25 | Start with Home page only, other pages as placeholders |
| 2026-03-25 | Pre-release music: .wav previews via HTML5 audio |
| 2026-03-25 | Site deployed to Cloudflare Workers — live at anubisgrind.com |
| 2026-06-01 | Dropped Eleventh Hour track; full album TBD (~10 songs) |
| 2026-06-01 | Removed About page from site and nav |
| 2026-06-01 | Music page plan: album art → track listing page, audio via Cloudflare R2 |
| 2026-06-01 | R2 bucket already set up; just needs audio files uploaded |
| 2026-07-02 | LUFS/TP normalization completed — all 10 LP tracks normalized to -14 LUFS / -1 dBTP, 24-bit WAV |
| 2026-07-02 | Final masters in `masters/final-lufs-masters/anubis-grind-lp/`; originals untouched in `a-pre-lufs-tp-masters/` |
| 2026-07-02 | Confirmed full LP track list and album title: "Anubis Grind" (self-titled) — see LP Track List section |
| 2026-07-17 | Remixed Gravity Flows, Waking What Sleeps, and Duat; re-normalized all three (-14.03/-0.99, -14.00/-2.86, -14.00/-7.05 dBTP respectively) — finals updated in `masters/final-lufs-masters/anubis-grind-lp/` |

## LP Track List

**Album:** Anubis Grind (self-titled)
All 10 tracks normalized 2026-07-02. Files in `masters/final-lufs-masters/anubis-grind-lp/`.

| # | Title | Slug | Hz | LUFS | True Peak | Notes |
|---|---|---|---|---|---|---|
| 1 | Duat | duat | 48k | -14.0 | -7.05 dBTP | Wide dynamics (13.2 LU); remixed & re-normalized 2026-07-17 |
| 2 | The Weighing | the-weighing | 44.1k | -14.0 | -3.6 dBTP | |
| 3 | Waking What Sleeps | waking-what-sleeps | 48k | -14.0 | -2.86 dBTP | Remixed & re-normalized 2026-07-17 |
| 4 | Something Lets Us In | something-lets-us-in | 48k | -14.0 | -3.8 dBTP | |
| 5 | Venus Lies | venus-lies | 44.1k | -14.0 | -1.9 dBTP | |
| 6 | Afterglow | afterglow | 48k | -14.0 | -1.0 dBTP | |
| 7 | Between Two Worlds | between-two-worlds | 48k | -14.0 | -4.0 dBTP | |
| 8 | Without a Sound | without-a-sound | 48k | -14.0 | -0.9 dBTP | 0.1 dBTP over ceiling — accepted; fix requires Logic |
| 9 | Big Dark Open | big-dark-open | 48k | -14.0 | -1.0 dBTP | |
| 10 | Gravity Flows | gravity-flows | 48k | -14.0 | -0.99 dBTP | Remixed & re-normalized 2026-07-17 |

Slugs map to filenames in the masters folder. Use as URL slugs for Music page routes (`/music/anubis-grind/[slug]`).

## LUFS Normalization Tool

`ffmpeg-normalize` is installed but not in PATH — invoke as `python3 -m ffmpeg_normalize`.

Standard command for future tracks:
```bash
python3 -m ffmpeg_normalize <input.wav> \
  -of <output_folder> \
  -t -14 -tp -1.0 -lrt 11 \
  -c:a pcm_s24le -ofmt wav -ext wav \
  -ar <original_hz> -f
```
Add `--keep-lra-above-loudness-range-target` for tracks with LRA > 11 LU.
Always specify `-ar` to prevent loudnorm from upsampling to 192 kHz in dynamic mode.

## Open Questions

- Social media handles (Instagram, TikTok, YouTube URLs)
- Album name: "Anubis Grind" (self-titled) ✓ confirmed
- Album artwork (new needed — Eleventh Hour dropped)
- Any copy/text for the Home page (tagline, description)
- Merch plans (print-on-demand service? Existing store?)
