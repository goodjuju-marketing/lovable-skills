---
name: goodjuju-pm-website
description: >-
  Use when building or rebuilding a website for a residential property
  management client — homepage, about, services, or contact pages. Enforces the
  required section checklist, owner-facing copy standards, and site-wide items
  that must exist on every Goodjuju build. Not for blog posts, landing pages, or
  internal tools.
---

# Property management website build

The audience is **rental property owners and investors** deciding who manages
their asset — not tenants. Every heading, stat, and section speaks to that person.

This is a literal checklist, not a starting point. Work it item by item against
the actual rendered pages before calling anything done. Do not wait to be told a
section is missing.

Pair with `goodjuju-design-direction` — lock the art direction first, then build
these sections in that direction's visual language.

## Homepage — every item required

- [ ] Hero
- [ ] About preview
- [ ] Services grid
- [ ] Differentiators / "why us"
- [ ] **Guarantees** — real, currently-honored commitments only
- [ ] **Track Record** — a stats band (units managed, happy owners, eviction rate,
      renewal rate) plus real case-study/results cards
- [ ] **Testimonials** — real Google reviews, with a Google "G" badge for authenticity
- [ ] **"More About [Company]"** — centered dark section, logo + 2 paragraphs of real
      company overview
- [ ] **Areas We Serve** — pill list of *every* real nearby city served, not 2–3
- [ ] FAQ
- [ ] CTA banner with an **embedded lead-capture form** — client-side only is fine,
      but it must be a real form, not a button
- [ ] Blog preview

## About page

Hero · founding story · stats band (years in business, properties managed, eviction
rate, renewal rate) · values/philosophy cards · leadership (render only if real bios
exist — guard on length) · recognition and credentials (real memberships only —
NARPM, NAR, Equal Housing. Never fabricate an award.)

## Services page

Hero · services grid using **custom SVG icons in the site's established icon style**
(e.g. navy circle + accent-color line icon) — never stock photos, they're hard to
source and look cheap · impact stats + testimonials · process steps

## Contact page

Hero · real contact form · areas served · FAQ

## Site-wide — every build

- [ ] JSON-LD schema (`LocalBusiness` + `RealEstateAgent`); most templates ship none
- [ ] **Portal Login** in the header nav — Owner and Tenant links (AppFolio or the
      client's actual portal)
- [ ] Footer: `Websites and marketing for property managers by` +
      **Goodjuju Marketing** linked to `https://gogoodjuju.com`. Replace any
      template-author or framework credit.
- [ ] `color-scheme: light` and an explicit `body` background — without it,
      dark-mode browsers render unstyled sections black
- [ ] Full leftover-content sweep before ship (see below)

## Copy standard — no generic headings

Every heading names the actual industry and value prop. Reject anything that could
apply to any business.

| Never | Instead |
|---|---|
| What We Offer | Everything Your Rental Property Needs, Handled by One Team |
| Our Services | Full-Service Management, From Listing to Renewal |
| Why Choose Us | Why Owners Move Their Doors to Us |
| Get Started Today | Talk to Someone Who Manages in [City] |
| Let's Start the Conversation | See What Your Property Should Be Renting For |

Short eyebrow labels above a heading ("Our Services", "Our Values") may stay
generic — the heading underneath carries the specificity. The bar applies to the
heading, not every small UI label.

## Leftover-content sweep — pixels, not just strings

A text grep is not enough. Off-brand imagery hides where a copy pass never looks.
Before shipping, walk every image actually rendered on every page type — hero,
about, services grid, service detail, blog list, blog detail, sidebars, footer —
and **look at each one**. Confirming a variable was reassigned is not confirming
the pixels changed.

Specifically check:

- Decorative sidebar banners with marketing text baked into the image
- Small "why choose us" thumbnails
- One hardcoded image import reused across every dynamic detail route — fixing the
  data per item never touches these
- "Decorative" low-opacity background shapes that turn out to be a recognizable
  symbol from the template's original industry
- `.svg` files — old brand hex values and literal themed icons both hide there;
  include SVGs in every color grep
- Hardcoded template emails, addresses, and brand names inside components, not
  just in data files

Then delete orphaned assets.

## Data honesty

Real stats or no stats. Real reviews or no reviews section. Real credentials or
none. If the client hasn't supplied a number, write a clearly labeled placeholder
and list it in your handoff — never invent a figure, a testimonial, or an award.

## Before you call it done

Go through every checkbox above against the live rendered pages one at a time —
"something conceptually adjacent exists" does not count. If the design direction
has no natural slot for a required section, build one in that direction's own
visual style rather than skipping it. Every item ships on every build.
