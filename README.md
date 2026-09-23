# HLL Design System

Design system for the Hungaro Lux Light (hungarolux.hu) website rebuild, in the
`designmd.app` markdown format so it can be loaded into Claude Design.

## Which file to load

**`HLL-design-system.md`** — this is the one. Palette lifted from the live
hungarolux.hu stylesheet, extended with two missing values (a link blue that
passes contrast on white, and the amber already present in the hero imagery).
Typography, layout, components and rules come from the honlapterv v1.0 §06
specification.

| Token | Value | Role |
|---|---|---|
| Éjkék | `#12132C` | Dark ground — hero, evidence bands, reference headers |
| Mélykék | `#222E66` | Secondary surface on the dark ground |
| Kék akcent | `#4A81D3` | Links and buttons **on dark only** (4.6:1) |
| Kék sötét | `#2F63AE` | Links on light grounds (6.0:1) |
| Borostyán | `#E9A23B` | The single warm accent — conversion elements only |
| Szürke | `#797A8C` | Captions, metadata, assumptions |
| Világos alap | `#F8F9FA` | Reading ground |
| Tinta | `#111013` | Body text on light |

Type: **Archivo** (display, 700) · **Inter** (body) · **IBM Plex Mono**
(measured values, labels).

Governing rule: **dark grounds are for persuasion, light grounds are for
reading.**

## `reference/aurora-ui-template.md`

Not the HLL system. This is the *Aurora UI* template downloaded from
designmd.app — magenta/cyan mesh gradients, system-ui type, aimed at premium
SaaS and creative tools. It is kept here only as a format reference for the
markdown structure Claude Design expects.

**Do not load it as the HLL design system.** Its palette, typography and motion
are the opposite of what this project specified.

## Source

- Honlapterv v1.0 — structure and design system specification
- Low-fi UX terv — the 8 templates this system dresses
- Tartalomstratégia v2.0 — positioning the system serves

Uniquefield · 2026
