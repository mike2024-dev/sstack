# Gear 1: Foundation (Layout + Structure)

**Goal**: Get the skeleton right. Sections exist. Layout is not centered. Grid is in place. Real content (not placeholder text) is roughed in.

**Speed**: Fast. Don't refine typography here — that's Gear 2.

**Gate**: Layout is correct, sections exist, no centering → advance to Gear 2.

---

## Table of Contents
- [Decision Tree](#decision-tree)
- [Checklist](#checklist)
- [Anti-Pattern Triggers](#anti-pattern-triggers)
- [AI Prompt Templates](#ai-prompt-templates)

---

## Decision Tree

```
IF starting from scratch
  → Write a structured brief FIRST (see references/ai-collaboration.md)
  → Let AI generate a 60% skeleton in one prompt
  → DO NOT iterate on typography or color yet

IF inheriting AI-generated page
  → Check: is everything centered? → Fix to left-align BEFORE anything else
  → Check: is the hero a single column? → Consider split layout (Gear 1 fix)
  → Check: are there off-white alternating section backgrounds? → Remove them

IF the hero section is blank/boring
  → IF real product exists → add real screenshot (not fake UI)
  → IF no product yet → use split headline layout (text only, no image)
  → IF centering the headline → switch to split 3/5 + 2/5 grid

IF the layout feels cramped or too narrow
  → Check max-width. Default Tailwind (1024px) is too narrow.
  → Set container to max-w-[1280px]

IF sections blur together visually
  → Add canvas grid (vertical borders on container, horizontal dividers full-width)
  → DO NOT add off-white alternating backgrounds

IF logo cloud exists with a section title
  → Remove the section title — logos are self-evident
```

---

## Checklist

- [ ] Container width: `max-w-[1280px]` (not Tailwind default `max-w-screen-xl`)
- [ ] Hero layout: asymmetric split (`grid grid-cols-5`, heading `col-span-3`, supporting `col-span-2`, `items-start`)
- [ ] All section headings: `text-left` (override AI's default `text-center`)
- [ ] Hero screenshot (if used): captured at 3x resolution, bottom-cropped (`pb-0 rounded-b-none`)
- [ ] Logo cloud: no section title, logos at full opacity (`fill-gray-950`), slightly bigger than AI default (`h-6` or larger)
- [ ] Section backgrounds: white only — no `bg-gray-50` / `bg-slate-50` alternating sections
- [ ] Canvas grid (optional): vertical `border-l border-r` on container, horizontal `border-t w-screen` between sections
- [ ] Sections present: navbar → hero → logo cloud → feature section → stats → testimonials → CTA → footer

---

## Anti-Pattern Triggers

🚨 **Everything is centered** → AI defaulted. Left-align before anything else.

🚨 **Alternating off-white section backgrounds** → Remove. Use canvas grid instead.

🚨 **Container width feels narrow** → Not using `max-w-[1280px]`.

🚨 **Logo cloud has "Trusted by" or "Our Partners" title** → Delete it.

🚨 **Hero shows a fake/generated UI mockup** → Replace with real screenshot or remove.

🚨 **Stats/features have `bg-gray-800` dark section** → Get rid of it. White page only.

---

## AI Prompt Templates

### Initial Brief (copy-paste and fill in the blanks)

```
Design a marketing homepage for [PRODUCT NAME].

[PRODUCT NAME] is [ONE-SENTENCE DESCRIPTION OF WHAT IT DOES AND WHO IT'S FOR].

Keep it simple and minimal. No colored accents — use neutral grays.

Include these sections in this order:
- Navbar with logo, nav links, and a sign-in + primary CTA button
- Hero with headline, supporting text, and CTA buttons
- Logo cloud (trusted-by section)
- Feature section with 3 features
- Stats section with 3-4 key metrics
- Testimonials (3 cards)
- CTA section
- Footer with links and social icons

Left-align all text and layouts. Don't center anything.
```

**What NOT to put in the first prompt:**
- Specific colors or fonts (fix those in Gear 2)
- Exact pixel values (iterate on these)
- Layout details for individual sections (let AI choose, then fix)

**Philosophy**: First prompt gets to 60%. Speed > perfection at step 1.

---

### Fix Centering (global)

```
Left-align all section headings and body text throughout the page. The hero headline
and supporting text should both be left-aligned. Don't center anything except [EXCEPTION IF ANY].
```

---

### Fix Hero Layout (split)

```
Change the hero layout to a split headline. Make the headline take up 3/5 of the width
on the left, and put the supporting text and buttons on the right in the remaining 2/5.
Use a 5-column grid. Align the tops. Both sides left-aligned.
```

---

### Add Canvas Grid

```
Add a canvas grid to the page. Put vertical borders on the sides of the content
container. Add horizontal borders between each section that extend to the full width
of the viewport. Use a very subtle border color — gray-950 at 10% opacity.
```

---

### Fix Logo Cloud

```
Remove the section title from the logo cloud. Make all logos gray-950 at full opacity
with no opacity reduction. Remove any off-white background from this section.
Remove any top and bottom borders. Make the logos slightly larger.
```

---

### Fix Container Width

```
Set the page container to max-w-[1280px]. This should apply to all sections consistently.
```

---

### Remove Off-White Section Backgrounds

```
Remove all off-white and light gray section backgrounds (bg-gray-50, bg-slate-50,
bg-neutral-50). Every section should have a white background. Keep canvas grid borders
if present.
```

---

*Back to SKILL.md → [Workflow Overview](../SKILL.md#end-to-end-workflow-9-steps)*
*Next gear → [references/gear-2-typography-color.md](gear-2-typography-color.md)*
