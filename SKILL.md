---
name: sstack
description: >
  UI design cognitive framework for building polished marketing/landing pages with AI coding
  tools (Claude Code, Cursor, etc.). Activate when: building a marketing homepage from scratch,
  iterating on an AI-generated page that looks "template-y" or generic, doing a pre-launch
  polish pass, or reviewing sections against Schoger's design patterns. NOT for: application
  UI / dashboards, component library design, accessibility auditing (WCAG), brand identity /
  logo design, mobile-native apps, dark mode, animation, or multi-page site architecture.
  Implements Steve Schoger's 4-gear cognitive framework with decision trees, cheat sheets,
  and copy-pasteable AI prompt templates.
---

# UI Design Skill

> Cognitive framework for shipping polished marketing pages with AI coding tools.
> Based on Steve Schoger's "Designing with Claude Code" methodology.

## When to Use / Not Use

**Use when:**
- Building a marketing/landing page from scratch with Claude Code or Cursor
- Iterating on an AI-generated page that looks generic or "template-y"
- Pre-launch polish pass on a marketing page
- Validating a page against Schoger's design patterns

**Do NOT use for:**
- Application UI / dashboards (different constraints)
- Component library / design system work
- Accessibility audits (WCAG compliance)
- Brand identity / logo design (use Figma)
- Mobile-native apps (web/marketing only)
- Dark mode, animation, performance optimization

---

## The 4 Cognitive Gears

Run them in order. Each has a gate — don't advance until the gate condition is met.

| Gear | Name | Goal | Gate Condition |
|------|------|------|----------------|
| 1 | **Foundation** | Skeleton right, sections exist, layout not centered | Layout correct, sections exist, no centering |
| 2 | **Typography + Color** | Font system locked, tracking fixed, color palette set | Font, tracking, color system locked |
| 3 | **Components + Details** | Every interactive element pixel-correct | Every interactive element correct |
| 4 | **Polish + Validation** | No orphans, no muddy borders, global patterns applied | No orphans, no muddy effects, patterns global |

> **Speed guide**: Gear 1 = fast. Gear 2 = medium (fix globally, not per section). Gear 3 = slow (where the work is). Gear 4 = fast (review pass, not building).

**Reference files for each gear:**
- Gear 1 details (decision tree + checklist + prompts) → `references/gear-1-foundation.md`
- Gear 2 details → `references/gear-2-typography-color.md`
- Gear 3 details → `references/gear-3-components.md`
- Gear 4 details → `references/gear-4-polish.md`

---

## End-to-End Workflow (9 Steps)

```
STEP 1 — Write the Brief                          [Gear 1]
  → Describe product (1-2 sentences)
  → List sections explicitly
  → Do NOT specify colors or fonts yet

STEP 2 — Generate the Skeleton                    [Gear 1]
  → Run brief as first prompt — one big prompt
  → Accept the 60% result — don't iterate yet
  → Do NOT make multiple small prompts

STEP 3 — Fix Layout Problems                      [Gear 1]
  → Left-align everything
  → Fix hero to split layout if needed
  → Remove off-white section backgrounds
  → Remove logo cloud section title

STEP 4 — Fix Font + Color System                  [Gear 2]
  → Switch to variable Inter from rsms.me
  → Apply tracking-tight to headlines
  → Switch slate → neutral grays
  → Fix accent color (remove indigo)
  → Apply globally — one prompt per concern

STEP 5 — Fix Typography Details                   [Gear 2]
  → Add eyebrow labels (monospace treatment)
  → Add inline heading where appropriate
  → Set max-w-[40ch] on text containers
  → Apply text-balance to headings

STEP 6 — Fix Components                           [Gear 3]
  → Fix all solid borders near shadows (→ ring)
  → Fix button sizing (padding-based, not fixed height)
  → Fix button height parity (ring compensation)
  → Set up screenshot wells (bg-gray-950/5)
  → Fix testimonials (photo background + gradient)
  → Fix concentric border radii

STEP 7 — Visual Decisions via Temporary Tools     [Gear 3]
  → Any value hard to spec numerically → build a temp tool
  → Screenshot crop, spacing tweaks, etc.
  → Extract values → bake → remove tool

STEP 8 — Apply Patterns Globally                  [Gear 4]
  → Once a pattern is right → apply to all similar sections
  → One global prompt, not per-section repeats

STEP 9 — Final Polish Pass                        [Gear 4]
  → Orphan check on all headings
  → Border audit (no solid borders near shadows)
  → Background check (no off-white sections)
  → Canvas grid alignment check
```

---

## AI Collaboration Protocol (Key Patterns)

**Initial prompt template** → full template in `references/ai-collaboration.md`

**Iteration rule:** One problem at a time. One prompt per change. Short prompts win.
- ✅ "Make the tracking in the headline a bit tighter."
- ❌ "Fix the tracking AND the font weight AND the button color AND the spacing..."

**Apply global patterns:** Once a pattern is correct in one section:
> "Apply this same eyebrow label style to all sections below."

**Temporary tool pattern:** For decisions you can't spec numerically (crop position, exact spacing):
> "Build a temporary interactive tool inline on this page. I need to visually adjust [WHAT].
> Show me the CSS values as I adjust. Remove the tool when I give you the final values."

Full protocol (override table, iteration strategy, tool pattern) → `references/ai-collaboration.md`

---

## Anti-Pattern Quick Scan 🚨

Run this checklist before Gear 2. These 4 items cause 80% of "template-y" visual perception:

| # | Anti-Pattern | Fix |
|---|---|---|
| 1 | **Font from Google Fonts** | Variable Inter from rsms.me |
| 2 | **Indigo accent color** | gray-950 or deliberate brand color |
| 3 | **Solid border near shadow** | `ring-1 ring-gray-950/10` |
| 4 | **Off-white section backgrounds** | White only, no `bg-gray-50` |

**Additional triggers by gear:**

**Gear 1:**
- 🚨 Everything is centered → Left-align before anything else
- 🚨 Alternating off-white backgrounds → Remove, use canvas grid instead
- 🚨 Container feels narrow → Set `max-w-[1280px]`
- 🚨 Logo cloud has "Trusted by" title → Delete it
- 🚨 Hero shows fake/generated UI mockup → Replace or remove
- 🚨 Dark `bg-gray-800` stats section → Remove, white page only

**Gear 2:**
- 🚨 Inter from fonts.google.com → Missing variable font + features
- 🚨 Accent is indigo → Override immediately (#1 AI template tell)
- 🚨 Gray has blue cast → Using slate, switch to neutral
- 🚨 Headlines feel "floaty" → Missing `tracking-tight`
- 🚨 Single word stranded at end of headline → Missing `text-balance`
- 🚨 Eyebrow label looks like a smaller heading → Not using monospace treatment
- 🚨 `max-w-[600px]` on text → Use `max-w-[40ch]` instead

**Gear 3:**
- 🚨 `border border-gray-*` near shadow → Replace with `ring-1 ring-gray-950/10`
- 🚨 Two buttons look different heights → Ring is adding visual height, fix with wrapper
- 🚨 Button has `h-[38px]` → Fixed height breaks, use padding instead
- 🚨 Inner rounded element = same radius as container → Fix with concentric rule
- 🚨 Screenshot has gray/white border → Replace with `ring-1 ring-inset ring-gray-950/10`
- 🚨 Testimonial has stars + circular avatar → Remove, use photo background + gradient
- 🚨 Logo cloud logos are text-based or colored → Need real SVGs at gray-950

**Gear 4:**
- 🚨 Section headings have different styles → Pattern isn't global yet
- 🚨 Page still looks AI-generated after all gears → Run the 4-item checklist above
- 🚨 Canvas grid sections don't line up → Container class inconsistency
- 🚨 Footer link text same size as body → Should be `text-xs`

---

## Reference Files Navigation

| File | When to Read |
|------|-------------|
| `references/gear-1-foundation.md` | Starting or fixing layout/structure (Steps 1–3) |
| `references/gear-2-typography-color.md` | Setting up font system and color (Steps 4–5) |
| `references/gear-3-components.md` | Fixing buttons, screenshots, testimonials (Steps 6–7) |
| `references/gear-4-polish.md` | Final validation pass (Steps 8–9) |
| `references/cheat-sheets.md` | Quick lookup: exact Tailwind values for any element |
| `references/ai-collaboration.md` | Initial prompt template, override table, temp tool pattern |

---

## Sections Checklist (Standard Marketing Page)

Expected section order for a complete marketing page:
```
navbar → hero → logo cloud → feature section → stats → testimonials → CTA → footer
```

---

*Based on: Steve Schoger — "Designing with Claude Code" (~60 min). 2026-03-22.*
