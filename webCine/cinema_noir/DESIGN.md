# Design System Document: The Cinematic Editorial

## 1. Overview & Creative North Star
### The Creative North Star: "The Projected Frame"
This design system rejects the "app-like" density of traditional interfaces in favor of a cinematic, large-format billboard experience. It is inspired by the high-contrast light of a projector in a pitch-black theater. We move beyond generic dark modes by utilizing **Organic Asymmetry** and **Tonal Depth**. 

The goal is to make the user feel like they are interacting with a living movie poster. We achieve this through aggressive typographic scales, "No-Line" containerization, and the intentional use of "Popcorn Red" and "Electric Yellow" to guide the eye through a void of deep blacks.

---

## 2. Colors: The High-Contrast Palette
Our color strategy relies on a "True Black" foundation (`#0e0e0e`) to allow our vibrant accents to "glow" as if back-lit.

### The "No-Line" Rule
**Strict Mandate:** Designers are prohibited from using 1px solid borders to define sections. 
- Use **Background Shifts**: Define the "Hero" area with `surface` and the "Coming Soon" section with `surface-container-low`.
- Use **Padding**: Leverage the Spacing Scale (e.g., `spacing.16`) to create mental boundaries through whitespace rather than physical lines.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers of varying opacity:
- **Base Layer:** `surface` (#0e0e0e) - The infinite void.
- **Secondary Content Areas:** `surface-container` (#1a1a1a) - Subtle lift for movie carousels.
- **Floating Overlays:** `surface-container-highest` (#262626) - For "Buy Ticket" modals or navigation drawers.

### The "Glass & Gradient" Rule
To add "soul" to the interface, use a subtle radial gradient on `primary` buttons, transitioning from `primary` (#ffe792) to `primary-container` (#ffd709). For high-impact hero moments, apply a `backdrop-blur` of 20px to `surface-variant` elements at 60% opacity to create a "Smoked Glass" effect.

---

## 3. Typography: The Editorial Voice
We use a tri-font system to create an authoritative, high-end editorial feel.

*   **Display & Headlines (Space Grotesk):** This is our "Billboard" voice. Use `display-lg` for movie titles. The wide, technical nature of Space Grotesk feels modern and architectural.
*   **Titles & Body (Manrope):** A sophisticated sans-serif that balances the tech-heavy headlines. Use `title-lg` for section headers and `body-lg` for synopses.
*   **Labels (Plus Jakarta Sans):** Used for metadata (Run time, Rating, Genre). The higher x-height ensures readability at small scales like `label-sm`.

**The Hierarchy Rule:** Never pair two fonts of the same weight. If the title is `Bold`, the metadata must be `Regular` or `Medium` to ensure the "Cinematic" contrast.

---

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are too "software-centric." We use **Ambient Glows** and **Tonal Stacking**.

*   **The Layering Principle:** Place a Movie Card (`surface-container-high`) onto a background of `surface-dim`. This 2-step jump in the container scale provides enough contrast to signify "lift" without a single pixel of shadow.
*   **The "Ghost Border" Fallback:** If a poster image is too dark and bleeds into the background, use an `outline-variant` at **15% opacity**. This creates a "breath" of light around the edge rather than a hard stroke.
*   **Ambient Shadows:** For floating "Book Now" buttons, use a shadow color derived from `on-secondary` (#4a0002) at 10% opacity with a `48px` blur. This simulates the red glow of a "Quiet Please" sign.

---

## 5. Components

### Movie Cards
*   **Structure:** No borders. Use `roundedness.lg` (0.5rem) for poster art.
*   **Separation:** Instead of dividers, use a `3.5rem` (spacing.10) vertical gap between rows.
*   **Overlay:** Movie titles should use `display-sm` and overlap the bottom 10% of the poster image using a `surface-container-lowest` to `transparent` gradient scrim.

### Showtime Badges
*   **Interactive:** Use `primary-container` for available times.
*   **Sold Out:** Use `surface-variant` with `on-surface-variant` text.
*   **Shape:** Use `roundedness.full` to create a "pill" that contrasts against the sharp, rectangular movie posters.

### Buttons (The "Action" Tier)
*   **Primary:** `primary` background, `on-primary` text. No border. `roundedness.md`.
*   **Secondary (Cinematic):** `surface` background with a 1px "Ghost Border" of `secondary` at 40% opacity. This is for "Trailer" or "More Info" buttons.
*   **Tertiary:** Text-only using `secondary` color.

### Responsive Navigation
*   **Desktop:** Asymmetric layout. Logo on the far left, links grouped on the far right using `label-md` for a clean, minimalist header.
*   **Mobile:** A "Glassmorphic" bottom dock using `surface-container-highest` with a 24px backdrop blur.

---

## 6. Do's and Don'ts

### Do
*   **Do** use extreme scale. A `display-lg` movie title next to a `label-sm` duration creates professional tension.
*   **Do** use `secondary` (Popcorn Red) sparingly as a "heartbeat" color—only for CTAs or live status indicators.
*   **Do** allow poster art to be the hero. Use the `background` color to let the art breathe.

### Don't
*   **Don't** use dividers or lines. If the layout feels messy, increase your `spacing` values.
*   **Don't** use pure white (#ffffff) for long body text. Use `on-surface-variant` (#adaaaa) to reduce eye strain in a dark environment.
*   **Don't** use "Standard" 400ms easing. Use a "Cinematic" 600ms ease-in-out for transitions to mimic the feel of a camera move.