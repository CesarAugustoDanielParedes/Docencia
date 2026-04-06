# Design System Document: The Editorial Feline

## 1. Overview & Creative North Star
**Creative North Star: "The Tactile Sanctuary"**

This design system moves away from the clinical, rigid grids of standard tech platforms to embrace the warmth of a physical, boutique café experience. We are building a "Tactile Sanctuary"—a digital environment that feels as soft, layered, and inviting as a sun-drenched rug. 

To break the "template" look, we employ **Intentional Asymmetry** and **Organic Layering**. High-quality imagery of cats should never be trapped in perfect squares; instead, they should overlap container boundaries or use organic, high-radius "squircle" masks. The goal is to move the user’s eye through a rhythmic flow of soft shapes and deep editorial typography, mimicking the relaxed movement of a cat through a room.

---

## 2. Colors & Surface Philosophy
The palette is rooted in warmth, using a spectrum of creams and muted roses to create a sense of calm.

### The "No-Line" Rule
Traditional 1px borders are strictly prohibited for sectioning. They create visual friction that contradicts our "cozy" personality. Instead, define boundaries through **Tonal Shifting**.
*   **Example:** A `surface-container-low` (#f5f3f3) section should sit directly against a `surface` (#fbf9f8) background. The transition is felt, not seen.

### Surface Hierarchy & Nesting
Treat the UI as stacked sheets of fine, heavy-weight paper. 
*   **Base:** `surface` (#fbf9f8) for the main canvas.
*   **Primary Containers:** Use `surface-container-low` (#f5f3f3) for large content areas.
*   **Interactive Cards:** Nest `surface-container-lowest` (#ffffff) cards inside low-tier sections to create a natural "pop" of cleanliness and focus.

### The "Glass & Gradient" Rule
To add soul to the interface, use subtle, long-form gradients for hero areas.
*   **Signature Gradient:** Transition from `primary` (#894e59) to `primary_container` (#feb2be) at a 45-degree angle to simulate the soft glow of a sunset.
*   **Glassmorphism:** For floating navigation or overlays, use `surface` at 80% opacity with a `24px` backdrop blur. This ensures the "warmth" of the content underneath bleeds through the interface.

---

## 3. Typography
We pair a modern, rounded sans-serif with a classic, high-legibility serif to balance playfulness with editorial sophistication.

*   **Display & Headlines (Plus Jakarta Sans):** The rounded terminals reflect the "soft corners" of the brand. Use `display-lg` (3.5rem) with tighter letter-spacing (-0.02em) for a high-end magazine feel.
*   **Body & Titles (Noto Serif):** The serif provides an "established" and "caring" tone. `body-lg` (1rem) is your workhorse for descriptions, providing a literary quality that encourages slow reading.
*   **Labels (Plus Jakarta Sans):** Use `label-md` (0.75rem) in uppercase with generous letter-spacing (0.05em) for a sophisticated, "curated" look on small metadata.

---

## 4. Elevation & Depth
Depth in this system is achieved through light and pigment, never through harsh shadows.

*   **The Layering Principle:** Avoid elevation shadows where possible. Instead, use the **Surface Tint** (`surface_tint`: #894e59). Apply a 2%–5% overlay of this tint on top of containers to indicate they are "closer" to the user.
*   **Ambient Shadows:** When a float is required (e.g., a "Book a Session" FAB), use an extra-diffused shadow: `0px 12px 32px rgba(137, 78, 89, 0.08)`. Notice the shadow uses the `primary` hue rather than grey, maintaining the warmth.
*   **The Ghost Border:** If a form field or button requires a container but the background is too similar, use `outline_variant` (#b2b2b1) at **15% opacity**. This creates a "whisper" of an edge.

---

## 5. Components

### Buttons
*   **Primary:** Uses `primary` (#894e59) with `on_primary` (#fff7f7) text. Corner radius: `full` (pill-shaped).
*   **Secondary:** Uses `secondary_container` (#feecce) with a "Ghost Border." 
*   **Interaction:** On hover, buttons should scale slightly (1.02x) rather than just changing color, mimicking a soft tactile "squish."

### Cards & Lists
*   **The No-Divider Rule:** Never use horizontal lines to separate list items. Use `24px` of vertical whitespace or alternating subtle background shifts (`surface` to `surface-container-low`).
*   **Imagery:** Cards must feature a `radius-lg` (2rem) and, where possible, a playful "paw print" icon overlapping the top-right corner of the image.

### Input Fields
*   **Styling:** Large padding (`1.5rem`) and `radius-md` (1.5rem). The background should be `surface-container-highest` (#e3e2e2) to look "inset" into the page.
*   **Focus State:** A soft 4px outer glow of `primary_fixed` (#feb2be) rather than a sharp border change.

### Narrative Components (Unique to This System)
*   **The "Cat-Log" Carousel:** A non-linear slider where images are varied in aspect ratio (some tall, some wide) to create a scrapbook feel.
*   **"Purr" Notifications:** Small, toasted-orange (`tertiary_container`) toasts that slide in from the bottom with a bounce effect.

---

## 6. Do's and Don'ts

### Do:
*   **Embrace Whitespace:** Give elements room to breathe. The "cozy" feeling comes from a lack of clutter.
*   **Use Intentional Asymmetry:** Offset text blocks from images to create a dynamic, editorial flow.
*   **Tone-on-Tone:** Use the `on_surface_variant` (#5f5f5f) for secondary text to keep the contrast soft and readable.

### Don't:
*   **Don't use pure black (#000000):** Use `on_background` (#323233) for all text to keep the visual "weight" soft.
*   **Don't use "Default" Shadows:** Avoid the standard CSS `0px 2px 4px rgba(0,0,0,0.5)`. It feels "cheap" and digital.
*   **Don't use sharp corners:** Even "none" radius components should have a minimum of `sm` (0.5rem) to stay on-brand.
*   **Don't use 1px Dividers:** If you feel the need to separate, use space. If space fails, use a tonal shift.