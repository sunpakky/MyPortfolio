# Design System Document: The Architectural Engineer

## 1. Overview & Creative North Star
**Creative North Star: "The Precise Monolith"**

This design system moves beyond the "standard developer portfolio" by embracing an editorial, high-end engineering aesthetic. It avoids the cluttered, component-heavy look of traditional dashboards in favor of **The Precise Monolith**: an experience defined by expansive white space, authoritative typography, and a "built, not rendered" structural integrity.

To break the "template" feel, this system leverages **intentional asymmetry**. Instead of centering all content, we use a heavy left-aligned typographic anchor with staggered secondary content to the right. We replace rigid 1px borders with **Tonal Sectioning**, creating a sense of depth through "layered slate" rather than outlines. The result is a digital space that feels like a premium architectural blueprint—calculated, clean, and indisputably professional.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a "Deep Slate" foundation, using "Professional Blue" as a surgical tool for emphasis, rather than a primary paint.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to define sections or containers. 
*   **The Technique:** Transitions between content blocks must be achieved via background shifts. Use `surface` (#f7f9fb) for the main canvas, and transition to `surface_container_low` (#f2f4f6) or `surface_container` (#eceef0) for secondary content areas. This creates a "milled" look, where elements appear carved out of the background.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of materials.
*   **The Base Layer:** `background` (#f7f9fb).
*   **The Inset Layer:** Use `surface_container_highest` (#e0e3e5) for inset code blocks or technical data visualizations to suggest they are "embedded" into the page.
*   **The Floating Layer:** Use `surface_container_lowest` (#ffffff) for high-priority cards, giving them a natural, bright lift against the off-white background.

### Signature Textures (The "Glass & Gradient" Rule)
To evoke high-end tech, use **Glassmorphism** for navigation bars and floating action menus.
*   **Token Usage:** `surface` at 80% opacity with a 12px `backdrop-blur`.
*   **The "Lead Engineer" Gradient:** For primary CTAs or Hero backgrounds, use a subtle linear gradient from `surface_tint` (#0053db) to `on_primary_container` (#497cff) at a 135-degree angle. This adds "soul" and depth to an otherwise flat minimalist environment.

---

## 3. Typography
The system utilizes a dual-font strategy: **Manrope** for structural authority and **Inter** for technical clarity.

| Level | Token | Font | Size | Character |
| :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | Manrope | 3.5rem | High-impact, tight tracking (-2%). For hero statements. |
| **Headline** | `headline-md` | Manrope | 1.75rem | Bold, architectural. For major project titles. |
| **Title** | `title-lg` | Inter | 1.375rem | Medium weight. For section headers. |
| **Body** | `body-lg` | Inter | 1rem | Regular weight, 1.6 line-height. For case study narratives. |
| **Label** | `label-md` | Inter | 0.75rem | All-caps, 0.05em tracking. For technical metadata (e.g., "STACK"). |

**Editorial Note:** Use `display-lg` sparingly. The contrast between a massive Manrope headline and a small, precise Inter `label-md` creates the "high-end editorial" tension that defines this system.

---

## 4. Elevation & Depth

### The Layering Principle
Depth is achieved through color, not just shadow. Place a `surface_container_lowest` card on a `surface_container_low` background. This creates a "Soft Lift" that feels modern and intentional.

### Ambient Shadows
Where floating elements are required (e.g., a "Back to Top" button or a Modal):
*   **Shadow Construction:** Use a multi-layered shadow with a 24px blur and 4% opacity, using the `on_surface` (#191c1e) color as the tint. It should feel like a soft glow of shadow rather than a dark smudge.

### The "Ghost Border" Fallback
If contrast is needed for accessibility, use the `outline_variant` (#c6c6cd) at 20% opacity. **Never use 100% opaque borders.**

---

## 5. Components

### Buttons
*   **Primary:** `surface_tint` background with `on_primary` text. Use `xl` (0.75rem) roundedness. 
*   **Secondary:** No background. `outline` (#76777d) "Ghost Border" at 20% opacity. `primary` text.
*   **Interaction:** On hover, primary buttons should shift to a subtle gradient; secondary buttons should fill with `surface_container_high`.

### Inputs & Text Fields
*   **Style:** Minimalist under-lines or "milled" insets. Use `surface_container` as the background with a `sm` (0.125rem) rounded bottom edge.
*   **Error State:** Use `error` (#ba1a1a) for text and `error_container` as a 5% opacity background wash.

### Technical Chips
*   **Style:** `surface_container_high` background, `on_surface_variant` text, `full` roundedness. No border. Use these for tagging languages (e.g., "TypeScript," "Rust").

### Architectural Cards
*   **Constraint:** **Forbid dividers.** Use `12` (3rem) vertical spacing from the scale to separate content blocks within a card. Use background color shifts to denote a footer or header within the card.

### Additional Component: The "Code Prism"
*   A specialized container for code snippets. Background: `inverse_surface` (#2d3133). Text: `inverse_on_surface` (#eff1f3). This provides a high-contrast "Dark Mode" moment within the light UI, signaling technical depth.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use asymmetrical layouts. Let a headline occupy the left 60% of the screen while the right 40% remains empty or holds a single metadata label.
*   **Do** use `surface_bright` to draw attention to the most important interactive element on a page.
*   **Do** prioritize "Breathing Room." When in doubt, increase spacing by one tier on the scale (e.g., move from `8` to `10`).

### Don'ts
*   **Don’t** use pure black (#000000) for text. Use `on_surface` (#191c1e) to maintain a soft, premium feel.
*   **Don’t** use standard 1px borders. If you feel the need for a line, use a 4px wide vertical "accent bar" of `primary` color instead.
*   **Don’t** crowd the interface. A Lead Engineer’s portfolio should feel like a gallery, not a repository.