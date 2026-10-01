# Console Zone Design System

This document is the visual and interaction source of truth for the Console Zone Google Stitch project. Use it when generating new screens, revising existing screens, or translating Stitch concepts into production UI.

## 1. Product and brand

Console Zone is an Indian gaming-commerce platform where customers can rent, buy, and sell consoles and accessories, book repairs, complete KYC, and manage orders. The experience should feel like a premium gaming storefront rather than a generic marketplace.

### Brand attributes

- **Electric:** vivid purple accents, decisive typography, quick feedback.
- **Premium:** restrained surfaces, generous space, crisp product imagery.
- **Direct:** short action-oriented copy and obvious next steps.
- **Trustworthy:** transparent pricing, condition labels, warranty and delivery cues.
- **Gaming-native:** energetic angles and glow are welcome, but never at the expense of legibility.

### Voice

- Prefer short, confident phrases: “Choose your rig”, “Rent now”, “Add to cart”.
- Use gaming language sparingly. One expressive phrase per section is enough.
- Use sentence case for descriptions and form help; uppercase may be used for headings, labels, navigation, and CTAs.
- Show prices in Indian rupees with Indian digit grouping (for example, `₹42,999`).
- Never hide fees, deposits, stock state, rental duration, or product condition.

## 2. Visual direction

The interface is dark-first, high-contrast, and product-led. Black and graphite surfaces create depth; electric purple identifies actions and active states. Large italic display headings introduce energy, while body copy stays calm and readable.

### Design principles

1. **The product is the hero.** Use clean cutout imagery, a strong silhouette, and enough negative space.
2. **Purple communicates intent.** Reserve the primary purple for actions, selection, focus, and key emphasis.
3. **Glow is feedback, not decoration.** Apply a soft glow only to an active or promoted element.
4. **One dominant action per region.** Secondary actions should be quieter and visually distinct.
5. **Dense information needs structure.** Group pricing, fulfillment, warranty, and condition into scannable rows or chips.

## 3. Foundations

### Color tokens

| Token | Value | Use |
| --- | --- | --- |
| `background` | `#050505` | Page background and deep overlays |
| `surface` | `#0A0A0A` | Cards, panels, footer, menus |
| `surface-raised` | `#121212` | Media wells, inputs, nested panels |
| `surface-hover` | `#1A1A1A` | Hovered neutral controls |
| `primary` | `#A855F7` | Primary action, active state, links, focus |
| `primary-deep` | `#601CC9` | Purple gradients and pressed states |
| `secondary` | `#06B6D4` | Rare supporting data accents |
| `success` | `#10B981` | Availability, confirmed, Xbox-specific highlights |
| `signal` | `#39FF14` | Rare live/online signal; never a second CTA color |
| `text-primary` | `#FFFFFF` | Headings and high-emphasis text |
| `text-secondary` | `#9CA3AF` | Body copy |
| `text-muted` | `#6B7280` | Metadata and placeholders |
| `border` | `rgba(255,255,255,0.10)` | Default outline |
| `border-subtle` | `rgba(255,255,255,0.05)` | Section and card separation |

Primary glow: `0 0 20px rgba(168, 85, 247, 0.40)`. Use at most one glowing element within a component. Avoid glow behind paragraphs, form fields, and large regions.

#### Semantic color rules

- Purple means actionable, selected, or featured—not merely decorative.
- Green means success, available, or confirmed.
- Red means destructive, failed, or unavailable.
- Amber means warning, pending, or low stock.
- Pair every status color with text and/or an icon; color alone is insufficient.
- Maintain WCAG AA contrast for essential text and controls.

### Typography

- **Display and headings:** Inter, system sans-serif fallback; weights 800–900. Use tight tracking (`-0.03em` to `-0.06em`), uppercase, and optional italic styling for campaign-level headings.
- **Body and UI:** Inter, system sans-serif fallback; weights 400–700.
- **Technical metadata:** a monospace face may be used for eyebrow copy, codes, and compact pricing metadata.

| Style | Desktop | Mobile | Notes |
| --- | --- | --- | --- |
| Display XL | 96 px / 0.85 | 56 px / 0.9 | Home hero only |
| Display L | 72 px / 0.9 | 48 px / 0.95 | Page heroes |
| Heading 1 | 48–60 px / 1.0 | 36–40 px / 1.05 | Major sections |
| Heading 2 | 32–40 px / 1.1 | 28–32 px / 1.1 | Subsections |
| Heading 3 | 20–24 px / 1.2 | 18–20 px / 1.25 | Cards |
| Body L | 18–20 px / 1.5 | 17–18 px / 1.5 | Hero support copy |
| Body | 14–16 px / 1.6 | 14–16 px / 1.6 | General copy |
| Label | 10–12 px / 1.2 | 10–12 px / 1.2 | Uppercase, 0.12–0.2em tracking |

Do not set long descriptions in uppercase, italics, or below 12 px. Limit text lines to roughly 65–75 characters.

### Spacing and sizing

Use a 4 px base grid. Preferred spacing steps are `4, 8, 12, 16, 24, 32, 48, 64, 96, 128`.

- Page gutters: 16 px mobile, 24 px tablet, 32 px desktop.
- Standard content width: 1280 px (`max-w-7xl`).
- Narrow reading/forms width: 768 px.
- Section spacing: 64–80 px mobile, 96–128 px desktop.
- Minimum interactive target: 44 × 44 px.
- Fixed public navigation height: 64 px.

### Shape

- Inputs and compact controls: 16 px radius.
- Buttons: 16 px radius by default; hero campaign buttons may use the angled/skewed treatment.
- Standard cards: 24 px radius.
- Feature and campaign cards: 32–48 px radius.
- Pills and status chips: fully rounded.
- Avoid mixing more than two radius families in one component.

### Elevation and borders

Use surface contrast and fine borders before shadows. Default cards have a `1px` subtle border. Interactive cards may shift to a 50%-opacity primary border and a faint primary shadow on hover. Modal and floating panels may use a deep black shadow. Do not use light gray drop shadows.

### Iconography and imagery

- Use Lucide-style outline icons with consistent 1.5–2 px strokes.
- Use 16–20 px icons in controls and 24 px icons for standalone actions.
- Product images should be high-resolution cutouts on `surface-raised`, centered with 24–32 px breathing room.
- Lifestyle photography should be darkened enough to preserve foreground contrast; use an explicit overlay rather than altering text color.
- Do not place critical text inside imagery.
- Every informative image needs meaningful alt text; decorative images should be ignored by assistive technology.

## 4. Layout and responsive behavior

### Global shell

- A fixed translucent navigation sits at the top with logo left and primary destinations right.
- Public navigation order: Home, Rental, Shop, Sell, Services, account, cart.
- The current destination uses purple text and a 2 px glowing underline.
- The footer uses four columns on desktop and one column on mobile: brand/contact, categories, support, social/support hours.
- Primary content begins below the fixed header. Never allow the first interactive element to sit underneath it.

### Breakpoints

- **Mobile:** 0–767 px. Single-column layout, full-width primary actions, compact headings.
- **Tablet:** 768–1023 px. Two- or three-column grids where content permits.
- **Desktop:** 1024 px and above. Multi-column grids with a maximum content width of 1280 px.

Responsive behavior should be content-driven. Product grids typically progress from 1 to 3 to 4 columns. Feature grids progress from 1 to 3 columns. Checkout and sell flows stack the summary beneath the form on small screens; on desktop the summary may remain sticky in a right rail.

### Grid rules

- Default gap: 24 px mobile and 32 px desktop.
- Align headings, grids, filters, and footers to the same container edges.
- Keep image ratios consistent within any one product grid.
- Avoid masonry for commerce results because it makes comparison difficult.

## 5. Core components

### Buttons

**Primary:** purple fill, white bold uppercase label, optional trailing arrow. Hover brightens and adds a restrained glow. Pressed uses `primary-deep`. Disabled is lower-contrast and never glows.

**Secondary:** dark translucent fill, white text, subtle border. Hover raises the border and surface contrast.

**Tertiary:** text or icon only, muted by default and white/purple on hover.

**Destructive:** red-tinted surface and border; require confirmation for irreversible actions.

Button labels should be specific (“Schedule pickup”, not “Submit”). Show an inline spinner during asynchronous work and retain the button width to prevent layout shift.

### Product cards

A product card contains, in order:

1. Consistent-ratio image well.
2. Optional “Featured”, stock, or condition marker.
3. Product name, limited to two lines.
4. Short description, limited to two lines.
5. Category/condition chips.
6. Price label and price.
7. One primary card action.

Cards use `surface`, a subtle border, 24–40 px outer radius, and 24 px padding. Hover may lift by 2–4 px; never make a card jump or scale more than 1.02.

### Form controls

- Use persistent labels; placeholders provide examples, not labels.
- Field height is at least 48 px with 16 px horizontal padding.
- Default background is `surface-raised`; focus uses a primary border plus a visible focus ring.
- Validation appears beneath the field. State what happened and how to fix it.
- Group related inputs into titled sections and provide clear progress for multistep booking, checkout, and KYC.

### Chips and tabs

Use chips for compact metadata such as “Pre-owned”, “Rental”, and “6-month warranty”. Use tabs for switching one content region, such as PS5/PS4/Xbox rental plans. Selected tabs use a filled primary treatment; unselected tabs use neutral surfaces. If tabs overflow on mobile, make them horizontally scrollable with a visible continuation cue.

### Search and filters

Place category filters before search on desktop and stack them on mobile. Preserve filter state during navigation. Show the result count, an empty-state reset action, and removable active-filter chips when multiple filters are available.

### Navigation, cart, and account

- Cart count is a compact purple badge anchored to the bag icon.
- Mobile navigation opens below the header, traps focus while modal, and closes after selecting a destination.
- Account actions should clearly distinguish signed-out and signed-in states.
- Provide visible keyboard focus on every navigation element.

### Feedback patterns

- **Loading:** skeletons matching the final layout; use a spinner for button-level work.
- **Empty:** explain why the region is empty and provide one recovery action.
- **Success:** green icon plus a concise result and next step.
- **Error:** red icon plus plain-language recovery guidance.
- **Toast:** only for brief, non-blocking confirmation; never use a toast for information required to complete a task.

## 6. Screen specifications

### Home

1. Full-height hero with a single expressive headline, brief value proposition, and two CTAs: Rentals primary, Shopping secondary.
2. Optional campaign banner with deadline/code, one action, and no competing promotion.
3. Featured purchase products.
4. Rental products.
5. Reviews with rating, quote, customer, and location.
6. FAQ/support section.

Keep the first viewport focused. Do not show more than two hero actions or place product cards behind the headline.

### Rental discovery

- Page hero explains rental value and fulfillment area.
- Console-family tabs change the imagery and plan set without navigating away.
- Pricing cards compare Day, Week, and Month consistently.
- Mark one recommended plan, not several.
- State included controllers, games, deposit, delivery, and extra-controller price before booking.
- The selected console and plan must persist into the booking flow.

### Shop

- Hero followed by category filters and search.
- Desktop result grid uses four columns; tablet three; mobile one.
- Each product exposes purchase price, condition, stock status, and warranty.
- Filtering and search update the result count and empty state.
- Product detail should prioritize imagery, title, price, condition, warranty, delivery, and add-to-cart action in that order.

### Sell

- Begin with product search and pincode serviceability.
- Use a two-column desktop layout: eligible products on the left, valuation basket/summary on the right.
- Explain that displayed values are estimates until inspection.
- Show item quantity, estimated unit value, estimated total, pickup status, and payout method.
- The success state confirms the next contact window and offers a clear route back.

### Services

- Group services into hardware repair, controllers, cleaning, and software/storage.
- Each card includes scope, starting price, expected timing, and a book/contact action.
- Use trust cues such as diagnosis process and warranty rather than ornamental badges.

### Cart and checkout

- Show item image, name, type (purchase/rental), quantity or duration, unit price, and removal action.
- Order summary separates subtotal, delivery, deposit, discount, tax when applicable, and total.
- Keep the checkout CTA visible without obscuring content on mobile.
- Never combine refundable deposits with the merchandise subtotal without labeling them.

### Authentication, profile, and KYC

- Use a narrow centered form and progressive disclosure.
- Explain why identity data is required, how it is used, and what remains to complete.
- KYC progress and failure states must be explicit and recoverable.
- Mask sensitive identifiers after entry.

### Admin

Admin screens may be denser but must retain the same colors and typography. Favor tables, filters, status chips, and clear bulk actions over oversized marketing cards. Place destructive actions in menus or confirmation dialogs. Charts must include labels and accessible summaries; do not rely on color alone.

## 7. Motion and interaction

- Standard transition: 150–250 ms, ease-out.
- Page/section entrance: opacity plus no more than 20 px vertical movement, 300–500 ms.
- Hover lift: 2–4 px; card scale maximum 1.02.
- Background slideshows change no faster than every 5 seconds and must not interfere with reading.
- Use one entrance sequence per viewport. Avoid perpetual animation except a small live indicator or progress state.
- Respect `prefers-reduced-motion`: remove smooth movement, scale, marquee, auto-rotation, and nonessential parallax.

## 8. Accessibility and content quality

- Target WCAG 2.2 AA.
- Preserve semantic heading order and use landmarks for navigation, main content, and footer.
- Ensure all functionality is keyboard accessible with a clearly visible focus state.
- Icon-only controls require accessible names and tooltips where their meaning is not obvious.
- Dialogs trap focus, close with Escape, and return focus to their trigger.
- Announce cart changes, validation errors, loading completion, and dynamic result counts appropriately.
- Do not use gray-on-black combinations below AA contrast for meaningful text.
- Support zoom to 200% and widths down to 320 px without horizontal page scrolling.
- Tap targets must be at least 44 × 44 px and should not overlap.

## 9. Stitch generation guidance

When prompting or iterating in Google Stitch:

1. Start with a desktop frame and a corresponding mobile frame for every customer-facing screen.
2. Name layers semantically (`Product card`, `Price`, `Primary action`) rather than by appearance.
3. Reuse the tokens and component patterns in this document instead of inventing screen-specific styles.
4. Generate realistic product names, prices, rental durations, and stateful examples.
5. Include loading, empty, error, selected, disabled, and success states when the screen is interactive.
6. Keep purple as the sole primary-action color, even when product branding introduces green or blue.
7. Check the design at 320 px, 768 px, 1024 px, and 1440 px before handoff.

### Recommended Stitch prompt prefix

> Design a responsive Console Zone screen for a premium Indian gaming marketplace. Use a near-black `#050505` background, graphite `#0A0A0A` cards, white type, muted gray body copy, and electric purple `#A855F7` only for primary actions and selected states. Use bold, tightly tracked, optional italic uppercase display headings with readable Inter body copy. Favor spacious product-led layouts, subtle borders, soft active-state glow, 24 px card radii, clear pricing, and accessible high-contrast controls. Create both desktop and mobile variants and follow the Console Zone DESIGN.md.

## 10. Avoid

- Purple gradients or glow on every surface.
- Multiple competing primary CTAs in one region.
- Tiny uppercase paragraphs or over-tracked long text.
- Excessive glassmorphism that reduces contrast.
- Generic dashboard styling on customer storefront pages.
- Hidden fees, deposits, eligibility, stock, or warranty terms.
- Auto-playing media with sound.
- Layouts that depend on hover for essential information.
- Inconsistent radii, icon families, image ratios, or price formatting.

## 11. Handoff checklist

- [ ] Desktop and mobile frames exist.
- [ ] Tokens match this document.
- [ ] Primary, secondary, hover, focus, pressed, and disabled states are represented.
- [ ] Loading, empty, error, and success states are included where relevant.
- [ ] Content uses realistic Indian pricing and fulfillment details.
- [ ] Product condition, rental period, deposit, warranty, and stock are explicit.
- [ ] Keyboard order and focus treatment are documented.
- [ ] Contrast and tap-target checks pass.
- [ ] Images have alt-text intent documented.
- [ ] Layout remains usable at 320 px and 200% zoom.
