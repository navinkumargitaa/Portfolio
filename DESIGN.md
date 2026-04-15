# Design System Specification: High-End Engineering Editorial

## 1. Overview & Creative North Star: "The Digital Architect"
This design system moves away from the "generic developer template" and toward a high-end, editorial experience titled **"The Digital Architect."** The goal is to present software engineering not just as code, but as a disciplined craft. 

The system rejects the rigid, boxed-in constraints of standard web grids in favor of **intentional asymmetry** and **tonal depth**. By utilizing overlapping elements, massive typographic scales, and a "void-like" dark aesthetic, we create a sense of infinite space where the engineer’s work is the focal point. We prioritize breathing room over density, using whitespace as a functional tool to guide the eye through complex technical narratives.

---

## 2. Colors: Tonal Depth & Luminous Accents
The palette is rooted in deep, atmospheric navies, punctuated by a high-frequency mint accent.

### The "No-Line" Rule
**Explicit Instruction:** Traditional 1px solid borders are prohibited for sectioning or containment. 
Boundaries must be defined exclusively through:
1.  **Background Shifts:** Transitioning from `surface` to `surface-container-low`.
2.  **Negative Space:** Using the spacing scale to create distinct visual groups.
3.  **Luminous Glows:** Using subtle radial gradients of `primary` at 5-10% opacity to "lift" a section.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of semi-translucent materials. 
*   **Base Level:** `surface` (#08132a) – The infinite void.
*   **Section Level:** `surface-container-low` (#101b33) – Large content blocks.
*   **Interaction Level:** `surface-container-high` (#1f2942) – Hover states and elevated cards.
*   **Glassmorphism:** For floating navigation or modals, use `surface-container-highest` at 60% opacity with a `24px` backdrop-blur.

### Signature Textures
Avoid flat `primary` fills on large surfaces. Instead, use **Linear Accents**: A 2px gradient line (from `primary` to `transparent`) at the very top of a hero section or card to suggest a "light leak" from an internal source.

---

## 3. Typography: The Editorial Voice
We utilize a three-font system to create a sophisticated, technical-meets-editorial hierarchy.

*   **Display & Headlines (Plus Jakarta Sans):** These are the "Statement" elements. Use `display-lg` for hero headers with `letter-spacing: 0.04em`. This font provides a modern, geometric clarity that feels engineered.
*   **Body (Manrope):** Chosen for its superior readability at `font-weight: 300`. The generous `line-height: 1.8` ensures that even dense technical explanations feel approachable and airy.
*   **Technical Labels (Space Grotesk):** Used for `label-md` (tags, small caps, metadata). This adds a "monospaced-adjacent" feel that nods to the engineer's IDE without looking dated.

---

## 4. Elevation & Depth: Tonal Layering
In "The Digital Architect," depth is felt, not seen.

*   **The Layering Principle:** To lift a card, do not reach for a shadow first. Instead, place a `surface-container-highest` card atop a `surface-dim` background. The contrast in value provides all the separation necessary.
*   **Ambient Shadows:** If a component must float (e.g., a "Contact Me" FAB), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4)`. The shadow color should be a tinted version of `on-surface`, never pure black.
*   **The "Ghost Border" Fallback:** If accessibility requires a stroke (e.g., in high-glare environments), use the `outline-variant` token at **15% opacity**. This creates a "whisper" of a boundary that does not break the immersion.
*   **Subtle Glows:** Use the `primary` color for `box-shadow` on active elements (like a glowing "Online" status or an active CTA), but keep the spread high and the opacity low (15-20%) to mimic a soft neon bloom.

---

## 5. Components: Precision Engineered

### Buttons
*   **Primary:** Solid `primary` background with `on-primary` text. No border. `border-radius: md`. On hover, add a `4px` primary outer glow.
*   **Secondary:** `surface-container-highest` background with `primary` text. This creates a "recessed" look.
*   **Tertiary:** No background. Underline only on hover using a 1px `primary` stroke.

### Cards (Project/Experience)
*   **Style:** Forbid divider lines. Use `surface-container` tiers to separate the header from the body.
*   **Interaction:** On hover, the card should shift from `surface-container-low` to `surface-container-highest` and scale by 1.01% with a 300ms ease-out transition.

### Chips (Tech Stack)
*   **Visuals:** Use `label-md` (Space Grotesk). 
*   **Style:** Background: `secondary-container` at 30% opacity. Text: `secondary-fixed-dim`. This makes tags look "ghosted" and secondary to the main content.

### Inputs & Fields
*   **Base:** `surface-container-lowest`. 
*   **Active State:** A 1px bottom-border only of `primary`. Do not wrap the entire input in a box; keep it open and architectural.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use asymmetrical layouts. Place a large `display-lg` headline on the left and offset the body text to the right grid columns.
*   **Do** use "Motion as Meaning." Every hover should feel like a light turning on—slow, smooth, and deliberate.
*   **Do** leverage the `primary-fixed-dim` for links within body text to ensure they "pop" against the lavender-white `neutral` text.

### Don't
*   **Don't** use pure black (#000000). It kills the depth of the dark navy environment.
*   **Don't** use sharp corners. Always use at least `DEFAULT` (0.25rem) or `md` (0.375rem) roundedness to soften the "tech" feel.
*   **Don't** use icons without purpose. Icons should be minimal (2pt stroke) and consistent with the `outline` color token.