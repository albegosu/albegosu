---
name: micrographic
description: Use this skill to build UI components, web pages, dashboards, or design systems with a micrographic aesthetic - dense, technical, schematic design inspired by industrial labels, hardware spec sheets, and Swiss modernist typography. Trigger when users mention "micrographic", "micro-graphics", "dense information UI", "schematic interface", "spec sheet style", "industrial aesthetic", "technical grid", "Maison Margiela style", "Virgil Abloh / Off-White aesthetic", "blueprint UI", or when they want UI that feels layered, precise, and data-rich. Also trigger for "technical", "engineering", "dense", or "compressed" visual design, or when the UI should feel like professional equipment, a scientific instrument, or a fashion brand's inner label. Use proactively whenever the design direction is monochromatic, typographically intense, and information-dense.
---

# Micrographic Design System

Micrographic design builds UI that operates at two scales simultaneously: visual texture from a distance, readable information up close. It draws from industrial product labeling, hardware spec sheets, care instruction tags, and Swiss modernist typography.

This is not minimalism. Minimalism removes. Micrographic compresses. Density should feel earned, not cluttered: every element has a specific job.

## Typography

Build typography first.

Preferred typefaces:
- Primary: Barlow Condensed, Barlow Semi Condensed, IBM Plex Sans Condensed, Roboto Condensed
- Mono: IBM Plex Mono, DM Mono, JetBrains Mono
- Fallback: `ui-sans-serif, system-ui, sans-serif`

Type scale:

```css
:root {
  --text-micro: 8px;   /* decorative only */
  --text-xs:   10px;   /* labels and tags */
  --text-sm:   11px;   /* body, rows */
  --text-base: 13px;   /* primary body copy */
  --text-md:   15px;   /* local headings */
  --text-lg:   20px;   /* section headings */
  --text-xl:   32px;   /* display numerals */
  --text-2xl:  56px;   /* hero values */
}
```

Rules:
- Use ALL CAPS + `letter-spacing: 0.08em` to `0.15em` for labels and categories.
- Use tight line-height for display (`1.0` to `1.1`) and normal for body (`1.4` to `1.6`).
- Use `font-variant-numeric: tabular-nums` for numeric data.

## Color

Use a near-monochromatic palette plus one accent.

```css
:root {
  --color-black:   #0A0A0A;
  --color-ink:     #1A1A1A;
  --color-dark:    #2A2A2A;
  --color-mid:     #555555;
  --color-muted:   #888888;
  --color-faint:   #BBBBBB;
  --color-border:  #D4D4D4;
  --color-surface: #F2F2F2;
  --color-white:   #FAFAFA;

  --color-accent:  #0033FF; /* pick one accent per screen */
}
```

Accent usage rule: one strong accent hit per screen. If it appears in three places, reduce usage.

## Spacing, Borders, Geometry

Use a strict 4px base grid:

```css
:root {
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
}
```

Shape rules:
- Border-radius: `0` to `2px` max.
- Borders define structure; avoid shadows and gradients.

Border tokens:

```css
:root {
  --border:        1px solid var(--color-border);
  --border-dark:   1px solid var(--color-dark);
  --border-accent: 1px solid var(--color-accent);
}
```

## Component Guidelines

- **Labels/Tags:** uppercase, tracked, bordered, compact padding (`2px 6px`).
- **Cards/Panels:** clear header/body/footer zones with hairline separators.
- **Buttons:** flat and sharp (`border-radius: 0`), fast transitions (`80ms`), no soft effects.
- **Tables:** dense grid feel, uppercase micro headers, monospaced numeric cells.
- **Forms:** labels in micro uppercase style, inputs with mono font and sharp borders.

## Decorative Micro-Elements

Sprinkle non-semantic schematic artifacts:
- Reference codes: `REF-4821-A`, `SKU/0042`, `REV.03`
- Serial strips
- Registration marks (`+`, `x`)
- Grid coordinates (`A1`, `B3`)

All decorative micro-elements must be `aria-hidden="true"`.

## Do / Don't

Do:
- Compress information intentionally.
- Repeat small visual elements for rhythm.
- Use borders and rules as primary structure.
- Keep palette grayscale + one accent.

Don't:
- Use soft rounded corners or friendly rounded typefaces.
- Add large shadows, blur, or multiple accent colors.
- Put critical information at 8px micro size.

## Accessibility

- Maintain WCAG AA contrast on readable text.
- Treat `--text-micro` as decorative only.
- Keep interactive targets at least 32px.
- Keep visible focus states (`outline: 2px solid var(--color-accent)`).
- Never rely on color alone for state changes.

## Starting Checklist

1. Import condensed + mono typefaces.
2. Define tokens (type, color, spacing, border).
3. Apply `border: var(--border-dark)` to component boundaries.
4. Add uppercase micro labels for sections/components.
5. Choose one accent and reserve it for primary emphasis.
6. Add at least one layer of spec annotations.
7. Use tabular numerals for every numeric view.
