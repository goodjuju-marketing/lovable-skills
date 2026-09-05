---
name: goodjuju-premium-craft
description: >-
  Use on every client website build, template elevation, or redesign that has to
  feel expensive — especially when starting from a template the client picked
  during onboarding. Covers the craft layer that separates a $15K site from a
  competent one: first-impression control, cognitive load, typographic
  refinement, photography as a system, motion coherence, one-of-a-kind brand
  touches, conversion architecture, the missing-inputs protocol, and a scored
  self-audit you run on your own work before reporting done. Not for internal
  tools, backend work, or bug fixes.
---

# Premium craft standard

A client paid, filled out onboarding, and picked a starting template from a handful
of styles. That template is a **floor, not a ceiling.** Your job is not to redesign
it and not to fill it in — it is to raise it until it reads as custom, one-of-a-kind,
and expensive, in its own style.

Premium is not a style. It is a set of signals a visitor registers without
articulating. This skill is the list of those signals and the order to apply them.

**The 10/90 rule:** a specific 10% of decisions carry 90% of the perception. This
document is that 10%. Work it in order.

Pair with `goodjuju-pm-website` (which sections must exist) and finish with
`goodjuju-prelaunch-audit` (technical gate). This skill is the craft layer between
them. Where `goodjuju-design-direction` picks a direction from scratch, this skill
starts from a direction that already exists in the template.

---

## The pathway

```
0  Read the template's DNA      →  never fight the style the client chose
1  Lock the system              →  tokens before components
2  Win the first 50ms           →  the hero decides the verdict
3  Cut cognitive load           →  one job per section
4  Refine the type              →  the highest-leverage craft pass
5  Open up the space            →  whitespace reads as confidence
6  Systematize the imagery      →  the single biggest lever after type
7  Add the custom layer         →  where "one-of-a-kind" is manufactured
8  Tune the motion              →  peaks people remember
9  Make the copy specific       →  vagueness is the loudest cheap signal
10 Build trust + conversion     →  proof, then one clear action
11 Carry it to every page       →  premium is a system property
12 Request what's missing       →  never invent, never silently downgrade
13 Self-audit and fix           →  score your own work, then fix what scored low
```

Do not skip to 13. An audit cannot add craft that was never built.

---

## 0 — Read the template's DNA before you touch anything

The client chose this look. Amplify it; do not replace it. A premium site is one
direction executed without flinching — blending a second direction is the fastest
way to make an expensive template look cheap.

Starting points come from one of two places, and they give you different access:

| Source | What you get | How to read it |
|---|---|---|
| **A Goodjuju style** — one of our own builds the client picked from a handful | Full source: tokens, fonts, components | Read the code. The DNA is literal. |
| **A site the client brought** — they fell in love with something | A live URL only | Read it visually, and see the blind-spot warning below |

Before the first edit, print this block:

```
TEMPLATE DNA
DIRECTION:   <editorial / warm analog / dark luxury / quiet premium / swiss / technical>
TYPE:        <display face> / <body face>          FLAG IF BANNED
PALETTE:     <every color actually used + hex>     FLAG IF > 5
RHYTHM:      <section padding values, container max-width, corner radius>
MOTION:      <timing + easing the template already uses>
IMAGERY:     <photo style: full-bleed / cards / duotone / none>
SIGNATURE:   <the one memorable move — or "NONE, must add">
WEAKEST:     <the three things dragging it down>
READ:        <sections in DOM> found / <sections you could describe> read
UNREAD:      <any section you could not parse — name it, never drop it>
```

Then every decision from here amplifies that DNA. Newton Property Management is the
reference build for this: Bricolage Grotesque display + Manrope body + Fraunces used
sparingly, a four-color palette of near-black `#050505`, warm off-white `#F0E9E9`,
terracotta `#B35A30`, deep green `#3E5641`, pill buttons, uppercase eyebrows at 5px
tracking, numbered service cards. One direction, held everywhere.

### You cannot see the whole page — assume that

Elementor and similar page builders routinely hide real sections from an automated
read. This is the most common way a rebuild silently loses content.

What goes missing, and what to do about it:

| Hidden by | Why you miss it | How to reach it |
|---|---|---|
| Entrance animations | Elementor holds elements at `opacity: 0` until scrolled into view — the section reads as empty, not absent | Scroll the full page height first, then read |
| Tabs, accordions, toggles | Only the open panel is populated | Open every one and read each |
| Carousels and sliders | Only slide 1 is in the DOM | Step through every slide |
| Lazy-loaded blocks | Never render if you read the page cold | Scroll to the bottom, wait, re-read |
| CSS background images | Not in `document.images`, so an image-list read shows nothing | Read computed `background-image`, not just `<img>` tags |
| Sticky and scroll-triggered reveals | Fire on scroll position you never reached | Same — scroll the whole height first |

Then **count the sections in the DOM against the ones you can actually describe.**
If those numbers disagree, say so out loud. Ask for a full-page screenshot or a PDF
export of the sections you could not parse.

**Never omit a section because it was invisible to you, and never guess at its
contents.** A section you silently dropped is a section the client will notice is
gone. Raise it in the §12 format instead.

**Fix before proceeding, matching the template's feel:** a banned font, more than
five colors, a flat color-block hero, or arbitrary spacing values. These are not
style choices — they are defects in any style.

---

## 1 — Lock the system

Tokens first. Components consume tokens only. Zero raw hex inside a component.

| Token group | Rule |
|---|---|
| Color | 5 max: background, ink, muted ink, accent, surface/border |
| Type scale | Fixed: 12 / 14 / 16 / 18 / 24 / 32 / 48 / 72 / 96 |
| Spacing | 4/8 rhythm; section tiers 64 / 96 / 128 / 160 |
| Radius | One value plus a "pill" — not four different roundings |
| Motion | One duration set, one easing curve (see §8) |
| Shadow | Two: a resting lift and a hover lift. Never the framework default. |

If a value appears once and belongs to no scale, it is a bug.

---

## 2 — Win the first 50ms

A visitor forms a verdict in roughly 50 milliseconds, and the **halo effect** makes
that verdict color everything they read afterward. A weak hero poisons content that
is otherwise excellent. This is the most valuable real estate on the site — treat it
as the whole job, not the top of the page.

**Name the one emotion first.** Calm? Confidence? Local trust? Quiet authority?
Write it down. Every hero decision serves that one word.

Required in the first viewport:

- [ ] A **real photograph or video** — the actual property, team, office, or city —
      **or a deliberate type-led hero.** Never a flat color block, never a gradient,
      never a generic skyline.
- [ ] When there is a photo: a **tinted, directional overlay** — not a flat black
      scrim. Two stops carrying brand color, e.g. `linear-gradient(135deg,
      rgba(20,18,16,.85) 0%, rgba(20,18,16,.55) 60%, rgba(45,74,58,.65) 100%)`. Flat
      `rgba(0,0,0,.5)` is the single most common cheap tell in a hero.
- [ ] A headline where **exactly one word** carries emphasis (accent color, weight
      shift, or a hand-drawn underline). Not the whole line.
- [ ] **One** primary CTA. At most one ghost secondary beside it.
- [ ] **One proof element visible without scrolling** — star rating, door count,
      years in business, or a credential badge.
- [ ] Four elements maximum competing for attention. Count them.

**A type-led hero is a commitment, not a fallback.** It earns its place through
oversized display type, real editorial hierarchy, and one strong supporting element —
a rule system, a stat, a single credential. A colored rectangle with a headline
centered in it is not a type-led hero; it is an unfinished one. If you cannot name
why the type alone carries the viewport, you need a photograph.

Banned above the fold: stacked badges, a carousel of promos, two competing offers,
autoplaying audio, a cookie wall covering the headline, a slider whose second slide
nobody sees.

**Technically, the hero must not flinch.** Layout shift while loading is the most
jarring anti-premium experience there is.

- LCP under 2.5s on a mid-range phone on 4G — not on your machine
- CLS under 0.1; every image, embed, and font-swapped headline has reserved space
- Preload the hero image and the display font
- Hero image served as WebP/AVIF with `srcset`, everything below the fold lazy

---

## 3 — Cut cognitive load

The brain treats effort as a cost and reads ease as a quality signal. This is
**cognitive fluency**: a site that is easier to process is judged as better made and
more trustworthy — not because it is, but because processing felt effortless.

- **One job per section.** If three elements compete to be the section's primary
  focus, none of them wins and the section reads as noise.
- **The removal test.** For each section ask what can be deleted, not what can be
  added. Deciding what matters and removing everything that dilutes it *is* the work.
- **Navigation is scaffolding, not a pitch.** Seven top-level items maximum. No
  mega-menu with promo images and secondary CTAs. Predictable to the point of boring
  is correct.
- **Scroll rhythm.** No two adjacent sections share the same background treatment.
  Alternate: light → dark full-bleed → light → image-backed → light. The page should
  read as chapters with a deliberate cadence, not a stack of white boxes.
- **One thought per paragraph**, 2–4 sentences. Walls of text read as unedited.

---

## 4 — Refine the type

Typography is the highest-impact improvement available for the least effort, and
**inconsistency — not any single wrong choice — is what reads as cheap.** Body text
that changes size between sections, headings that don't follow a scale, and weights
used interchangeably are the tell.

| Element | Size | Tracking | Line-height | Weight |
|---|---|---|---|---|
| Display / H1 | 48–96 | −0.02 to −0.03em | 1.0–1.15 | 500–700 |
| H2 | 32–48 | −0.01 to −0.02em | 1.15–1.25 | 600–700 |
| H3 | 24 | 0 | 1.3 | 600 |
| Body | 16–18 | 0 | 1.5–1.7 | 400 |
| Eyebrow / label | 12–14 uppercase | +0.08 to +0.15em (3–5px) | 1.2 | 500–600 |
| Stat numeral | 48–96 | −0.02em | 1 | 600, tabular |

Craft rules:

- **Tighten as size grows.** Display type set at default tracking looks unset.
- **Break headlines deliberately** into 2–3 balanced lines (`text-wrap: balance`, or
  an explicit break at desktop). Ragged auto-wrapped headlines read as unconsidered.
- **Tabular figures** on every price, stat, phone number, and numeric column.
- Body measure 60–75 characters desktop, 35–60 mobile. Wider is unreadable and looks
  like a text dump.
- Never letter-space lowercase body text. Only uppercase labels get tracking.
- Two faces, plus at most one accent face used in **three places or fewer** on the
  whole site (Newton uses Fraunces exactly this way).
- The same H2 size everywhere on every page. One exception is a system; three is a
  mess.

---

## 5 — Open up the space

Generous whitespace signals confidence — a brand that does not need to shout. Cramped
layouts read as a business trying to fit everything in before you leave.

- Section padding from the tier scale: 96 / 128 / 160 desktop, 64 / 80 mobile. Use the
  **top of the range** for the hero, the primary CTA, and any section carrying proof.
- Never crowd a CTA or a form. The highest-intent areas get the most air.
- **Proximity is grouping.** Related elements sit tight; unrelated ones get real
  distance. Even gaps everywhere means nothing is grouped.
- **Align everything.** A few pixels off measurably lowers perceived quality even
  when the viewer can't name what's wrong.
- One container max-width, used everywhere, with consistent gutters.
- **Break the grid deliberately exactly once** — an oversized pull quote, a headline
  that runs past the container, an image bleeding off one edge. Perfect symmetry
  everywhere reads as a template; one intentional break reads as designed.

---

## 6 — Systematize the imagery

Photography does more work for the premium impression than almost anything else. A
site with excellent photography and average design beats excellent design with average
photography. The goal is that the images look like **one collection**, not a library.

**The collection test:** put every image on the page side by side. Do they share
color temperature, lighting, depth of field, and treatment? If they look assembled
from different sources, they will read as assembled, no matter how good each one is.

Ranked, best to worst:

1. Real client photos — their team, office, actual managed properties, their city
2. Real local photography of the service area (recognizable, not a generic skyline)
3. Directed stock, all from one shoot, with a unifying color grade applied
4. **No image at all** — a type-led section is premium; a bad photo never is
5. Recognizable generic stock — worse than nothing

Rules:

- Apply a single grade across all sourced images so they belong to one world.
- Consistent aspect ratio per component. Cards do not mix 4:3 and 16:9.
- At least one **full-bleed** image moment per page.
- Real faces with real names and titles. A stock "team" on an About page is the
  fastest way to lose an owner's trust.
- Custom SVG icons: one family, one stroke width, sized generously (70–80px in a
  standalone service card). Put the accent color **inside** the icon's geometry — one
  filled detail — rather than wrapping a flat icon in a colored circle.
- Never: laptop-and-coffee, team high-five, glass skyline, handshake, stock "happy
  family," or an emoji standing in for an icon.

---

## 7 — Add the custom layer

This is where one-of-a-kind is manufactured. Everything above makes a site *good*;
this section is what makes it look like it was designed for this client and nobody
else. **Ship at least four of these, chosen to fit the template's direction.**

| Touch | How |
|---|---|
| **Logo watermark** | The client's logo mark, oversized, at 3–6% opacity behind a dark section or bleeding off a section edge |
| **Mark as ornament** | The logo's icon reused as list bullets, section dividers, or the marker between eyebrow and heading |
| **Numbered sections** | `01`–`06` in mono or display type on services, process, guarantees |
| **Marquee strip** | A slow horizontal ticker of services or cities served, separated by the brand mark |
| **Brand-shape masking** | The logo's geometry used as an image mask or frame on one hero or portrait |
| **Hand annotation** | One headline word circled or underlined in a hand-drawn accent stroke |
| **Custom service-area map** | A drawn map of the actual counties/cities in brand colors — not a Google Maps embed |
| **Real place photography** | The actual office exterior, a real managed property, a recognizable local landmark |
| **Founder signature** | A handwritten signature image closing the About or letter section |
| **Display-type stat band** | Real numbers set at 72–96px — the numeral is the graphic |
| **Brand pattern** | A repeating pattern derived from the logo, used at low opacity on one section |

Pick 4–5. Shipping all eleven is noise — restraint is the point.

---

## 8 — Tune the motion

People do not remember an average of an experience. They remember its **peaks and its
end** (the peak–end rule). Micro-interactions are engineered peaks — each satisfying
hover, smooth reveal, and well-timed transition is a small positive spike, and those
spikes are what a visitor carries away as a sense of craft.

Static, lifeless sites feel cheap because nobody asked how the page feels to touch.

**One motion character for the whole site.** Mixed timings and easings read as
undesigned even when each animation is fine on its own.

| Interaction | Duration | Notes |
|---|---|---|
| Hover (buttons, links, cards) | 120–160ms | Fast enough to feel connected to the cursor |
| State change (open, toggle, active) | 200–250ms | |
| Section reveal on scroll | 500–700ms | Once, never repeating |
| Page / route transition | 300–400ms | |

- **One easing curve** site-wide. `cubic-bezier(0.4, 0, 0.2, 1)` as default;
  `cubic-bezier(0.16, 1, 0.3, 1)` for a slower luxury feel.
- **Transform and opacity only.** Never animate width, height, top, or left.
- Reveal = opacity 0→1 plus `translateY(16–24px)`, fired once, staggered 60–80ms
  across at most 2–3 elements per viewport. Fade-up on every element in the page is
  an instant tell.
- **Every interactive element needs three states:** hover, `focus-visible`, and
  active/pressed. Missing focus states are both an accessibility failure and a
  craft failure.
- Form fields animate their focus state. Buttons depress. Valid input confirms.
- **Functional over decorative.** If an animation does not communicate state, guide
  attention, or reveal content, delete it — it is cognitive load with no payoff.
- Honor `prefers-reduced-motion`.
- **Design the end.** The peak–end rule means the last viewport and the footer are
  remembered as much as the hero. A designed footer with real content, a final proof
  element, and a clear last action — never a dumped link list.

---

## 9 — Make the copy specific

A beautiful site with generic copy is a premium shell with a default interior, and
visitors feel it immediately. Premium copy **sounds like knowledge**, not like
marketing. Vague superlatives signal that the business either cannot describe what it
does or does not trust the specifics to carry the weight.

- **Specificity is the entire trick.** Real numbers, real place names, real
  timeframes, real process detail, real tool names.
- Weave the city and company name through **body copy repeatedly**, not just
  headlines. Scrub the names out — if what's left could belong to any company in any
  city, rewrite it.
- Micro-copy is where craft shows: reassurance under a CTA ("Takes under 60 seconds.
  Results sent instantly."), helper text under fields, useful empty states, button
  labels that name the outcome.
- One voice site-wide — calm, authoritative, consultative. Never bro-marketer energy.

| Vague | Specific |
|---|---|
| Fast, reliable service | Maintenance requests answered same business day |
| We market your property everywhere | Listed across 35+ channels including Zillow, Realtor.com, and Apartments.com |
| Trusted by many owners | Trusted by 90+ owners across the Tennessee Valley |
| Quality tenant screening | Credit, criminal, eviction history, income verification at 3x rent, and prior-landlord references |
| Competitive pricing | 10% of monthly rent, full service, every fee listed in the agreement |
| We'll get back to you soon | Follow-up call within minutes from a licensed manager |

Generic headings stay banned — "What We Offer," "Our Services," "Why Choose Us,"
"Get Started Today." Short eyebrow labels above a heading may stay generic; the
heading beneath must carry the specificity.

---

## 10 — Build trust, then ask once

Proof earns the right to ask. Ask before proving and the CTA reads as pushy; prove
without asking and the visit dead-ends.

**Trust signals — real or absent, never invented:**

- Testimonials with a full name, a photo (or a colored-initial fallback), the source
  platform's badge, and a date. Past three, use a carousel, not a wall.
- Credentials as **badge graphics** — Equal Housing, NARPM, NAR, BBB. A styled text
  pill reads as a claim; a graphic reads as evidence.
- A stat band with real numbers set in display type.
- Named guarantees with actual terms.
- Real team faces with real titles.
- "As seen in" / "trusted by" only when it is true.

**Conversion architecture:**

- **One** primary conversion action for the whole site, worded identically every time.
- Repeat it 3–5 times: hero, after the proof section, mid-page, before the footer.
- The primary form gets value bullets beside it, a short field count, and a
  reassurance line beneath the button.
- Every CTA names the outcome, not the mechanic — "Get my rental estimate," never
  "Submit."
- Tap-to-call phone number in the mobile header. Owner/Tenant portal logins in the
  utility bar.

---

## 11 — Carry it to every page

**Premium is a system property.** The thing that most reliably separates premium from
nearly-premium is consistency held across every page, not just the high-attention
ones. A homepage at a 9 and a services page at a 5 averages to a 5, because the
inconsistency itself is the signal.

- **The second-page test:** open any interior page cold. Is it as designed as the
  homepage? Blog, service detail, and legal pages are where premium quietly dies.
- Identical section padding tiers, H2 size, card style, image treatment, button
  style, and motion character on every route.
- Design the overlooked states: 404, form success, form error, thank-you page, empty
  states, loading states.
- Favicon, per-route title and meta description, and a real OG preview image.
- Where a CMS or client editing exists, constrain it — apply the system through the
  template so it cannot drift as content is added later.

---

## 12 — Request what's missing (do not invent, do not downgrade)

You will regularly hit the criteria above without the inputs to satisfy them. When
that happens: **build the section with an honest, clearly labeled placeholder, and
raise a request immediately** — the moment you know, not at handoff.

Never invent a statistic, testimonial, award, or credential. Never quietly drop a
required section because the content is missing. Never leave an unlabeled gray box.

Raise it in this format:

```
NEEDED TO HIT THE PREMIUM BAR
ITEM:     <what is missing>
FOR:      <which section it unblocks>
WHY:      <which criterion fails without it>
FALLBACK: <what is on the page right now in its place>
```

Commonly needed, roughly in order of impact:

1. Real photos — team, office exterior, actual managed properties, local landmarks
2. Real numbers — doors managed, years in business, owners served, renewal rate,
   eviction rate, average days to lease
3. 3–6 real reviews with reviewer names and the source platform
4. The guarantees the company actually honors, with terms
5. The complete list of cities/counties served
6. Logo as SVG, in light and dark versions
7. Brand colors and fonts, if they exist
8. Owner and tenant portal URLs
9. Memberships and credentials (NARPM, NAR, Equal Housing, licenses)
10. Pricing tiers and what each includes
11. Founder story and a headshot
12. The one thing this company does that competitors in their market do not

Restate every outstanding item in the handoff, with what is currently standing in.

---

## 13 — Self-audit, then fix

**Do not report a build as done until you have run this on your own work and printed
the scorecard.** You built it, so you are the wrong person to trust — which is why
this is scored rather than a yes/no.

First, three fast perceptual passes:

- **Screenshot test.** Capture the page at 1440 and at 375. Does any single viewport
  look accidental, empty, or crowded? A premium site survives being frozen anywhere.
- **Squint test.** Blur your view of each section. Is there one obvious focal point,
  or a field of equal-weight noise?
- **Cold-visitor test.** Read it as an owner who has never heard of this company. In
  the first 5 seconds: who is this, what do they do, where, and what do I do next?

Then score each dimension 1–5. **Anything under 4 gets fixed, not explained.**

| # | Dimension | 5 = |
|---|---|---|
| 1 | Direction held | One direction executed everywhere, never diluted |
| 2 | First 50ms | Real image with tinted overlay (or a committed type-led hero), one emphasized word, one CTA, visible proof |
| 3 | Cognitive load | One job per section; nav is boringly clear; nothing to delete |
| 4 | Typography | Scale held site-wide, display tracking tightened, headlines broken deliberately |
| 5 | Space & alignment | Generous, on-grid, one deliberate break |
| 6 | Color | ≤5 tokens, accent on under 10% of the page, tinted not flat overlays |
| 7 | Imagery | Passes the collection test; real over stock; no banned image |
| 8 | Custom layer | 4+ brand touches from §7 actually shipped |
| 9 | Motion | One timing set, one curve, hover + focus + active on everything, designed footer |
| 10 | Copy specificity | Real numbers and place names in body copy; nothing generic survives |
| 11 | Trust & conversion | Real proof, one repeated CTA, form with reassurance |
| 12 | Cross-page consistency | Interior pages match the homepage exactly |

Fix everything under 4, re-score, and repeat. Only then print:

```
PREMIUM SCORECARD
1 Direction .......... _/5      7 Imagery ............ _/5
2 First 50ms ......... _/5      8 Custom layer ....... _/5
3 Cognitive load ..... _/5      9 Motion ............. _/5
4 Typography ......... _/5     10 Copy specificity ... _/5
5 Space & alignment .. _/5     11 Trust & conversion . _/5
6 Color .............. _/5     12 Cross-page ......... _/5

TOTAL: __/60          SIGNATURE MOVE: <what it is>
CUSTOM TOUCHES SHIPPED: <list the 4+>
FIXED THIS PASS: <what you changed after the first score>
STILL NEEDED FROM CLIENT: <the §12 list, or none>
```

Under 48/60 is not ready to show a client. Do not soften a score to reach a number,
and do not score a dimension you did not actually check.

---

## Instant fails

Any one of these means the build is not premium, whatever else is right:

- Flat color-block or gradient hero — a headline centered on a colored rectangle is
  not a type-led hero, it is an unfinished one
- Flat black `rgba(0,0,0,.5)` scrim over a hero photo
- A banned font as a brand face — Inter, Roboto, Open Sans, Poppins, Montserrat,
  Lato, Nunito, raw system-ui
- Three cards in a row, each with a default Lucide icon in a pastel rounded square
- Emoji used as icons
- Fade-up animation on every section
- Invented stats, testimonials, awards, or client logos
- Generic headings that could belong to any business
- Recognizable generic stock photography
- Layout shift on load, or a hero that reflows when fonts arrive
- Missing focus states
- An interior page visibly less designed than the homepage
- Template-author or framework credit left in the footer, instead of "Websites and
  marketing for property managers by Goodjuju Marketing"
- A section from the reference site silently dropped because it was invisible to an
  automated read
