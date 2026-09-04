---
name: goodjuju-prelaunch-audit
description: >-
  Use before handing any build to a client or publishing it — the final quality
  gate covering design, accessibility, performance, responsive behavior, SEO,
  security, and content honesty. Also use when asked to audit, QA, or review a
  site before launch. Not for mid-build work.
---

# Pre-launch audit

Run every section. Report findings as **critical** (blocks launch), **serious**,
or **minor**. Do not report "looks good" for anything you did not actually check —
say what you could not verify and why.

Finish with the verdict block at the bottom.

## 1. Design integrity

- [ ] The committed design direction is still legible in the finished build — it
      didn't drift back toward a template mid-way
- [ ] The signature move survived and is on the page
- [ ] No banned font anywhere: Inter, Roboto, Open Sans, Poppins, Montserrat,
      Lato, Nunito, or raw system-ui as a brand face
- [ ] Five colors or fewer
- [ ] Zero raw hex values inside components — grep for `#` in `src/components`
      and for `-[#` in className strings. Everything routes through tokens.
- [ ] One icon family, one stroke width, sizes from tokens
- [ ] No emoji used as an icon
- [ ] Type scale is the defined scale — no arbitrary sizes

## 2. Content honesty

- [ ] No lorem ipsum
- [ ] No invented testimonials, client logos, stats, or awards
- [ ] Every remaining placeholder is clearly labeled and listed in the handoff
- [ ] No generic headings ("What We Offer", "Our Services", "Why Choose Us",
      "Get Started Today")
- [ ] No leftover template content — emails, addresses, phone numbers, brand
      names hardcoded in components
- [ ] Every rendered image visually inspected, not just reassigned. Check
      sidebars, thumbnails, decorative background shapes, `.svg` files, and any
      single image reused across all dynamic detail routes.
- [ ] Orphaned assets deleted

## 3. Responsive

- [ ] 375px checked explicitly — and mobile is genuinely *designed*, not the
      desktop layout compressed
- [ ] 768 / 1024 / 1440 checked
- [ ] No horizontal scroll at any width
- [ ] Zoom is not disabled; viewport meta correct
- [ ] `min-h-dvh`, not `100vh`
- [ ] Landscape remains readable and operable
- [ ] Long tokens (URLs, IDs, user content) reflow instead of overflowing

## 4. Accessibility — WCAG AA

- [ ] Body text ≥ 4.5:1 in **both** themes; icons, borders, and UI boundaries ≥ 3:1
- [ ] Dark mode contrast verified independently — never inferred from light mode
- [ ] Full keyboard pass: everything reachable by Tab, visible focus ring never
      removed, modals trap focus, Escape closes
- [ ] Semantic HTML — real `<button>`, `<nav>`, `<main>`, exactly one `<h1>`,
      heading levels in order
- [ ] Every input has a visible label; placeholder-only is a failure
- [ ] Icon-only buttons have an accessible name
- [ ] Decorative icons beside visible text are `aria-hidden="true"`
- [ ] Meaningful images have alt text; decorative images have empty alt
- [ ] Color is never the only signal — errors and states carry an icon or text
- [ ] Inline field errors, plus a focused error summary on multi-error submits
- [ ] `prefers-reduced-motion` honored
- [ ] Password managers and paste work on any auth field

## 5. Performance

- [ ] Loads under 2s
- [ ] CLS under 0.1 — all images and embeds have reserved dimensions
- [ ] Images are WebP or AVIF, lazy-loaded below the fold
- [ ] Animations use transform and opacity only — never width, height, top, left
- [ ] No layout shift from fonts; `font-display: swap` set

## 6. SEO

- [ ] Unique `<title>` and meta description per route
- [ ] Open Graph and Twitter card tags with a real preview image
- [ ] Favicon
- [ ] JSON-LD (`LocalBusiness` + `RealEstateAgent` for PM clients)
- [ ] Canonical URLs
- [ ] `sitemap.xml` and `robots.txt`
- [ ] Meta tags actually update per route on client-side navigation

## 7. Security and data

- [ ] Row Level Security enabled on **every** Supabase table
- [ ] No secrets in client code, no secrets committed — Supabase secrets or edge
      functions only
- [ ] Server-side input validation on every write
- [ ] No service-role key reachable from the browser

## 8. Goodjuju standards

- [ ] Footer reads "Websites and marketing for property managers by
      **Goodjuju Marketing**", linked to `https://gogoodjuju.com`
- [ ] No template-author or framework credit left anywhere
- [ ] Portal Login (Owner / Tenant) in the header nav
- [ ] `color-scheme: light` plus an explicit `body` background
- [ ] Goodjuju orange `#ff7c05` does not appear on client work
- [ ] Every form submits somewhere real, or is clearly flagged as not yet wired

## Verdict

```
LAUNCH:    READY / BLOCKED
CRITICAL:  <count> — <one line each>
SERIOUS:   <count> — <one line each>
MINOR:     <count>
NOT VERIFIED: <anything you could not check, and why>
PLACEHOLDERS REMAINING: <list, or none>
```

Any critical finding means BLOCKED. Do not soften the verdict, and do not report
a check as passed when you inferred it rather than performed it.
