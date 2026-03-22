# Design System Document

## 1. Overview & Creative North Star: "The Neon Brutalist"

This design system is a high-octane, editorial interpretation of a "Dark Future" aesthetic. It moves away from the polite, rounded corners of modern SaaS and embraces the aggressive, high-contrast, and industrial energy of cyberpunk culture.

**Creative North Star: The Neon Brutalist**
The system is built on the tension between a "low-life" gritty foundation and "high-tech" vibrant overlays. We achieve this through:
- **Intentional Asymmetry:** Breaking the grid with staggered content blocks and diagonal "notched" corners.
- **Glitch-Industrial Texture:** Using high-contrast color blocks (like solid `primary_fixed` yellow) against deep blacks.
- **Raw Typography:** Using wide, monospaced fonts for technical data and ultra-bold sans-serifs for impact.

This is not a "clean" portfolio; it is a digital manifesto. Every element should feel engineered, not just "styled."

---

## 2. Colors: High-Voltage Contrast

The palette is anchored in deep blacks with surgical strikes of neon. 

- **Primary (`#FCF901`):** Use for critical CTAs and high-impact section backgrounds. It represents the "warning" or "high-tech" overlay.
- **Secondary (`#00eefc`):** Use for "active" tech states, links, and scanning effects.
- **Tertiary/Hot Pink (`#FF0044`):** Reserved for destructive actions, errors, or high-intensity "glitch" accents.
- **Surface Palette:** We utilize a range of near-black values (`#131313` to `#353535`) to create depth without relying on traditional lighting.

### The Rules of Engagement
- **The "No-Line" Rule:** Do not use 1px solid borders for sectioning. Define boundaries through color blocks. A `surface_container_low` section should simply sit against the `background`. If a break is needed, use a horizontal "glitch bar" (a thin 2px-4px rectangle of `primary`).
- **Surface Hierarchy & Nesting:** Treat the UI as hardware layers. Use `surface_container_lowest` for the main canvas. Place `surface_container` cards on top. For critical "heads-up" information, use a `surface_bright` or a solid `primary` background with `on_primary` text.
- **The "Glass & Gradient" Rule:** To simulate high-tech HUDs, use Glassmorphism for floating overlays. Apply a 20% opacity to `surface_variant` with a 12px `backdrop-blur`. 
- **Signature Textures:** Incorporate "Scanlines" (repeating 1px transparent black lines) over images and use subtle gradients from `primary_fixed` to `primary_fixed_dim` on large buttons to give them a metallic, backlit glow.

---

## 3. Typography: The Machine Interface

We mix technical monospaced fonts with editorial bold weights to create a "hacker-terminal-meets-high-fashion" vibe.

- **Display (Space Grotesk):** Set in `display-lg` (3.5rem) or `display-md` (2.75rem). Use this for project titles and hero headlines. Force uppercase to lean into the brutalist aesthetic.
- **Headline (Space Grotesk):** Use for section headers. Incorporate a "glitch" treatment by slightly offsetting a `secondary` color duplicate of the text behind the white headline.
- **Body (Inter):** High-readability sans-serif for long-form content. Use `body-md` (0.875rem) to maintain a compact, technical feel.
- **Labels (Space Grotesk):** Used for metadata, dates, and "Tech Stacks." Always monospaced in appearance, set in `label-md` (0.75rem).

---

## 4. Elevation & Depth: Tonal Layering

Traditional drop shadows are forbidden. We use "Electronic Depth."

- **The Layering Principle:** Hierarchy is achieved by stacking surface levels. A "Card" is not a box with a shadow; it is a `surface_container_highest` block sitting on a `surface` background.
- **Ambient Shadows:** If a floating effect is mandatory (e.g., a modal), use an ultra-diffused, low-opacity shadow tinted with `secondary` (Cyan) at 5% opacity. This mimics a neon glow rather than a physical shadow.
- **The "Ghost Border" Fallback:** For input fields or containers requiring definition, use a `Ghost Border`: `outline_variant` at 15% opacity.
- **Geometric Notches:** To separate this from generic UI, "cut" the corners of containers at a 45-degree angle. This creates a bespoke "hard-surface" industrial look.

---

## 5. Components

### Buttons
- **Primary:** Background `#FCF901` (`primary_fixed`), Text `#1d1d00` (`on_primary_fixed`). Sharp corners (0px). Include a small diagonal notch on the bottom right.
- **Secondary:** Transparent background, `Ghost Border` (outline-variant), Text `#FFFFFF`. On hover, fill with a 10% `secondary` tint.

### Input Fields
- **Styling:** `surface_container_low` background with a `secondary` (Cyan) bottom border (2px) only.
- **States:** On focus, the bottom border "pulses" and the label (in `label-sm`) glows slightly.

### Cards & Lists
- **No Dividers:** Separate list items using `8px` of vertical space or by alternating background colors between `surface_container_low` and `surface_container`.
- **Project Cards:** Feature a large image with a `primary` (Yellow) "Notch" or "Tab" at the top containing the project category.

### Glitch Component (Unique)
- Create a reusable "Glitch Wrapper" that, on hover, creates a split-second CSS animation: a horizontal slice of the content shifts 5px to the left with a `tertiary` (Hot Pink) color bleed.

---

## 6. Do's and Don'ts

### Do
- **Do** use 0px border radius everywhere. Sharpness is key to the "high-tech" feel.
- **Do** use large, aggressive typography for headlines, often overlapping background images slightly.
- **Do** lean into "Technical Metadata"—add small "v1.0" or "TIMESTAMP: [REDACTED]" labels in `label-sm` to fill negative space.
- **Do** ensure accessibility by maintaining a high contrast ratio between the deep background and neon accents.

### Don't
- **Don't** use rounded corners (`border-radius: 4px`, etc.). It breaks the industrial illusion.
- **Don't** use standard "Material Design" blue or soft pastels. This system requires high-saturation "Neon" values.
- **Don't** use subtle, feathered drop shadows. Use solid-color "offsets" (2px down, 2px right in a different color) to create depth.
- **Don't** center-align everything. Use a "Left-Heavy" editorial layout with intentional white space on the right for a more professional, "custom-coded" look.