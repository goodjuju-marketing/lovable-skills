---
name: goodjuju-premium-craft
description: >-
  Use on every client website build or template elevation that must feel
  expensive, especially when starting from a template the client picked during
  onboarding. Not for internal tools or backend work.
---

# Premium craft standard

The client picked a starting template. It is a floor, not a ceiling — raise it until it reads
custom and expensive, in its own style. Work 0–13 in order; an audit cannot add craft that
was never built.

Tokens, type scale, banned fonts and the five-color rule come from
`goodjuju-design-direction`; required sections from `goodjuju-pm-website`.

## 0 — Read the template's DNA first

Amplify the direction the client chose; never blend a second one in. Print before editing:

```
DIRECTION: <editorial / warm analog / dark luxury / quiet premium / swiss / technical>
TYPE:      <display> / <body>      FLAG IF BANNED
PALETTE:   <colors + hex>          FLAG IF > 5
RHYTHM:    <padding, max-width, radius>
MOTION:    <timing + easing in use>
SIGNATURE: <the one memorable move — or "NONE, must add">
WEAKEST:   <three things dragging it down>
READ:      <sections in DOM> / <sections you could describe>
UNREAD:    <sections you could not parse — name them, never drop them>
```

**You cannot see the whole page.** Elementor holds elements at `opacity: 0` until scrolled
into view · tabs and carousels populate only the open panel or slide 1 · lazy blocks never
render cold · CSS backgrounds are absent from `document.images`. Scroll the full height, open
every panel and slide, read computed `background-image`. Then count DOM sections against the
ones you described; if they disagree, ask for a screenshot. Never drop or guess at a section
you could not read — raise it (§12).

Fix first, in the template's own style: banned font, >5 colors, flat color-block hero,
arbitrary spacing. Defects in any style. Reference build — Newton PM: Bricolage Grotesque /
Manrope / Fraunces sparingly, `#050505` `#F0E9E9` `#B35A30` `#3E5641`.

## 1 — Extend the tokens

Beyond the design-direction set: section padding tiers 64/96/128/160 · one radius plus a pill ·
one duration set and one easing curve · two shadows, a resting and a hover lift, never the
framework default. A value belonging to no scale is a bug.

## 2 — Win the first 50ms

The verdict forms in ~50ms and colors everything after. Name the one emotion the hero must
produce, then serve only that.

- Real photograph or video, **or** a deliberate type-led hero. Never a flat color block,
  gradient, or generic skyline.
- With a photo, a tinted directional overlay: `linear-gradient(135deg, rgba(20,18,16,.85),
  rgba(45,74,58,.65))`. Flat `rgba(0,0,0,.5)` is the most common cheap tell there is.
- Exactly one emphasized word in the headline.
- One primary CTA, at most one ghost secondary.
- One proof element visible without scrolling — rating, door count, years, credential.
- Four competing elements maximum.

A type-led hero is a commitment — oversized display type, real hierarchy, one strong
supporting element. A headline on a rectangle is unfinished, not type-led.

Banned above the fold: stacked badges, promo carousels, two competing offers, a cookie wall
over the headline. Nothing shifts on load — LCP <2.5s on a mid-range phone on 4G, CLS <0.1,
preload hero image and display font, WebP/AVIF with `srcset`, lazy below.

## 3 — Cut cognitive load

One job per section; three elements competing for focus means none wins · ask what can be
deleted, not added · nav is scaffolding, 7 items max, no mega-menu with promos · no two
adjacent sections share a background · one thought per paragraph, 2–4 sentences.

## 4 — Refine the type

Inconsistency, not any single wrong choice, is what reads cheap.

| Element | Tracking | Line-height | Weight |
|---|---|---|---|
| Display / H1 48–96 | −0.02 to −0.03em | 1.0–1.15 | 500–700 |
| H2 32–48 | −0.01 to −0.02em | 1.15–1.25 | 600–700 |
| Body 16–18 | 0 | 1.5–1.7 | 400 |
| Eyebrow 12–14 upper | +0.08 to +0.15em | 1.2 | 500–600 |
| Stat numeral 48–96 | −0.02em | 1 | 600, tabular |

Tighten as size grows — display at default tracking looks unset. Break headlines into 2–3
balanced lines (`text-wrap: balance`). Tabular figures on prices, stats, phone numbers. Never
letter-space lowercase body. Two faces plus one accent face used in three places or fewer.
Same H2 size on every page.

## 5 — Open up the space

Padding from the tier scale, top of the range for hero, primary CTA and proof · never crowd a
CTA or form · proximity is grouping, related tight and unrelated far · align everything, since
a few pixels off lowers perceived quality even when nobody can name why · break the grid
**once**, with a pull quote or an image bleeding off an edge. Total symmetry reads as a
template.

## 6 — Systematize the imagery

**Collection test:** line up every image. Same color temperature, lighting, depth of field,
treatment? If they look assembled, they read as assembled.

Best to worst: real client photos (team, office, managed properties, their city) → real local
photography → directed stock from one shoot with a unifying grade → **no image at all** →
generic stock.

One grade across all sourced images · consistent aspect ratio per component · one full-bleed
moment per page · real faces with real names and titles · custom SVG icons at 70–80px in a
service card, accent inside the icon's geometry, not a circle around it.

## 7 — Add the custom layer

Where one-of-a-kind is manufactured. **Ship at least four**, fitted to the direction:

- Logo mark at 3–6% opacity as a section watermark
- The mark as bullets, dividers, or eyebrow markers
- Numbered sections `01`–`06` on services, process, guarantees
- A slow marquee of services or cities, split by the brand mark
- A hand-drawn annotation on one headline word
- A drawn service-area map in brand colors, not a Maps embed
- Real place photography — the office, a managed property, a landmark
- A founder signature closing the About section
- A stat band at 72–96px where the numeral is the graphic

Four or five. All nine is noise.

## 8 — Tune the motion

Micro-interactions are the peaks people remember. One motion character site-wide; mixed
timings read as undesigned.

Hover 120–160ms · state change 200–250ms · scroll reveal 500–700ms, once · route transition
300–400ms. One easing curve: `cubic-bezier(.4,0,.2,1)`, or `cubic-bezier(.16,1,.3,1)` for
slower luxury. Reveal = opacity 0→1 plus `translateY(16–24px)`, staggered 60–80ms across 2–3
elements per viewport. Every interactive element needs hover, `focus-visible`, active. If an
animation doesn't communicate state, guide attention or reveal content, delete it.

**Design the end.** The footer is remembered as much as the hero: real content, a final proof
element, one clear last action. Never a dumped link list.

## 9 — Make the copy specific

Premium copy sounds like knowledge, not marketing.

| Vague | Specific |
|---|---|
| Fast, reliable service | Maintenance requests answered same business day |
| We market everywhere | Listed across 35+ channels including Zillow and Realtor.com |
| Trusted by many owners | Trusted by 90+ owners in the Tennessee Valley |

Weave the city and company name through body copy, not just headlines — scrub the names out,
and if what's left fits any company in any city, rewrite it. Micro-copy carries craft:
reassurance under a CTA ("Takes under 60 seconds"), helper text, useful empty states, buttons
naming the outcome ("Get my rental estimate," never "Submit").

## 10 — Build trust, then ask once

Real or absent, never invented: testimonials with full name, photo (or initial fallback),
platform badge and date, carousel past three · credentials as **badge graphics**, not text
pills · a stat band of real numbers · named guarantees with terms · real team faces.

One primary conversion action, worded identically, repeated 3–5 times: hero, after proof,
mid-page, before footer. The form gets value bullets beside it, few fields, and a reassurance
line under the button. Tap-to-call in the mobile header.

## 11 — Carry it to every page

A homepage at 9 and a services page at 5 averages to 5 — the inconsistency is the signal.
**Second-page test:** open an interior page cold; is it as designed as the homepage? Blog and
service-detail pages are where premium dies. Identical padding tiers, H2 size, card style,
image treatment and motion on every route. Design the 404, form success and error, empty and
loading states. Constrain any CMS so it can't drift.

## 12 — Request what's missing

Never invent a statistic, testimonial, award or credential. Never quietly drop a section or
leave an unlabeled gray box. Build a labeled placeholder and raise the request the moment you
know:

```
NEEDED TO HIT THE PREMIUM BAR
ITEM:     <what is missing>
FOR:      <which section it unblocks>
WHY:      <which criterion fails without it>
FALLBACK: <what is standing in for it now>
```

Highest impact first: real photos · real numbers (doors, years, renewal and eviction rate,
days to lease) · 3–6 real reviews with names and platform · guarantees honored, with terms ·
full list of cities served · logo as SVG. Restate every open item at handoff.

## 13 — Self-audit, then fix

Do not report done until you have scored the build. Run the **Premium Scorecard** in
`goodjuju-prelaunch-audit` — twelve dimensions matching §§0–12, scored 1–5. Anything under 4
gets fixed, not explained; re-score and repeat. Under 48/60 is not client-ready.

## Instant fails

Beyond the never-ship list in workspace knowledge: a flat `rgba(0,0,0,.5)` scrim over a hero
photo · a headline on a colored rectangle passed off as a type-led hero · fewer than four
custom touches from §7 · an interior page visibly less designed than the homepage · a section
silently dropped because it was invisible to an automated read.
