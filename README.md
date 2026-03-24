# Design System Strategy: The Serene Manuscript

## 1. Overview & Creative North Star
This design system is built upon the "Creative North Star" of **The Serene Manuscript**. It is an editorial-first approach that treats the digital interface not as a utility, but as a digital sanctuary. We move away from the rigid, boxed-in layouts of standard mobile apps toward a high-end, spacious experience that mirrors the rhythmic beauty of Islamic calligraphy.

By leveraging intentional asymmetry, large typographic scales, and layered surfaces, we create a sense of "Meditative Flow." The interface should feel like it is breathing, using white space as a functional element rather than a void. This system rejects the "template" look in favor of a signature aesthetic where content is framed by sophisticated tonal depth and subtle geometric textures.

---

## 2. Colors
Our palette is rooted in the heritage of Islamic art, utilizing a deep, authoritative emerald and soft, luminous gold to guide the user’s eye.

*   **Primary Tier (`#003229`):** Represents the depth of the emerald. Used for high-emphasis elements and the primary brand presence.
*   **Secondary Tier (`#775a19`):** Our soft gold. Reserved for "The Golden Path"—the most important calls to action or indicators of sacred moments (e.g., prayer times, highlighted Ayahs).
*   **Surface Tier:** We utilize the `surface-container` tokens to create a sophisticated hierarchy without the need for visual noise.

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning or containment. Boundaries must be defined solely through background color shifts. For example, a featured "Dua of the Day" card should use `surface-container-low` sitting atop a `surface` background. This creates a soft, architectural transition rather than a hard stop.

### The "Glass & Gradient" Rule
To elevate the experience beyond flat design, floating elements (like a sticky prayer time bar) must use **Glassmorphism**. Apply `surface` or `surface-container-lowest` at 85% opacity with a `backdrop-blur` of 20px. 

### Signature Textures
CTAs and Hero backgrounds should utilize a subtle linear gradient transitioning from `primary` (#003229) to `primary_container` (#004b3e). This adds "soul" and prevents the deep green from feeling stagnant. Additionally, incorporate a low-opacity (2-5%) Islamic geometric pattern overlay on these containers to add tactile depth.

---

## 3. Typography
The typography is a dialogue between the modern world and ancient tradition.

*   **Display & Headlines (Noto Serif):** Used for titles and key headings. The serif terminals mimic the "Qalam" (pen) strokes of calligraphy. Use `display-lg` for prayer time digits or section titles to create an editorial, high-contrast look.
*   **Body & Labels (Plus Jakarta Sans):** A modern, geometric sans-serif that provides maximum readability for settings, descriptions, and functional UI.
*   **Quranic Text (Naskh):** While not in the base tokens, all Quranic scripture must be rendered in a high-quality Naskh font, prioritized at `headline-sm` or `title-lg` sizing to honor the text's importance.

---

## 4. Elevation & Depth
Depth is conveyed through **Tonal Layering** rather than traditional structural lines.

*   **The Layering Principle:** Stacking determines importance.
    *   Level 0: `surface` (The Base)
    *   Level 1: `surface-container-low` (Subtle sections)
    *   Level 2: `surface-container-lowest` (The "Elevated" Card)
*   **Ambient Shadows:** For elements that must float (e.g., a Bottom Sheet), use an extra-diffused shadow: `offset: 0, 12; blur: 40; spread: -4; color: rgba(0, 50, 41, 0.06)`. The shadow color is a tinted version of our Primary green, creating a natural, atmospheric lift.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use the `outline_variant` token at **15% opacity**. Never use 100% opaque borders.

---

## 5. Components

### Buttons
*   **Primary:** Rounded `full` (pill-shaped). Background: `primary` gradient. Text: `on_primary`. 
*   **Secondary:** Rounded `full`. Background: `secondary_container`. Text: `on_secondary_container`.
*   **States:** On hover/press, shift background to `primary_fixed_dim`.

### Cards & Lists
*   **The Divider-Free Rule:** Forbid the use of line dividers. Use a `1.4rem` (Spacing 4) vertical gap or a subtle background shift to `surface-container-low` to separate list items.
*   **Geometry:** Use `lg` (1rem) rounded corners for standard cards. Use `xl` (1.5rem) for major hero sections to create a softer, more inviting feel.

### Input Fields
*   **Styling:** Use `surface_container_highest` as the background. No border. Use `sm` (0.25rem) rounded corners.
*   **Focus State:** A "Ghost Border" of `secondary` at 40% opacity should fade in to indicate focus, symbolizing the "Gold" activation.

### Floating Sacred Bar (Specific Component)
A persistent element at the bottom of the screen showing the next prayer time. Use the **Glassmorphism** rule here with `surface_container_lowest` and a soft `secondary` (Gold) accent on the text.

---

## 6. Do’s and Don'ts

### Do:
*   **Embrace Asymmetry:** Place a heading at `display-md` and let the body text sit slightly offset to create a premium, editorial feel.
*   **Use the Spacing Scale:** Stick strictly to the scale (e.g., `5.5rem` for section margins) to ensure the "breathing" effect is consistent.
*   **Tint Your Greys:** Ensure all "neutral" surfaces have a slight hint of the emerald or gold base to keep the palette cohesive and "expensive."

### Don't:
*   **Don't use pure black:** Use `on_surface` (#191c1c) for text to maintain a soft, high-end contrast.
*   **Don't crowd the edges:** Elements should never be closer than `1.4rem` (Spacing 4) to the screen edge.
*   **Don't use standard shadows:** Avoid the default "black drop shadow." It muddies the emerald and gold aesthetic. Use the tinted Ambient Shadows described above.
