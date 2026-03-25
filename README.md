# The Heart Speaks — Spectrum of Wisdom

A single-file HTML web experience exploring emotional wisdom through Scripture. Built for **Green Pastures / Nat Consulting Ltd.** as a standalone, deployable landing page.

---

## Overview

**The Heart Speaks** is an interactive, content-rich webpage that guides users through the emotional landscape of the Bible — connecting their present feelings to biblical figures, scriptures, and practical wisdom tools. It is the frontend showcase for the *Spectrum of Wisdom* framework, a seven-dimension model for whole-person flourishing.

---

## File Structure

```
spectrum-of-wisdom-1.html   ← Everything. One self-contained file.
```

No build step. No dependencies. No external scripts. Just open in a browser or deploy as-is.

---

## Sections

| Section | Description |
|---|---|
| **Hero** | Animated heart visual with floating emotional vocabulary words |
| **Emotional Map** | 6 clickable emotion cards (Anger, Fear, Joy, Shame, Loneliness, Peace) — each expands to show real-life context, biblical insight, figures, practical wisdom, and a reflection question |
| **The Pathway** | 4-step journey framework: Awareness → Understanding → Healing → Transformation |
| **Biblical Figures** | Interactive profiles for David, Joseph, Elijah, Peter, and Paul — each showing their emotion, event, response, lesson, and personal application |
| **Heart School** | 5 progressive curriculum modules from emotional awareness to spiritual emotional intelligence |
| **Scripture Hub** | 6 thematic scripture collections (Lament, Fear to Faith, Restoration, Joy in Suffering, Shame and Grace, Righteous Anger) with verse displays |
| **Emotional Tools** | 4 modal-based tools: Daily Check-In, Journal Prompts, Self-Reflection, Guided Exercises |
| **Spectrum Preview** | Overview of the 7-dimension Spectrum of Wisdom framework |
| **Stories** | 3 featured story cards |
| **CTA Banner** | Call to action for beginning the journey |
| **Footer** | Navigation, links, and brand information |

---

## External Dependencies

All loaded via CDN — no local assets required.

| Resource | Purpose |
|---|---|
| `Google Fonts` | Cormorant Garamond (headings), DM Sans (body), Playfair Display |

No JavaScript libraries. No CSS frameworks. All interaction is written in vanilla JS.

---

## Interactivity

All interactive features are powered by inline JavaScript at the bottom of the file:

- **`showEmotion(key)`** — Expands emotion detail panel when a feeling card is clicked
- **`showCharacter(key)`** — Loads biblical figure profile when a character card is clicked
- **`showTheme(key)`** — Swaps scripture content in the hub panel
- **`openModal(id)` / `closeModal(id)`** — Controls the modal overlay for tool cards
- **`scrollTo(id)`** — Smooth-scrolls to a named section (overrides native `scrollTo`)
- **IntersectionObserver** — Triggers `.fade-in` animations as sections enter the viewport
- **Scroll listener** — Adds a shadow to the nav bar after 60px of scroll

---

## Design System

### Color Palette

| Variable | Hex | Usage |
|---|---|---|
| `--warm-white` | `#FAF7F2` | Page background |
| `--sand` | `#F5EFE0` | Section backgrounds, card fills |
| `--clay` | `#C4956A` | Primary accent, labels, borders |
| `--burnt` | `#8B5E3C` | Hover states, headings |
| `--deep` | `#2C2416` | Dark sections, body text |
| `--gold` | `#C9A84C` | Highlights, spectrum accents |
| `--olive` | `#6B7C5C` | Secondary accent |
| `--slate` | `#4A5568` | Body copy, descriptions |

### Typography

- **Headings:** Cormorant Garamond (300–600 weight, italic used decoratively)
- **Body / UI:** DM Sans (300–500 weight)
- **Fluid sizing:** `clamp()` used on `h1` and `h2` for natural scaling

### Animations

- Pulsing heart rings (`pulseRing`)
- Heartbeat center icon (`heartbeat`)
- Floating vocabulary words (`floatWord`)
- Scroll line pulse (`scrollPulse`)
- Fade-in on scroll (IntersectionObserver + CSS transition)

---

## Responsiveness

| Breakpoint | Behaviour |
|---|---|
| `> 900px` | Full desktop layout — 2-column hero, multi-column grids |
| `≤ 900px` | Single or reduced columns; hero right panel hidden; nav links hidden |

> **Known gap:** There is no hamburger/mobile menu at ≤ 900px. Nav links are hidden but not replaced. Mobile users cannot navigate by menu. This should be addressed before production deployment.
>
> **Secondary gap:** No second breakpoint at ~480px. Some 2-column layouts (emotion detail grid, footer) may feel cramped on small phones.

---

## Deployment

This file can be deployed anywhere that serves static HTML:

- **Netlify** — Drag and drop the `.html` file into the Netlify dashboard
- **GitHub Pages** — Rename to `index.html`, push to a repo, enable Pages
- **Any web host** — Upload via FTP/SFTP to the root or a subdirectory

No server-side processing is required.

---

## Known Issues & Recommended Fixes

| Issue | Priority | Notes |
|---|---|---|
| No mobile nav menu | High | Nav links hidden at 900px with no hamburger replacement |
| No 480px breakpoint | Medium | 2-column layouts on small phones may need single-column pass |
| `event` global in `showCharacter()` | Low | Uses implicit `event` object; pass explicitly for robustness |
| `scrollTo` naming collision | Low | Overrides native `window.scrollTo` — works but worth renaming |
| Scripture passage counts are cosmetic | Low | "18 passages" label shows only 3 verses in the panel |

---

## Content Data

All content is embedded directly in the HTML file as JavaScript objects. To update:

- **Emotions** — Edit the `emotions` object in the `<script>` block (approx. line 1960)
- **Biblical figures** — Edit the `characters` object (approx. line 2077)
- **Scripture themes** — Edit the `themes` object (approx. line 2162)
- **Modal content** — Edit the modal `<div>` blocks in the HTML body

---

## Brand

Built for **Green Pastures** (trading name of Nat Consulting Ltd.)
Part of the *Spectrum of Wisdom* resource series — emotional intelligence through Scripture.
