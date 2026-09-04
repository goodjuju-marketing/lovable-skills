# Lovable Skills — Goodjuju Marketing

Agent skills and workspace knowledge that push [Lovable](https://lovable.dev) toward
deliberate, premium output instead of its defaults.

Built for websites for residential property management companies, but the design and
audit skills are industry-agnostic — only `goodjuju-pm-website` is PM-specific.

Markdown only. No scripts, no dependencies. Also works unchanged in Claude Code and
Cursor, which read the same Agent Skills format.

## What's here

| | Type | Use it for |
|---|---|---|
| [`workspace-knowledge.md`](workspace-knowledge.md) | Knowledge | Always-on rules — loads on every message |
| [`skills/goodjuju-design-direction`](skills/goodjuju-design-direction) | Skill | Commit to an art direction before writing code |
| [`skills/goodjuju-pm-website`](skills/goodjuju-pm-website) | Skill | Required sections for a property management site |
| [`skills/goodjuju-prelaunch-audit`](skills/goodjuju-prelaunch-audit) | Skill | Final quality gate before client handoff |

**Knowledge and skills are different mechanisms.** Knowledge is always in context and
sets the baseline. Skills load on demand when their description matches the task. The
knowledge file is pasted by hand — there is no import path for it.

## Install

**Workspace knowledge** — open [`workspace-knowledge.md`](workspace-knowledge.md), copy
everything below the `## PASTE THIS` line, and paste it into
Lovable → Settings → Workspace knowledge.

**Skills** — Workspace skills → **Add** → **Import from GitHub**, one URL at a time:

```
https://github.com/goodjuju-marketing/lovable-skills/tree/main/skills/goodjuju-design-direction
https://github.com/goodjuju-marketing/lovable-skills/tree/main/skills/goodjuju-pm-website
https://github.com/goodjuju-marketing/lovable-skills/tree/main/skills/goodjuju-prelaunch-audit
```

Or download a skill folder and use **Upload ZIP** with `SKILL.md` at the archive root.

## Updating

**Lovable's GitHub import is a one-time snapshot, not a live link.** It downloads the
repo, validates it, and stores its own copy. Pushing here does not change what Lovable
already holds.

So the loop is:

1. Edit the `SKILL.md` in this repo
2. Push
3. Delete the old skill in Lovable
4. Re-import

Editing a skill inside Lovable's UI instead forks it silently, and this repo stops
being the truth. Edit here.

## The bar these enforce

- A named design direction, committed before any component is written
- No default fonts — Inter, Roboto, Open Sans, Poppins, Montserrat, Lato are banned
- Five colors maximum, as semantic tokens, never raw hex in a component
- One signature move per project
- Mobile designed, not shrunk
- WCAG AA, sub-2s load, semantic HTML, real meta tags
- No invented testimonials, stats, logos, or awards

## Credits

The design bar draws on **The $10K Checklist** (Metics Media, Field Guide No. 01) and the
rule set from [**ui-ux-pro-max**](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)
by nextlevelbuilder (MIT). That skill's guidance is distilled into prose here because
Lovable cannot execute its Python search tooling.

## License

MIT — see [LICENSE](LICENSE). Free for personal and commercial use.
