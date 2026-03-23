# Cheat Sheets — Quick Reference Tables

For exact Tailwind values and CSS rules. Look up the element, get the value, move on.

---

## Table of Contents
- [Typography Cheat Sheet](#typography-cheat-sheet)
- [Color Cheat Sheet](#color-cheat-sheet)
- [Layout Cheat Sheet](#layout-cheat-sheet)
- [Component Cheat Sheet](#component-cheat-sheet)

---

## Typography Cheat Sheet

| Element | Value | Notes |
|---------|-------|-------|
| Font source | `https://rsms.me/inter/` | Variable Inter — never Google Fonts basic Inter |
| Optical sizing (CSS) | `font-optical-sizing: auto` | Required in CSS, not Tailwind |
| Feature settings (CSS) | `font-feature-settings: 'cv01', 'cv02', 'cv03', 'cv04'` | Enable stylistic sets |
| Disable tailed 'l' (CSS) | `font-feature-settings: 'cv05' 0` | *(Schoger preference, optional)* |
| Headline weight | `font-[550]` | Requires variable font *(Schoger preference, optional)* |
| Headline tracking | `tracking-tight` or `tracking-tighter` | Apply to `text-4xl` and above |
| Body tracking | Default | Never tighten small text |
| Eyebrow label (full) | `font-mono uppercase tracking-wider text-xs text-gray-600` | Full treatment for section labels |
| Inline heading span | `inline text-4xl text-gray-950` | Same size as body, different color |
| Inline body span | `inline text-4xl text-gray-600 font-medium` | Same container as heading |
| Text max width | `max-w-[40ch]` | Must be on same element as font-size declaration |
| Orphan prevention (headings) | `text-balance` | Test `text-pretty` as alternative |
| Orphan prevention (prose) | `text-pretty` | Especially when inline spans are present |
| Hero supporting text | `text-base` (16px) | Smaller than headline |
| Button text | `text-sm` (14px) | All buttons |
| Footer links | `text-xs` | Extra small |
| Line height (small text) | `leading-5` | For 14px / text-sm text |

---

## Color Cheat Sheet

| Use Case | Value | Notes |
|----------|-------|-------|
| Gray family | `gray-*` (neutral) | NOT `slate-*` (has blue cast) |
| Primary accent | `gray-950` | *(Schoger preference: neutral-only, optional)* |
| Ring near shadow | `ring-1 ring-gray-950/10` | Outer ring, not inset |
| Well background | `bg-gray-950/5` | 5% opacity dark well |
| Well inset ring | `ring-1 ring-inset ring-gray-950/5` | Edge definition on screenshot container |
| Screenshot ring (overlay) | `ring-1 ring-inset ring-gray-950/10` | Absolute-positioned overlay on image |
| Supporting text | `text-gray-600` | Labels, descriptions, secondary copy |
| Body text | `text-gray-950` | Near-black for main text |
| Logo cloud fill | `fill-gray-950` or `text-gray-950` | Full opacity, no reduction |
| Gradient overlay | `bg-gradient-to-t from-black/70 to-transparent` | For text legibility over images |
| Testimonial quote | `text-white` | Text on gradient overlay |
| Testimonial attribution | `text-white/80` | Slightly dimmed on gradient overlay |
| Stats divider | `divide-x divide-gray-950/10` | Subtle separator between stat columns |
| Canvas grid borders | `border-gray-950/10` | 10% opacity, both vertical and horizontal |

**What to avoid:**

| Avoid | Replace with |
|-------|-------------|
| `text-indigo-*` / `bg-indigo-*` | `gray-950` or deliberate brand color |
| `bg-gray-50` / `bg-slate-50` on sections | White (`bg-white`) |
| `border border-gray-300` near a shadow | `ring-1 ring-gray-950/10` |
| `slate-*` gray family | `gray-*` (neutral) |

---

## Layout Cheat Sheet

| Element | Value | Notes |
|---------|-------|-------|
| Page container | `max-w-[1280px]` | Wider than Tailwind default |
| Split hero grid | `grid grid-cols-5` | 5-column grid for asymmetric split |
| Headline column | `col-span-3` | 3/5 of width |
| Supporting column | `col-span-2` | 2/5 of width |
| Split top alignment | `items-start` | Both columns top-aligned |
| Section heading alignment | `text-left` | Always left (override AI default `text-center`) |
| Stats layout | `w-full flex justify-between` | Full width with dividers |
| Footer grid *(Schoger preference, optional)* | `grid grid-cols-5` | 5-column footer |
| Feature card gap | `gap-2` | 8px between cards |
| Canvas grid (vertical) | `border-l border-r` on container | Stays at content width |
| Canvas grid (horizontal) | `border-t w-screen` | Full viewport width |
| Canvas grid color | `border-gray-950/10` | 10% opacity |
| Canvas grid padding | `p-2` | 8px gap between grid line and content |

---

## Component Cheat Sheet

### Buttons

| Component | Value | Notes |
|-----------|-------|-------|
| Hero button height | `py-2.5 px-5` | ~38px — never use `h-[38px]` |
| Hero button font | `text-sm rounded-full` | Pill shape, 14px |
| Nav CTA button | `py-1 px-3 text-sm rounded-full` | ~28px height |
| Secondary button border | `ring-1 ring-gray-950/10` | Ring instead of solid border |
| Button height parity fix | `<span class="inline-flex p-px">` + calc() | When ring adds ~2px visual height |
| Shadow placement | On `<button>` not `<span>` | Always on the interactive element |

### Screenshots / Image Wells

| Component | Value | Notes |
|-----------|-------|-------|
| Feature card well background | `bg-gray-950/5` | 5% opacity dark well |
| Feature card well ring | `ring-1 ring-inset ring-gray-950/5` | Edge definition |
| Feature card padding | `p-2` | 8px tight padding |
| Hero well padding | `p-16 pb-0` | 64px padding, no bottom padding |
| Hero bottom crop | `rounded-b-none` | Image bleeds to container edge |
| Screenshot ring overlay | `absolute inset-0 ring-1 ring-inset ring-gray-950/10 rounded-*` | Positioned on top of image |
| Concentric radius formula | `inner_radius = outer_radius - gap_width` | Inner must be smaller than outer |
| Screenshot resolution | Capture at `devicePixelRatio: 3` | 3x for crisp display |

### Testimonials

| Component | Value | Notes |
|-----------|-------|-------|
| Card background | `bg-cover bg-center` | Portrait photo as background |
| Gradient overlay | `bg-gradient-to-t from-black/70 to-transparent` | Dark shim for legibility |
| Quote position | `absolute bottom-4 left-4 right-4` | Bottom-pinned |
| Quote text | `text-white` | High contrast on dark overlay |
| Attribution | `text-white/80` | Slightly dimmed |
| Stars | Remove | Visual noise |
| Circular avatar | Remove | Visual noise |

### Stats

| Component | Value | Notes |
|-----------|-------|-------|
| Number size *(Schoger preference, optional)* | `text-5xl font-normal` | Large, not heavy |
| Label | `text-sm text-gray-600` | Small gray label below number |
| Divider | `divide-x divide-gray-950/10` | Subtle column separator |

### Navbar

| Component | Value | Notes |
|-----------|-------|-------|
| Backdrop blur | `backdrop-blur-*` | Accept if AI added — looks good |
| Sign-in link *(Schoger preference, optional)* | `ring-1 ring-gray-950/10` + shadow | Secondary button treatment |

---

*Back to SKILL.md → [Anti-Pattern Quick Scan](../SKILL.md#anti-pattern-quick-scan-)*
