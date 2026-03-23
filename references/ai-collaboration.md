# AI Collaboration Protocol

Full guide for working with Claude Code (or Cursor) on UI design tasks.

---

## Table of Contents
- [Initial Prompt Template](#initial-prompt-template)
- [Iteration Strategy](#iteration-strategy)
- [Override Table](#override-table)
- [Temporary Tool Pattern](#temporary-tool-pattern)

---

## Initial Prompt Template

**Copy-paste and fill in [BRACKETS]:**

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
- Specific colors or fonts — fix those in Gear 2
- Exact pixel values — iterate on these later
- Layout details for individual sections — let AI choose, then fix

**Philosophy**: First prompt gets to 60%. Speed > perfection at step 1. Accept the skeleton. Move to Gear 1 fixes immediately.

---

## Iteration Strategy

**Rule: One problem at a time. One prompt per change. Short prompts win.**

✅ **Good:**
```
Make the tracking in the headline a bit tighter.
```

❌ **Bad:**
```
Can you please adjust the letter spacing on the headline to be tighter, and also fix
the font weight, and maybe change the color of the supporting text, and also I think
the button is a bit too big and the logo cloud needs to be cleaned up...
```

**The Iteration Loop:**
1. Look at the page (not the code)
2. Identify the ONE most visually wrong thing
3. Write a short, specific prompt
4. Check the result
5. Repeat

**Globalizing patterns:** Once a pattern is correct in one section, apply to all:
```
Apply this same [PATTERN: eyebrow label style / screenshot well / heading style]
to all sections below.
```

AI learns from context and auto-applies patterns to new sections. Let it. Don't re-specify.

---

## Override Table

When AI makes a default choice, override these immediately. When AI makes a surface choice that looks good, accept it.

### Always Override

| AI Default | Fix |
|---|---|
| Center-aligns all text | Left-align everything |
| Uses indigo as primary color | Use gray-950 or deliberate brand color |
| Uses emerald/green as accent | Neutral palette or brand color |
| Loads basic Inter from Google Fonts | Variable Inter from rsms.me |
| Uses slate grays (blue cast) | Switch all to neutral |
| Solid borders near shadows | `ring-1 ring-gray-950/10` |
| Section titles on self-evident sections | Remove ("Trusted by", "Our Partners") |
| Stars + circular avatars in testimonials | Photo background + gradient overlay |
| Builds tools on separate localhost port | "Make it inline on the same page" |
| Fixed-height buttons (`h-[38px]`) | Padding-based height (`py-2.5 px-5`) |

### Accept Without Hesitation

| AI Suggestion | Why Accept |
|---|---|
| Adds `backdrop-blur` to navbar unprompted | It looks good. Keep it. |
| Auto-applies a style to sections you didn't mention | Check if it's right → accept |
| "Understands" a poorly-worded prompt and does the right thing | Don't second-guess |
| Suggests an implementation detail you didn't think of | Evaluate on visual merit |

**Rule**: Override on structure/system issues. Accept on surface details and happy accidents.

---

## Temporary Tool Pattern

Use when a design decision is visual and can't be numerically specified in advance.

### When to Use
- Screenshot crop position within a card
- Exact padding/spacing that "feels right"
- Any value you'd normally eyeball in Figma
- Positioning adjustments between elements

### Step-by-Step

**Step 1:** Identify the decision you can't spec.

Example: "Where should this screenshot be cropped within its container?"

**Step 2:** Prompt Claude Code to build the tool:

```
Build a temporary interactive tool inline on this page (not a separate port or domain).
I need to visually adjust [WHAT YOU'RE ADJUSTING: the crop position of the screenshot
in the feature section / the spacing between X and Y] using a slider or drag control.
Display the final CSS values as I adjust. When I'm done, I'll give you the final values
and you can bake them into the code and remove the tool.
```

**Step 3:** If Claude Code builds the tool on a different localhost port, say:

```
Make it inline on the current page, not a separate port or domain.
```

**Step 4:** Visually adjust until it looks right.

**Step 5:** Copy the displayed CSS values.

**Step 6:** Final prompt:

```
Use these values: [PASTE VALUES]. Bake them into the code and remove the tool.
```

### Why This Works

You can't spec visual feel numerically in advance. This pattern borrows the "eyeballing in Figma" workflow and applies it directly in Claude Code. The temporary tool is not a feature — it's scaffolding. Remove it when done.

---

*Back to SKILL.md → [AI Collaboration Protocol](../SKILL.md#ai-collaboration-protocol-key-patterns)*
