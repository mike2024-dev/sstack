# Gear 4: Polish + Validation

**Goal**: No orphaned words. No muddy effects. Every pattern applied globally. The page looks intentional, not assembled.

**Speed**: Fast. This is a review pass, not building.

**Gate**: No orphans, no muddy effects, patterns global → page is done.

---

## Table of Contents
- [Decision Tree](#decision-tree)
- [Checklist](#checklist)
- [Anti-Pattern Triggers](#anti-pattern-triggers)
- [AI Prompt Templates](#ai-prompt-templates)

---

## Decision Tree

```
IF any section uses a different heading style than the others
  → Apply the established pattern globally in one prompt

IF a headline has a single word on the last line
  → Add text-balance (prefer for headings)
  → If inline spans are present → test text-pretty, may look better

IF feature section screenshots are at different crop positions
  → This is a Gear 3 problem. Use temporary tool pattern. Don't guess values.

IF navbar feels flat against page content
  → Check for backdrop-blur — add if missing

IF vertical borders (canvas grid) don't align between sections
  → Check that all sections use the same container class

IF the page still looks "template-y" after all gears
  → Check: Is font still from Google Fonts? → Fix (Gear 2)
  → Check: Is there any indigo? → Fix (Gear 2)
  → Check: Are there solid borders near shadows? → Fix (Gear 3)
  → Check: Is there an off-white background section? → Fix (Gear 1)
  → These 4 items cause 80% of "template-y" visual perception

IF AI added something you didn't ask for and it looks good
  → Accept it. Don't remove. (e.g., backdrop-blur on navbar)
  → AI pattern-learning is a feature, not a bug

IF AI applied a style to sections you didn't ask about
  → Check if the result is correct → if yes, accept and move on
```

---

## Checklist

**Global Patterns:**
- [ ] All section headings: same style applied globally
- [ ] All borders near shadows: `ring-1 ring-gray-950/10` (no `border border-*`)
- [ ] All orphaned headline words: `text-balance` applied
- [ ] All screenshots: same well treatment (`bg-gray-950/5`, `ring-1 ring-inset ring-gray-950/5`)

**Canvas Grid:**
- [ ] Canvas grid horizontal dividers: extend to full viewport width (`w-screen` or `w-full` with overflow)
- [ ] All sections use the same container class (alignment consistency)

**Logo Cloud:**
- [ ] Real SVGs, `fill-gray-950`, no title, no opacity reduction

**Footer:**
- [ ] Footer links: `text-xs`
- [ ] Social icons *(Schoger preference, optional)*: `text-gray-950 w-4 h-4` (small, dark)

**Backgrounds:**
- [ ] No section has `bg-gray-50` or `bg-slate-50`
- [ ] No section has a decorative `bg-gray-800` or dark background

**Details:**
- [ ] Feature section gaps: `gap-2` (8px) between containers
- [ ] Stats dividers: `divide-x divide-gray-950/10`
- [ ] Concentric border radius: verified on all inset images

**The 4-Item Template-y Check (80% of issues):**
- [ ] Font: variable Inter from rsms.me (not Google Fonts)
- [ ] Accent: not indigo
- [ ] Borders: `ring-1 ring-gray-950/10` (no solid borders near shadows)
- [ ] Backgrounds: white only (no off-white sections)

---

## Anti-Pattern Triggers

🚨 **Any section heading uses a different style than others** → Pattern isn't global yet.

🚨 **The page looks "AI-generated" even after all gears** → Run the 4-item checklist (font, indigo, solid borders, off-white backgrounds).

🚨 **Canvas grid sections don't line up** → Container class inconsistency.

🚨 **A solid color border appears anywhere near a shadow** → Missed in earlier gear.

🚨 **Footer link text is the same size as body text** → Should be `text-xs`.

---

## AI Prompt Templates

### Apply Global Pattern

```
Apply the same [COMPONENT TYPE: heading / screenshot well / eyebrow label] style
I established in the [SECTION NAME] to all other sections below it on the page.
```

---

### Final Orphan Sweep

```
Check all section headings and CTA text for orphaned words (single words on the last line).
Apply text-balance to any heading that has this problem.
```

---

### Final Border Audit

```
Do a pass through all components on the page. Any element that has both a border and
a drop shadow should use ring-1 ring-gray-950/10 instead of a solid border class.
```

---

### Remove Off-White Backgrounds

```
Remove all off-white and light gray backgrounds from every section (bg-gray-50, bg-slate-50,
bg-neutral-50). The page should have a consistent white background throughout.
```

---

### Fix Canvas Grid Alignment

```
All sections are not aligning to the same vertical grid lines. Make sure every section
uses the same container class for consistent grid alignment across the page.
```

---

### Apply Footer Sizing

```
Set all footer links to text-xs. Set social icons to w-4 h-4 text-gray-950.
```

---

*Back to SKILL.md → [Workflow Overview](../SKILL.md#end-to-end-workflow-9-steps)*
*Previous gear → [references/gear-3-components.md](gear-3-components.md)*
*For quick value lookup → [references/cheat-sheets.md](cheat-sheets.md)*
