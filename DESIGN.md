# Design System Specification: High-End Editorial Dark Mode

This design system is engineered for a high-growth tech startup that prioritizes a premium, "Electric Editorial" aesthetic. It moves beyond standard SaaS templates by leveraging deep tonal layering, expansive negative space, and a high-contrast interplay between violet and emerald. The goal is to create an interface that feels like a curated gallery—authoritative, sophisticated, and immersive.

---

### 1. Overview & Creative North Star
**Creative North Star: "The Neon Observatory"**
The system is built on the concept of looking into a deep, infinite space where high-velocity data (Violet) and organic growth (Emerald) collide. 

**Breaking the Template:**
To avoid a generic "boxed" layout, this design system utilizes **Intentional Asymmetry**. We favor wide-gutter layouts and staggered content blocks. Instead of centering everything, we use the `24 (8.5rem)` spacing token to push content into unexpected but balanced positions, allowing the "near-black" background to act as a premium canvas rather than just a backdrop.

---

### 2. Colors & Surface Philosophy
The palette is rooted in a midnight base (`#0b1326`), accented by a dual-tone strategy: **Violet (`primary`)** for brand authority and **Emerald (`secondary`)** for conversion and success states.

#### The "No-Line" Rule
**Explicit Instruction:** Traditional 1px solid borders are strictly prohibited for sectioning. Boundaries must be defined solely through:
- **Background Color Shifts:** Moving from `surface` to `surface_container_low`.
- **Tonal Transitions:** Using subtle gradients to move the eye from one content area to the next.

#### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use a "Nested Depth" model:
1.  **Base Layer:** `surface` (#0b1326) – The infinite foundation.
2.  **Sectional Layer:** `surface_container_low` (#131b2e) – Used for secondary content blocks.
3.  **Component Layer:** `surface_container_highest` (#2d3449) – Used for primary interactive cards.
4.  **Floating Layer:** Glassmorphism (Semi-transparent `surface_bright` with 20px backdrop-blur).

#### The "Glass & Gradient" Rule
To add "visual soul," apply a linear gradient to main CTAs and Hero accents. 
- **Signature Gradient:** `primary` (#d2bbff) to `primary_container` (#7c3aed) at a 135-degree angle.
- **Glassmorphism:** For floating cards, use `surface_container_high` at 60% opacity with a `40px` backdrop blur. This allows the neon accents to "bleed" through the container, creating an integrated, atmospheric feel.

---

### 3. Typography
We use **Inter** exclusively to lean into its neutral, architectural precision, allowing our bold color palette to do the heavy lifting.

- **Display Scale (`display-lg` / `3.5rem`):** Reserved for Hero headlines. Set with `font-weight: 800` and `letter-spacing: -0.04em`. This creates a massive, "impact-first" editorial feel.
- **Headline Scale (`headline-lg` / `2rem`):** Used for section headers. Always paired with generous top padding (`spacing-20`).
- **Body Scale (`body-lg` / `1rem`):** High readability. Use `on_surface_variant` for secondary descriptions to maintain the hierarchy.
- **Label Scale:** Used for overlines and micro-copy. Always uppercase with `0.1em` letter spacing to denote a "technical" vibe.

---

### 4. Elevation & Depth
We eschew traditional drop shadows in favor of **Tonal Layering**.

- **The Layering Principle:** Place a `surface_container_lowest` (#060e20) card inside a `surface_container_high` (#222a3d) section to create a "recessed" look. This adds depth without the clutter of shadows.
- **Ambient Glows:** Instead of shadows, use "Bloom." Apply a `primary` color glow (10% opacity, 100px blur) behind key product shots to simulate light emitting from the screen.
- **The "Ghost Border" Fallback:** If a border is required for accessibility, use `outline_variant` at **15% opacity**. It should be felt, not seen.

---

### 5. Components

#### Buttons
- **Primary:** Large, prominent. Use the `primary_container` background with `on_primary_container` text. 
- **Shape:** `Rounded-full` (9999px) to contrast against the sharp, clean lines of the grid.
- **States:** On hover, apply a `secondary` (#4edea3) outer glow (bloom) rather than a color change.

#### Cards
- **Forbid Dividers:** Never use a line to separate card header from body. Use a `spacing-4` vertical gap.
- **Styling:** Use `surface_container_highest` with a `lg` (1rem) corner radius. Apply the Glassmorphism rule for cards that sit atop decorative background elements.

#### Inputs
- **Field Style:** Background should be `surface_container_lowest`. 
- **Focus State:** Transition the "Ghost Border" from 15% opacity to 100% `secondary` (Emerald). This provides a sharp, high-contrast feedback loop for the user.

#### Chips
- **Selection:** Use `secondary_fixed` for active states. These act as "high-voltage" markers against the dark background.

---

### 6. Do's and Don'ts

**Do:**
- **Do** use `spacing-24` (8.5rem) for section vertical padding. Luxury requires room to breathe.
- **Do** use Emerald (`secondary`) sparingly—only for success, conversion, or "active" indicators.
- **Do** utilize "Optical Centering"—sometimes a headline looks better slightly offset to the left in a wide viewport.

**Don't:**
- **Don't** use pure white (#FFFFFF). Always use `on_surface` (#dae2fd) to prevent "retina burn" in dark mode.
- **Don't** use 1px dividers. If you feel the need for a line, use a background color shift instead.
- **Don't** use standard shadows. If a component doesn't pop via tonal layering, its hierarchy needs to be re-evaluated.
- **Don't** crowd the corners. Ensure the `xl` (1.5rem) roundedness has enough internal padding (`spacing-6` or higher) so content doesn't feel "trapped."