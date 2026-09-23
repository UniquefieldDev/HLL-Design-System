---
version: "1.0"
name: "Hungaro Lux Light"
description: "B2G design system for a Hungarian LED street-lighting manufacturer. Deep navy ground for persuasion, light ground for reading, one amber accent reserved for the three conversion points. Industrial grotesque headings, monospace for measured technical values. Built for municipal decision-makers, not for SaaS."
colors:
  primary: "#12132C"
  secondary: "#222E66"
  accent: "#4A81D3"
  accentDark: "#2F63AE"
  highlight: "#E9A23B"
  muted: "#797A8C"
  surface: "#F8F9FA"
  ink: "#111013"

typography:
  hero:
    fontFamily: Archivo, "Helvetica Neue", Arial, sans-serif
    fontSize: clamp(2.2rem, 5vw, 3.4rem)
    fontWeight: 700
  h1:
    fontFamily: Archivo, "Helvetica Neue", Arial, sans-serif
    fontSize: 2.125rem
    fontWeight: 700
  h2:
    fontFamily: Archivo, "Helvetica Neue", Arial, sans-serif
    fontSize: 1.375rem
    fontWeight: 600
  body-md:
    fontFamily: Inter, "Helvetica Neue", Arial, sans-serif
    fontSize: 1rem
    fontWeight: 400
  label-caps:
    fontFamily: "IBM Plex Mono", ui-monospace, monospace
    fontSize: 0.625rem
    fontWeight: 600
  data-mono:
    fontFamily: "IBM Plex Mono", ui-monospace, monospace
    fontSize: 0.8125rem
    fontWeight: 500

components:
  button-primary:
    backgroundColor: "{colors.highlight}"
    color: "#111013"
    padding: 12px 18px
    minHeight: 44px
    borderRadius: 2px
  button-secondary:
    backgroundColor: transparent
    border: "1.5px solid {colors.muted}"
    padding: 12px 18px
    minHeight: 44px
---

## Overview

Hungaro Lux Light manufactures LED street lighting and operates it for 300+ Hungarian municipalities. The buyer is not a designer, a developer or a procurement professional — it is the clerk or mayor of a village under 5 000 people, who will read the page on a phone, on a municipal network, and then take a printout to a council meeting.

That single fact settles most of this system. The page has to look like engineering, read like plain Hungarian, and survive being printed in greyscale. Nothing here is decorative for its own sake: the dark ground is where the argument is made, the light ground is where long text is actually read, and the one warm accent exists because amber is the only colour on the page that means *light*.

The palette is not invented. It is lifted from the company's existing site — deep navy ground, cool blue accent — and extended with two values the old site was missing: a darker blue that passes contrast for links on white, and the warm amber already present in the hero imagery, promoted to a real token.

- Density: 4/10 — Sparse, generous whitespace
- Variance: 3/10 — Low, deliberately repetitive
- Motion: 2/10 — Restrained

- **Style:** Industrial, Engineered, Evidence-led, Sober
- **Keywords:** Municipal, B2G, technical datasheet, night photography, measured values, long-life infrastructure
- **Era:** Contemporary industrial
- **Light/Dark:** ✓ Full / ✓ Full — both grounds are load-bearing, not a theme toggle

## Colors

- **Éjkék / Night Navy** (#12132C) — Primary dark ground. Hero, evidence bands, reference and case-study headers. The spine of the identity.
- **Mélykék / Deep Blue** (#222E66) — Secondary surface on the dark ground. Cards and raised bands, separating layers from the navy.
- **Kék akcent / Accent Blue** (#4A81D3) — Buttons, links and active states **on the dark ground only**. 4.6:1 on #12132C — passes AA. On white it is 3.9:1 and fails for body text.
- **Kék sötét / Accent Blue Dark** (#2F63AE) — The same blue for links and interactive text **on light grounds**. 6.0:1 on #F8F9FA.
- **Borostyán / Amber** (#E9A23B) — The single warm accent, reserved for conversion elements and one highlighted figure per band. 8.4:1 on navy. On white it is 2.2:1 — decorative only there, never text.
- **Szürke / Muted Grey** (#797A8C) — Captions, metadata, assumptions. Passes on white; on navy use a lighter step.
- **Világos alap / Surface** (#F8F9FA) — Ground for the knowledge base, technical datasheet and long case-study body.
- **Tinta / Ink** (#111013) — Body text on light grounds. Off-black, not #000000 — less tiring over fifteen paragraphs.

**The governing rule: dark grounds are for persuasion, light grounds are for reading.** Hero, evidence bands and reference headers sit on navy. Knowledge-base articles, the technical datasheet and case-study bodies sit on light. Nobody reads a thousand words on navy.

## Typography

- **Display / Hero:** Archivo — Weight 700, tracking −0.02em. A grotesque drawn for large-format print: slightly condensed, flat terminals, no geometric softness. Industrial without being retro.
- **Body:** Inter — Weight 400/500, 16px / 1.6, max 65ch per line. Deliberately neutral; the headline carries the character, the body's job is to stay readable for a clerk over fifteen paragraphs.
- **UI Labels / Captions:** IBM Plex Mono — 0.625rem, weight 600, uppercase, 0.09em letter-spacing. Eyebrows, section tags, badges.
- **Monospace / Measured values:** IBM Plex Mono — 0.8125rem, tabular figures. Every technical value, every currency figure, every count.

Scale:
- Hero: clamp(2.2rem, 5vw, 3.4rem)
- H1: 2.125rem
- H2: 1.375rem
- Body: 1rem / 1.6
- Small: 0.875rem
- Mono data: 0.8125rem

**Two non-negotiables.**

1. **Hungarian diacritics are an acceptance criterion, not an assumption.** Every face must render `ő ű ú ü ó ö í é á Ő Ű` correctly at every weight used. Most "industrial" display faces fail here. Verify before the first build, not after.
2. **Measured values are set in monospace.** `155 lm/W · IP66 · IK10 · 3000 K · L90B10 100 000 h` reads as data; the same string in the body face reads as marketing. Tabular figures also keep columns aligned in the datasheet and the calculator.

Fallback display pair if Archivo's coverage or character does not hold: **Chivo** (same foundry, more voice) or **Barlow Semi Condensed** (road-sign lineage, more overtly industrial). Body and mono stay as they are.

## Layout

- **Grid:** CSS Grid. Max-width 1120px centred, 36px side padding on desktop, 18px on mobile.
- **Spacing rhythm:** Base unit 0.5rem (8px). Section padding 26px top / 30px bottom, scaled up on dark bands.
- **Section vertical gaps:** clamp(2.5rem, 5vw, 4.5rem). Restrained — this is a document-like site, not a scroll experience.
- **Hero layout:** Split — headline and two buttons left, night-map visual right. Sized to its content, never 100vh: the evidence band must be visible on first paint.
- **Feature sections:** Four-up cards for the evidence pillars; zig-zag for product explanation. Two-up for before/after imagery.
- **Reading measure:** 65ch maximum for any running text. Tables and the datasheet may exceed it, each inside its own horizontally scrolling container.
- **Mobile collapse:** Everything to one column below 768px. Stat rows go 2×2, never a single row of four. No horizontal page scroll at 390px.
- **Tap targets:** Minimum 44×44px for every interactive element — including the logo, the hamburger, filter rows and removable chips.
- **z-index contract:** base (0) / sticky-nav (100) / sticky-cta (150) / overlay (200) / modal (300) / toast (500).

## Elevation & Depth

Depth comes from ground changes and 1px rules, not from shadow stacks. A page alternates navy and light bands; within a band, surfaces separate with a single hairline border and at most one soft shadow.

- **Physics:** Minimal. This is an infrastructure supplier, not a product launch.
- **Entry animations:** Fade + translate-Y (12px → 0) over 320ms ease-out. Nothing parked at opacity 0 waiting on a scroll observer — the page must read in a screenshot.
- **Hover states:** Border or background shift over 150ms. No scale, no lift on cards.
- **Page transitions:** None. Full page loads, fast.
- **Performance:** LCP under 2.5s on 4G. The clerk opens this on a phone, on a municipal network. Night photography is heavy — AVIF/WebP, sized variants, lazy loading everywhere except the hero.

## Shapes

Base corner radius: 2px. Near-square. Rounded corners read as consumer software; this system is closer to a datasheet than an app.

- Buttons: 2px
- Cards and surfaces: 0 (hairline border instead)
- Badges and chips: 2px
- Input fields: 2px

## Components

- **Primary Button:** Amber fill (#E9A23B), ink text, 2px radius, min-height 44px, weight 600. Reserved for the three conversion actions. Hover: 6% darken. Active: −1px translate. No glow.
- **Secondary / Ghost Button:** 1.5px border in muted grey, text in ink (light ground) or surface (dark ground). Hover: subtle fill. Never amber — it must lose to the primary.
- **Cards:** No radius, 1px border. Surface background. Shadow only where a card genuinely floats (0 2px 12px rgba(17,16,19,0.06)); otherwise the border does the work.
- **Stat tile:** Mono figure at 1.3rem+, tabular; uppercase mono caption beneath at 0.625rem. Used for counts, kilowatts, forint figures. One tile per band may take the amber treatment.
- **Data table:** Uppercase mono header row on a tinted band, 1px cell borders, numeric cells in mono with tabular figures, right-aligned. This is the datasheet and the calculator's output.
- **Assumptions box:** Dashed 1.5px border, muted ground, mono badge reading the source. Attached to every figure that depends on a stated assumption. **Structural, not optional** — see Do's and Don'ts.
- **Inputs:** Label above field. 1px border, min-height 44px. Focus ring 2px accent, offset 2px. Error text below in semantic red. No floating labels.
- **Navigation:** Five items plus one amber CTA pill. Active item at weight 600. Reduced header (logo + phone only) on campaign landing pages.
- **Filter chips:** Mono, 2px radius. Active chip inverts to ink ground. A chip with zero matching content renders at 40% opacity and is not clickable — an empty result page is worse than a missing category.
- **Sticky mobile CTA:** Amber bar pinned to the bottom, appearing after 25% scroll. The primary action must be reachable by thumb.

## Do's and Don'ts

- No emoji anywhere — line icons only (Lucide or Heroicons), 1.5px stroke
- No pure black (#000000) — use #111013
- No stock photography. A manufacturer with 300 projects using stock imagery says it has nothing of its own
- No #4A81D3 for body text or links on light grounds — 3.9:1 fails AA; use #2F63AE
- No amber text on white — 2.2:1, decorative only
- No amber on anything that is not one of the three conversion points; a fourth amber button devalues the other three
- No countdown timers or urgency devices. A statutory deadline stated as a calendar fact is enough; pressure reads as untrustworthy to a public official
- No `h-screen` hero — use content height so the evidence band is visible on first paint
- No percentage without its assumption beside it: against what baseline, what operating hours per year, what energy price
- No unexplained technical acronym on a page aimed at a non-technical reader — expand it once, then use it
- No Hungarian marketing clichés: "forradalmi", "innovatív megoldás", "kulcsrakész", "egyedülálló", "prémium minőség"
- No lorem ipsum in mockups — the copy is the deliverable on this site

- Do set every measured value in monospace with tabular figures
- Do attach an assumptions box to every calculated figure
- Do alternate navy and light grounds by function, not by rhythm
- Do verify Hungarian diacritics in every face before building
- Do check the page in greyscale — it will be printed for council meetings
- Do keep one primary action per page, repeated, never three competing buttons
- Do write "214 lámpatest, 2023, higanylámpa kiváltása" rather than "számos sikeres projekt"

## Use Case

B2G municipal procurement, infrastructure manufacturer, technical product catalogue, decision-support content for non-technical public officials, long-lifecycle capital equipment.

<!-- Source: Hungaro Lux Light honlapterv v1.0 §06 · Uniquefield -->
