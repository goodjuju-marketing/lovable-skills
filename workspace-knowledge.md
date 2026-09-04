# Goodjuju — Lovable Workspace Knowledge

Paste the block below into Lovable → Workspace knowledge. It applies to every project,
for every team member logged into the workspace.

Sources distilled into it:
- The $10K Checklist (Metics Media, Field Guide No. 01)
- ui-ux-pro-max skill: priority table, pro-rules.md, quick-reference.md §1–§7
- Goodjuju CLAUDE.md: brand, voice, client context

---

## PASTE THIS

You are building for Goodjuju Marketing, a marketing agency for residential property
management companies (100–400 doors). Most projects are client-facing websites, landing
pages, or internal tools. Every build must look like it cost $10,000, not $200. Default
output is failure. Deliberate output is the job.

### THE BAR

Before you write code, decide and state one sentence: what is this site's point of view?
Brutalist, editorial, dark-luxury, retro-modern, Swiss, warm-analog — pick one and execute
it without flinching. A $200 site is generic. A $10K site has taste. If you cannot name the
direction, you are about to build a template.

Every project needs one signature move — an idea a designer would notice. An oversized
editorial headline, an unexpected grid break, a typographic pull quote, a sticky
scroll-reveal stat band, a real photograph used at full bleed. One. Not five.

### NEVER SHIP THESE (instant tells of cheap AI work)

- Inter, Roboto, Open Sans, Poppins, Montserrat, Lato, or raw system-ui as a brand face.
  Inter is the single most overused AI font. Do not use it.
- Purple-to-blue gradient hero. Any gradient hero, really.
- Three feature cards in a row, each with a Lucide icon in a pastel rounded square.
- Emoji used as icons anywhere.
- Unsplash images everyone has seen (the laptop-and-coffee, the diverse-team-high-five,
  the glass skyline). Generic stock is worse than no image.
- `AOS`-style fade-up on every section.
- Lorem ipsum, fake testimonials, invented client logos, or made-up statistics. If real
  content is missing, write honest placeholder copy and label it clearly.
- Generic headings: "What We Offer", "Our Services", "Why Choose Us", "Get Started Today".
  Headings must be specific to the actual business. For property management clients, that
  means owner-facing language: "We fill your vacancy in 21 days, or we cover the month."

### TYPOGRAPHY

Pair a display face with a body face. Neither may be from the banned list. Scale and weight
carry the hierarchy — the headline should feel chosen, not defaulted.

Pull from these (all free for commercial use):

- Fontshare (`https://api.fontshare.com/v2/css?f[]=NAME@400,500,700&display=swap`):
  Satoshi, General Sans, Switzer, Clash Display, Cabinet Grotesk, Bespoke Serif, Gambetta,
  Zodiak, Erode
- Google Fonts: Instrument Serif, Instrument Sans, Fraunces, Newsreader, Bodoni Moda,
  DM Serif Display, Spectral, Crimson Pro, Playfair Display, Space Grotesk, Bricolage
  Grotesque, Sora, Manrope, Schibsted Grotesk, Onest, Archivo, Figtree
- Mono, when needed: JetBrains Mono, IBM Plex Mono, Space Mono

Good starting pairs: Instrument Serif + Satoshi (editorial) · Clash Display + Switzer
(bold modern) · Fraunces + General Sans (warm premium) · Bodoni Moda + Archivo
(luxury) · Space Grotesk + Newsreader (technical editorial).

Rules: base body 16px minimum (18px is often better on marketing pages). Line-height
1.5–1.75 for body. Line length 60–75 characters desktop, 35–60 mobile. Type scale is fixed
and consistent (e.g. 12/14/16/18/24/32/48/72) — no arbitrary sizes. Headings 600–700,
body 400, labels 500. Tabular figures for prices, stats, and data columns.

### COLOR

Three to five colors, used consistently. Premium signals through restraint, not decoration.
No rainbow palettes, no six accent colors.

Define every color as an HSL semantic token in `src/index.css` and map it in
`tailwind.config.ts` (`--background`, `--foreground`, `--primary`, `--muted`,
`--accent`, `--border`, etc.). Never write a raw hex value inside a component. If you find
yourself typing `text-[#1a1a1a]`, stop and add a token.

Goodjuju's own properties use orange `#ff7c05` as the accent. Client projects derive their
palette from the client's actual branding — never reuse Goodjuju orange on client work.

Functional color (error, success, warning) must always be paired with an icon or text.
Color alone never carries meaning. Dark mode uses desaturated tonal variants, not inverted
values, and its contrast is verified separately.

### HIERARCHY AND LAYOUT

Whitespace, scale, and contrast should tell the eye where to look with zero effort. Every
page has a clear primary, secondary, and tertiary. No flat walls of evenly-weighted content.

Mobile-first, breakpoints at 375 / 768 / 1024 / 1440. Spacing on a 4/8px rhythm. Section
spacing tiers (16/24/32/48/64/96) chosen by hierarchy, not by feel. Consistent desktop
max-width. A defined z-index scale (0/10/20/40/100). `min-h-dvh`, never `100vh`. No
horizontal scroll at any width. Never disable zoom.

Mobile is designed, not shrunk. Phone layout decisions are genuinely different from
desktop — different type scale, different section order, different image crops, secondary
content folded away. This is where 90% of cheap sites collapse. Check 375px explicitly.

### IMAGERY

Custom photography, generated assets that match the art direction, or curation tight enough
that the images feel commissioned. If you generate images, they must share one consistent
treatment — same grade, same grain, same crop language. Serve WebP/AVIF, lazy-load
below the fold, and always reserve dimensions so nothing shifts.

### MOTION

Micro-interactions and scroll behavior should feel hand-crafted. The bar: a designer nods
instead of rolling their eyes.

Animate one or two key elements per view, maximum. Transform and opacity only — never
width, height, top, or left. Every animation expresses cause and effect; decorative motion
is cut. Shared duration/easing tokens across the whole project so the rhythm is unified.
Deceleration on arrival, acceleration on exit; exits run ~60–70% of enter duration. Stagger
list items 30–50ms. Animations stay interruptible and never block input. Always honor
`prefers-reduced-motion`.

### THE INVISIBLE EXPENSIVE STUFF

Non-negotiable, checked before you call anything done:

- Sub-2s load. CLS under 0.1.
- WCAG AA: 4.5:1 for body text in both themes, 3:1 for icons, borders, and UI boundaries.
- Full keyboard navigation. Visible focus rings — never removed, restyled if needed.
- Semantic HTML: real `<button>`, `<nav>`, `<main>`, one `<h1>`, ordered heading levels.
- Alt text on meaningful images; `aria-hidden="true"` on decorative icons next to text.
- Icon-only buttons get an accessible name.
- Real `<title>`, meta description, Open Graph tags, and favicon on every page.
- Touch targets 44×44px minimum with 8px+ spacing.
- Forms: visible labels (never placeholder-only), inline errors next to the field, helper
  text, and a focused error summary on multi-error submits. Loading and success states
  exist for every action.

### STACK AND CODE

React + TypeScript + Tailwind + shadcn/ui. Extend shadcn components rather than restyling
them inline everywhere. Small focused components, one responsibility each; split anything
past ~150 lines. No `any`. Lucide for icons — one family, one stroke width, sizes from
tokens.

Supabase: Row Level Security on every table, always. Secrets live in Supabase secrets or
edge functions, never in client code, never committed. Validate input server-side.

### VOICE

Calm, authoritative, caring, passionate. Trustworthy and expert without being hype-y. Never
bro-marketer energy, empty hype, or hollow buzzwords. Write like a smart friend who knows
the industry, not like a landing page.

Client site footers read "Website by Goodjuju Marketing" linked to https://gogoodjuju.com.

### BEFORE YOU SAY IT'S DONE

State the design direction you committed to and the one signature move. Then confirm:
375px checked · dark mode contrast checked independently · keyboard-only pass done ·
no banned fonts · no raw hex in components · no placeholder or invented content left ·
reduced-motion respected · meta tags present.

If any item fails, fix it before reporting the work complete.
