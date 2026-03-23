# Gear 3: Components + Details

**Goal**: Every interactive element is pixel-correct. Borders don't muddy. Buttons are the right size. Screenshots are framed properly. Testimonials are clean.

**Speed**: Slow. This gear is where the work is.

**Gate**: Every interactive element is correct → advance to Gear 4.

---

## Table of Contents
- [Decision Tree](#decision-tree)
- [Checklist](#checklist)
- [Anti-Pattern Triggers](#anti-pattern-triggers)
- [AI Prompt Templates](#ai-prompt-templates)

---

## Decision Tree

```
IF a button has a solid colored border + drop shadow
  → Replace border with ring-1 ring-gray-950/10 (outer, not inset)
  → "Muddy" effect = shadow + solid border competing

IF primary + secondary buttons are side-by-side
  → Check height parity. Ring adds ~2px visual height.
  → IF misaligned → wrap secondary in <span class="inline-flex p-px"> + calc() fix
  → Move shadow to the <button>, not the wrapper <span>

IF button height is set with h-[38px]
  → Remove fixed height. Use padding instead: py-2.5 px-5 for hero, py-1 px-3 for nav
  → Button shapes: rounded-full (pill) for all buttons

IF a screenshot is inside a rounded card/container
  → Check: is the inner border-radius smaller than the outer?
  → Formula: inner_radius = outer_radius - gap_width
  → IF same radius → fix inner to be smaller (concentric rule)

IF showing a product screenshot on the page
  → Container: bg-gray-950/5 (5% opacity dark well)
  → Container ring: ring-1 ring-inset ring-gray-950/5
  → Feature card inset: p-2 (8px padding)
  → Hero inset: p-16 (64px padding)
  → Ring on image itself: absolute positioned with ring-1 ring-inset ring-gray-950/10
  → Bottom crop: pb-0, rounded-b-none (when image bleeds to container edge)

IF testimonials show star ratings + circular avatars
  → Remove both. They're visual noise.
  → Use portrait photo as card background
  → Add gradient overlay: bg-gradient-to-t from-black/70 to-transparent
  → Position quote: absolute bottom-4 left-4 right-4
  → Text: text-white, attribution: text-white/80

IF a visual/positional decision is impossible to spec numerically
  → Build a temporary inline tool (slider/drag UI)
  → Extract the final values
  → Bake into code and remove the tool

IF nav sign-in is a plain link
  → Give it secondary button treatment (ring + shadow) (Schoger preference, optional)

IF navbar has no depth/separation
  → Check if AI added backdrop-blur automatically — keep it if it did

IF logo cloud logos look like text placeholders
  → Export real SVGs from Figma, place in /public/logos/
  → Color: fill-gray-950, opacity: 100%, no reduction
```

---

## Checklist

### Buttons
- [ ] All borders near shadows: `ring-1 ring-gray-950/10` — NOT `border border-gray-300`
- [ ] Hero button height: padding-based `py-2.5 px-5`, NOT `h-[38px]`
- [ ] Hero button font: `text-sm` (14px)
- [ ] All buttons: pill-shaped `rounded-full`
- [ ] Nav CTA button: `py-1 px-3 text-sm rounded-full` (~28px height)
- [ ] Button shadow: on the `<button>` element, NOT on any wrapper `<span>`
- [ ] Primary + secondary button pair: height parity check — secondary wrapped in `inline-flex p-px` if ring is present

### Screenshots / Image Wells
- [ ] Screenshot container: `bg-gray-950/5` background, `ring-1 ring-inset ring-gray-950/5`
- [ ] Feature card screenshot padding: `p-2` (8px)
- [ ] Hero screenshot padding: `p-16` (64px), `pb-0`, `rounded-b-none`
- [ ] Image ring (on top): `absolute inset-0 ring-1 ring-inset ring-gray-950/10 rounded-*`
- [ ] Concentric border radius: inner `rounded-*` < outer `rounded-*`
- [ ] Screenshot resolution: captured at 3x (`devicePixelRatio: 3`)

### Testimonials
- [ ] Star ratings: removed
- [ ] Circular avatar containers: removed
- [ ] Photo: used as card background (`bg-cover bg-center`)
- [ ] Gradient overlay: `bg-gradient-to-t from-black/70 to-transparent`
- [ ] Quote position: `absolute bottom-4 left-4 right-4`
- [ ] Quote text: `text-white`
- [ ] Attribution text: `text-white/80`

### Stats
- [ ] Font size *(Schoger preference, optional)*: `text-5xl font-normal`
- [ ] Label color: `text-sm text-gray-600`
- [ ] Layout: `text-left`, full container width, `divide-x divide-gray-950/10`

### Navbar
- [ ] Sign-in link: secondary button treatment *(Schoger preference, optional)*: `ring-1 ring-gray-950/10` + shadow
- [ ] Backdrop blur: accept if AI added it automatically

---

## Anti-Pattern Triggers

🚨 **`border border-gray-*` on an element with a shadow** → Replace with `ring-1 ring-gray-950/10`.

🚨 **Two side-by-side buttons look different heights** → Ring is adding visual height. Fix with wrapper.

🚨 **Button has `h-[38px]`** → Fixed height breaks on zoom/content change. Use padding.

🚨 **Inner rounded element has same radius as its container** → Breaks the "hug" — fix with concentric rule.

🚨 **Screenshot has a gray/white border around it** → Replace with `ring-1 ring-inset ring-gray-950/10`.

🚨 **Testimonial card has stars and a circular avatar** → Remove. Use photo background + gradient.

🚨 **Logo cloud logos are text-based or colored** → Need real SVGs at `fill-gray-950`.

---

## AI Prompt Templates

### Fix All Borders (global, run early)

```
Find every element on the page that has both a border and a drop shadow.
Replace the solid border with ring-1 ring-gray-950/10 (outer ring, not inset).
```

---

### Fix Button Sizing

```
Make the hero button height approximately 38 pixels using padding, not fixed height.
Use py-2.5 px-5. Font size should be text-sm. Make all buttons pill-shaped with rounded-full.
```

---

### Fix Button Height Parity (when secondary has a ring)

```
The secondary button has a ring and appears 2px taller than the primary button.
Wrap the secondary button in a span with inline-flex and p-px. Apply calc() adjustments
on the span to make them visually the same height. Make sure the button shadow is on
the button element, not the parent span.
```

---

### Set Up Screenshot Well

```
Put the screenshot inside a container with bg-gray-950/5 background and
ring-1 ring-inset ring-gray-950/5. Add p-2 padding inside the container.
Place an absolutely-positioned overlay on top of the screenshot with
ring-1 ring-inset ring-gray-950/10 to create a subtle edge. Make sure the
screenshot's border radius is smaller than the container's border radius.
```

---

### Set Up Hero Screenshot Well

```
Put the hero screenshot inside a container with bg-gray-950/5 background.
Use p-16 padding on the container, but set pb-0 and rounded-b-none so the
screenshot bleeds to the bottom edge. Add ring-1 ring-inset ring-gray-950/5
to the container. Place an absolute overlay with ring-1 ring-inset ring-gray-950/10
on the screenshot itself.
```

---

### Fix Testimonials

```
Redesign the testimonials. Remove the star ratings and circular avatar containers.
Make the portrait photo the background of each card (bg-cover bg-center).
Add a dark gradient overlay from bottom to top (from-black/70 to-transparent).
Position the quote text at the bottom-left of the card in white. Attribution in white/80.
```

---

### Build a Temporary Positioning Tool

```
Build a temporary interactive tool inline on this page (not on a separate port or domain).
I need to visually adjust the crop position of the screenshot in [SECTION NAME].
Add a slider or drag control so I can move the image within its crop area.
Display the final CSS values so I can copy them. When I'm done, I'll tell you the
values and you can bake them into the code and remove the tool.
```

> **Note**: If Claude Code builds the tool on a different localhost port, add: "Make it inline on the current page, not a separate port."

---

### Fix Concentric Border Radius

```
The screenshot inside the [SECTION] card has the same border radius as the outer container.
Make the inner element's border radius smaller. The formula is:
inner_radius = outer_radius - gap_width.
```

---

*Back to SKILL.md → [Workflow Overview](../SKILL.md#end-to-end-workflow-9-steps)*
*Previous gear → [references/gear-2-typography-color.md](gear-2-typography-color.md)*
*Next gear → [references/gear-4-polish.md](gear-4-polish.md)*
