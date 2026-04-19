# Design System Strategy: The Elevated Voyager

## 1. Overview & Creative North Star
The "Creative North Star" for this design system is **"The Digital Concierge."** 

Unlike standard travel aggregators that feel like cluttered spreadsheets, this system adopts a high-end editorial approach. We move beyond the "template" look by utilizing intentional asymmetry, oversized typography for location names, and deep layered depth. The goal is to evoke the feeling of flipping through a premium travel magazine—where white space is a luxury and every interaction feels curated, not automated. We prioritize "Breathing Room" over "Information Density."

## 2. Colors: Tonal Depth & The "No-Line" Rule
Our palette is anchored in trust-inspiring blues and high-energy oranges, but the execution must remain sophisticated.

### The "No-Line" Rule
**Explicit Instruction:** 1px solid borders for sectioning are strictly prohibited. We define boundaries through background color shifts. To separate a booking card from the background, we do not draw a line; we place a `surface-container-lowest` element on a `surface-container-low` background.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of frosted glass.
*   **Base:** `surface` (#f8f9ff) for the primary application background.
*   **Sectioning:** Use `surface-container-low` (#f0f4fc) for large content areas.
*   **Elevated Content:** Use `surface-container-lowest` (#ffffff) for primary interactive cards. This creates a soft, natural lift.

### Signature Textures: The Gradient & Glass
*   **The Trust Gradient:** For primary actions and hero headers, transition from `primary-container` (#0078c7) to `primary` (#005f9f). This adds a "soul" to the interface that flat colors lack.
*   **Glassmorphism:** Floating navigation bars or header overlays must use a semi-transparent `surface` color with a `backdrop-blur` (20px-30px). This allows the vibrant travel photography to bleed through, softening the interface.

## 3. Typography: Editorial Authority
We use **Inter** not just for legibility, but as a structural element. 

*   **Display (lg/md):** Reserved for "Aha!" moments—flight prices or destination names. Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) to create an editorial impact.
*   **Headlines:** `headline-sm` (1.5rem) should be used for section titles, providing a clear entry point for the eye.
*   **Body:** `body-lg` (1rem) is our workhorse. Ensure a generous line-height (1.6) to maintain the premium, airy feel.
*   **Labels:** Use `label-md` (0.75rem) in `on-surface-variant` (#3f4752) for metadata (e.g., "Terminal 3" or "Non-refundable").

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are often "muddy." We achieve depth through light and tone.

*   **The Layering Principle:** Instead of shadows, stack `surface-container-highest` items inside `surface-container-low` containers to create "recessed" areas for secondary information.
*   **Ambient Shadows:** When an element must float (e.g., a "Book Now" sticky bar), use a multi-layered shadow: `0px 10px 40px rgba(0, 95, 159, 0.06)`. Note the tint—we use a tiny fraction of the `primary` blue, not black, to simulate natural light.
*   **The "Ghost Border" Fallback:** If accessibility requires a container edge, use `outline-variant` (#bfc7d4) at **15% opacity**. It should be felt, not seen.

## 5. Components: Fluidity & Softness

### Buttons
*   **Primary (CTA):** The `secondary-container` (#ff5e1f) with `on-secondary` white text. 
    *   *Style:* `xl` roundness (3rem), no shadow, but a subtle inner-glow (1px top-stroke in a lighter orange).
*   **Tertiary:** Purely text-based using `primary` color, used for "See All" or "View Map" to keep the UI clean.

### Cards & Lists
*   **Rules:** Forbid divider lines.
*   **The Travel Card:** Must use `DEFAULT` roundness (1rem) or `md` (1.5rem). Use vertical whitespace (24px - 32px) to separate items. Information should be grouped via typography scale, not boxes.

### Input Fields
*   **Interaction:** On focus, the container should shift from `surface-container-highest` to `surface-container-lowest` with a 2px `primary` ghost border. This "pop-out" effect guides the user's focus during the booking flow.

### Signature Component: The "Trip Pulse"
*   A progress indicator for multi-city trips using a soft `primary-fixed` (#d1e4ff) track with a `secondary` (#ab3500) indicator dot. It floats over images using glassmorphism.

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical layouts for image galleries (e.g., one large image paired with two smaller stacked ones).
*   **Do** use the `secondary` orange sparingly. It is a "trigger" color for conversion, not a decoration.
*   **Do** allow images to "break the grid" and bleed to the edge of the screen on mobile to increase immersion.

### Don't
*   **Don't** use 100% black (#000000) for text. Always use `on-surface` (#181c22) to keep the contrast soft and premium.
*   **Don't** use sharp corners. Everything—from checkboxes to full-screen modals—must have a minimum of `sm` (0.5rem) rounding to maintain the friendly, reliable vibe.
*   **Don't** use standard Material dividers. If you feel the need for a line, add 8px more whitespace instead.