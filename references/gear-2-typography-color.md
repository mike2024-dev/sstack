# Gear 2: Typography + Color

**Goal**: Lock the font system. Fix tracking. Set the color palette. This gear touches every piece of text on the page.

**Speed**: Medium. Typography mistakes propagate everywhere — fix globally, not per-section.

**Gate**: Font, tracking, color system locked → advance to Gear 3.

---

## Table of Contents
- [Decision Tree](#decision-tree)
- [Checklist](#checklist)
- [Anti-Pattern Triggers](#anti-pattern-triggers)
- [AI Prompt Templates](#ai-prompt-templates)

---

## Decision Tree

```
IF still using basic Inter from Google Fonts
  → Switch to variable Inter from rsms.me/inter
  → Enable optical sizing and stylistic sets
  → This is non-negotiable. Do it first.

IF headlines look loose or "default"
  → Apply tracking-tight or tracking-tighter to all text ≥ 24px
  → This is a one-line global change

IF the accent color is indigo
  → Always override. Indigo = AI template signal.
  → IF brand has a color → use that color
  → IF no brand color → use gray-950 (Schoger preference, optional)
  → DO NOT keep indigo

IF using slate grays (blue-cast)
  → Switch all gray-* to neutral (no color cast)
  → "Update all grays on the site to use neutral" as a single global prompt

IF eyebrow labels above section headings look generic
  → Apply: font-mono + uppercase + tracking-wider + text-xs + text-gray-600

IF headline + body text feel like two separate chunks
  → Consider inline heading treatment: same text-4xl size, heading dark, body gray-600 inline
  → Max width: max-w-[40ch] on the text container

IF a headline has an orphaned word on the last line
  → Add text-balance (headings) or text-pretty (prose)
  → Test both — they behave differently with inline spans

IF font weight at 500 (medium) feels too light but 600 (semi-bold) feels too heavy
  → Use font-[550] — only works with variable font (Schoger preference, optional)
```

---

## Checklist

**Font System:**
- [ ] Font source: variable Inter from `https://rsms.me/inter/` (NOT Google Fonts)
- [ ] Optical sizing enabled: `font-optical-sizing: auto` in CSS
- [ ] Display features enabled: `font-feature-settings: 'cv01', 'cv02', 'cv03', 'cv04';`
- [ ] Tailed 'l' disabled *(Schoger preference, optional)*: `font-feature-settings: 'cv05' 0`

**Typography:**
- [ ] Headline tracking: `tracking-tight` or `tracking-tighter` on all `text-4xl` and above
- [ ] Body tracking: default (do NOT tighten tracking on small text)
- [ ] Eyebrow labels: `font-mono uppercase tracking-wider text-xs text-gray-600`
- [ ] Inline heading max width: `max-w-[40ch]` applied on same element where font-size is declared
- [ ] Orphan prevention: `text-balance` on headings, test `text-pretty` as alternative
- [ ] Font weight for headlines *(Schoger preference, optional)*: `font-[550]`

**Color:**
- [ ] Gray scale: neutral family — `gray-*` not `slate-*` (neutral has no blue cast)
- [ ] Primary accent: NOT indigo — choose deliberately or use `gray-950`
- [ ] Border/ring color: `ring-gray-950/10` (10% opacity, not solid gray)
- [ ] Supporting text: `text-gray-600` for descriptions and labels
- [ ] Eyebrow label color: `text-gray-600`
- [ ] Text on dark overlays: `text-white` for quote, `text-white/80` for attribution

---

## Anti-Pattern Triggers

🚨 **Inter loads from fonts.google.com** → Missing variable font, optical sizing, feature settings.

🚨 **Accent color is indigo** → Override immediately. This is the #1 AI template tell.

🚨 **Gray colors have a blue cast** → Using slate. Switch to neutral.

🚨 **Headlines feel "floaty" or soft** → Missing `tracking-tight`.

🚨 **Single word stranded at end of a headline** → Missing `text-balance` or `text-pretty`.

🚨 **Eyebrow label looks like a smaller heading** → Not using monospace treatment.

🚨 **`max-w-[600px]` on text** → Use `max-w-[40ch]` instead (scales with font size).

---

## AI Prompt Templates

### Fix Font System (run once, globally)

```
Switch the font to the variable version of Inter from rsms.me/inter. Enable
font-optical-sizing: auto. Add font-feature-settings for cv01, cv02, cv03, cv04.
Use the display optical size for all headlines. Do not load Inter from Google Fonts.
```

---

### Fix Tracking (globally)

```
Apply tracking-tight to all headline text that is text-4xl or larger. Leave
body and caption text at default tracking.
```

---

### Fix Color System (globally)

```
Update all grays on the site to use neutral (not slate). Swap all uses of [CURRENT ACCENT COLOR]
to gray-950. Update all borders from solid colors to ring-1 ring-gray-950/10.
```

---

### Add Eyebrow Labels

```
Style the eyebrow label above the [SECTION NAME] heading as: font-mono, uppercase,
tracking-wider, text-xs, text-gray-600.
```

---

### Fix Orphaned Headline

```
Apply text-balance to the [SECTION] heading to prevent orphaned words on the last line.
```

---

### Inline Heading Treatment

```
Make the title and supporting text in the [SECTION] section the same font size (text-4xl).
Make the title inline with the supporting text so they read as one block. The title should
be text-gray-950. The supporting text should be text-gray-600 font-medium. Give the
container a max-w-[40ch] constraint.
```

---

### Apply Variable Font Weight (optional)

```
Set the headline font weight to font-[550] throughout the page. This requires the
variable Inter font from rsms.me to be loaded.
```

---

*Back to SKILL.md → [Workflow Overview](../SKILL.md#end-to-end-workflow-9-steps)*
*Previous gear → [references/gear-1-foundation.md](gear-1-foundation.md)*
*Next gear → [references/gear-3-components.md](gear-3-components.md)*
