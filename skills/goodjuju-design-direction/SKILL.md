---
name: goodjuju-design-direction
description: >-
  Use when starting a new page, site, or major visual redesign, or when a build
  looks generic and needs a point of view. Forces a committed art direction,
  a non-default type pairing, a restrained palette, and one signature move
  before any component is written. Not for bug fixes, copy edits, or backend work.
---

# Design direction lock

Nothing gets built until Steps 1–5 are answered and printed. A design decided
mid-build is a template with extra steps.

Output the completed **Design Brief** (Step 6) in chat before your first file edit.

## Step 1 — Commit to a direction

Pick exactly one. Do not blend two. Do not invent a ninth without saying why.

| Direction | Type | Color | Space | Motion | Imagery |
|---|---|---|---|---|---|
| **Editorial** | Serif display, huge; sans body | Off-white, ink, one accent | Wide margins, asymmetric | Almost none; text reveals | Documentary photography |
| **Dark luxury** | High-contrast serif or thin grotesk | Near-black, warm metallic, cream | Generous, centered | Slow fades, 600ms+ | Moody, low-key, full-bleed |
| **Swiss / archival** | Grotesk only, tight scale | Black, white, one primary | Strict grid, visible rules | None | Duotone or none |
| **Brutalist** | Oversized grotesk, raw weights | 2 colors, high clash | Dense, edge-to-edge | Instant, no easing | Raw, unretouched, or none |
| **Warm analog** | Humanist serif + rounded sans | Sand, clay, ochre, forest | Soft, breathing | Gentle springs | Film grain, natural light |
| **Technical** | Grotesk + mono accents | Slate, one signal color | Modular, data-dense | Precise, 150ms | Diagrams, screenshots, none |
| **Retro-modern** | Geometric display, wide tracking | Muted 70s tertiaries | Banded horizontal sections | Marquee, staggered | Illustrated or grainy |
| **Quiet premium** | Refined sans, restrained scale | Near-monochrome + 1 muted accent | Very generous | Barely-there | Sparse, commissioned-feel |

For property management clients, **Warm analog**, **Editorial**, and **Quiet premium**
convert best with rental-property owners. **Brutalist** and **Retro-modern** almost
never fit — use them only when the client's existing brand already goes there.

## Step 2 — Lock the type pairing

Banned outright — these read as default AI output: **Inter, Roboto, Open Sans,
Poppins, Montserrat, Lato, Nunito, raw system-ui as a brand face.**

Load Fontshare via `https://api.fontshare.com/v2/css?f[]=satoshi@400,500,700&display=swap`
and Google Fonts normally.

| Direction | Display | Body |
|---|---|---|
| Editorial | Instrument Serif · Newsreader | Satoshi · General Sans |
| Dark luxury | Bodoni Moda · Bespoke Serif | Archivo · Switzer |
| Swiss / archival | Clash Display · Archivo | Switzer · Schibsted Grotesk |
| Brutalist | Clash Display · Bricolage Grotesque | Space Grotesk |
| Warm analog | Fraunces · Gambetta | General Sans · Figtree |
| Technical | Space Grotesk | Satoshi + JetBrains Mono |
| Retro-modern | Bricolage Grotesque · Cabinet Grotesk | Onest · Manrope |
| Quiet premium | Instrument Sans · Cabinet Grotesk | Satoshi |

Fixed scale, no arbitrary sizes: 12 / 14 / 16 / 18 / 24 / 32 / 48 / 72 / 96.
Body 16px minimum (18px on marketing pages). Line-height 1.5–1.75. Measure 60–75
characters desktop, 35–60 mobile. Headings 600–700, body 400, labels 500.
Tabular figures on prices, stats, and any numeric column.

## Step 3 — Lock the palette

Three to five colors total. Premium signals through restraint, not decoration.

Recipe: one background, one foreground, one muted foreground, one accent, one
surface/border. That's it. If you want a sixth, delete one first.

Every value is an HSL semantic token in `src/index.css`, mapped in
`tailwind.config.ts`. **Never a raw hex inside a component.** If you type
`text-[#1a1a1a]`, stop and add a token.

Derive client palettes from the client's actual brand. Goodjuju orange `#ff7c05`
is for Goodjuju's own properties only — never on client work.

Dark mode uses desaturated tonal variants, never inverted values, and its
contrast gets verified on its own. Functional color always ships with an icon or
label; color alone never carries meaning.

## Step 4 — Name the signature move

One idea a designer would actually notice. Exactly one — five is noise.

Examples: an oversized editorial headline that breaks the grid · a sticky
scroll-revealed stat band · a full-bleed duotone portrait · a typographic pull
quote set at display size · a horizontal rule system that indexes the page ·
numbered section markers in mono · a hero with no image at all.

Not a signature move: a gradient, a card grid, an icon row, a testimonial slider.

## Step 5 — Write the tokens first

Before any component: define color tokens, the type scale, the spacing scale
(4/8px rhythm, section tiers 16/24/32/48/64/96), radius, and a z-index scale
(0/10/20/40/100). Components consume tokens only.

## Step 6 — Print the Design Brief

```
DIRECTION:  <one of the eight> — <one sentence on why it fits this client>
TYPE:       <display> / <body>
PALETTE:    <5 tokens with hex + role>
SIGNATURE:  <the one move>
MOBILE:     <what is genuinely different at 375px, not just narrower>
```

Then build.

## Never ship

- Purple-to-blue gradient hero. Any gradient hero.
- Three feature cards in a row, each with a Lucide icon in a pastel rounded square.
- Emoji as icons.
- Stock photos everyone has seen — laptop-and-coffee, team high-five, glass skyline.
  Generic stock is worse than no image.
- Fade-up on every section. Animate 1–2 elements per view, transform/opacity only.
- Lorem ipsum, invented testimonials, fake client logos, made-up stats. Missing
  content gets honest labeled placeholders.
- Generic headings — "What We Offer", "Our Services", "Why Choose Us", "Get Started
  Today". Headings name the specific business promise: "We fill your vacancy in 21
  days, or we cover the month."

## Mobile is designed, not shrunk

Different type scale, different section order, different image crops, secondary
content folded away. Verify at 375px explicitly. This is where cheap sites collapse.

## Stop conditions

Do not proceed if you cannot name the direction, if the pairing includes a banned
font, if the palette exceeds five colors, or if there is no signature move. Say
which one is missing and ask for it.
