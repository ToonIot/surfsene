# SURFSENE V5 Prototype

V5 evolves the static landing page into an interactive rental-service prototype.

## New in V5
- Product detail modal
- Product accessory selection UI
- Installation/service-mode selection
- Delivery-area estimator for Bangkok/metro, Central Thailand, and other provinces
- 14-day demo availability calendar
- Calendar date can populate rental pickup date
- Existing V4 rental cart, cost estimate, compatibility checker and V3 animated intro retained

## Prototype data disclaimer
Prices, inventory availability, delivery lead times, device specifications and calendar bookings are demo data only. Replace with approved pricing, real inventory/API data, actual product specifications and delivery SLA before commercial release.


### V6 Micro-interactions
- Scroll progress energy bar
- Ambient cursor glow
- Reveal-on-scroll
- Dynamic 3D catalog card tilt
- Hero live-data stream
- Floating SURFSENE Quick Start
- Active navigation highlighting
- Reduced-motion support

### V6.1 Fix
- Fixed invalid `document.querySelector('#')` from the home logo link.
- Header section observer now ignores `href="#"` and safely handles invalid selectors.

### V7 additions
- Mobile navigation drawer
- Product search and availability/protocol filters
- Smart Package Builder for Energy Audit, Environment, Gateway and Permanent Monitoring
- Sticky rental-cart summary
- Quote-request summary form (browser-only prototype)
- Lazy loading/async decoding on generated catalog images

### V8 additions
- Persistent cart and rental dates via localStorage
- Rental cart drawer with checkout shortcut
- Compare up to 3 rental products
- 3-question recommendation quiz
- Toast micro-feedback
- V7 features retained

### V9 additions
- Interactive Device → Gateway → SURFSENE Cloud → Dashboard data-flow section
- Clickable architecture nodes with protocol/context details
- Animated telemetry packets between architecture layers
- Live/Offline/Existing Equipment scenario selector
- Gentle simulated Volt/Amp/kW telemetry for UX demonstration
- Reduced-motion and hidden-tab handling for telemetry animation

### V9.1 UX adjustment
- Removed the intrusive bottom sticky rental summary bar.
- Rental cart now appears as a compact floating cart badge only when at least one item is selected.
- Clicking the compact cart opens the existing right-side rental cart drawer.

### V10 structure
- Fixed cart drawer `classList.toggle` error caused by a function/element global-name collision.
- Main landing page remains `index.html`.
- Added separate pages: `site-configurator.html`, `rental-simulator.html`, `rent-vs-buy.html`, and `live-dashboard.html`.
- All calculator values and telemetry remain demo/prototype data.

### V10.1 UX change
- Moved SURFSENE Interactive Tools directly after the service-model introduction and before delivery/catalog decision steps.
- Reframed the section as a customer decision aid rather than an auxiliary feature area.

### V10.2 UX cleanup
- Removed Recommendation Quiz from the landing page.
- Retained SURFSENE Interactive Tools as the early decision-support layer.
- Retained Smart Package Builder because it directly builds rentable solution packages.

### V10.3 Rental Journey redesign
- Moved "How to Rent" immediately before Rental Catalog where rental intent is highest.
- Rebuilt it as a prominent dark stepper/timeline with Choose → Schedule → Deliver → Measure & Return.
- Added clear Self-install vs On-site options and direct CTAs to Catalog and Rental Cost Simulator.

### V10.4 checkout-context UX
- Removed standalone Delivery Location / Availability section from landing page.
- Moved availability into Product Detail as "วันที่พร้อมให้เช่า" with a compact 14-day selector.
- Selecting an available date now populates the rental pickup date.
- Moved delivery area/destination selection into the Rental Cart Drawer.
- Delivery lead-time text remains explicit demo data.

### V10.5 Interactive Tools consolidation
- Removed standalone Compatibility Checker and Smart Package Builder sections from the landing page.
- Added both as cards inside SURFSENE Interactive Tools.
- Created `compatibility-checker.html` and `package-builder.html` as dedicated pages.
- Updated landing navigation so Tools becomes the central decision-support destination.

### V10.6 Intro frequency control
- Intro animation shows on first visit.
- The timestamp is stored in browser `localStorage` under `surfsene_intro_last_seen`.
- Returning to the landing page within 1 hour skips the intro immediately.
- After 1 hour, the intro is eligible to play again and the timestamp resets.
- If localStorage is unavailable, the page safely falls back to the normal intro behavior.

### V10.7 asset optimization
- Converted large photographic PNG assets to WebP quality 80.
- Hero image capped at 1600px wide.
- Installation/delivery imagery capped at 1280px wide.
- Catalog product imagery capped at 900px wide.
- Optimized PNG logo/favicon and retained alpha-capable branding assets where appropriate.
- Added lazy loading and async decoding for non-critical local images.

### V10.8 bug fix
- Restored the `openProduct()` product-detail modal function accidentally removed during the V10.5 Compatibility Checker extraction.
- Restored accessory rendering, modal close behavior, and "add to rental" from product detail.
- Exported `openProduct` to `window` for inline catalog handlers and retained the availability-calendar wrapper.

### V10.9 responsive hardening
- Responsive viewport with safe-area support for modern phones.
- Mobile/tablet/desktop breakpoints with overflow protection.
- Inputs render at 16px to prevent unwanted iOS Safari zoom.
- 40px+ touch targets for links/buttons and larger mobile menu button.
- Dynamic viewport height (`100dvh`) for mobile drawers and cart.
- Product detail becomes a bottom-sheet style modal on phones.
- Header logo and hero typography scale across 320px phones through large desktop screens.
- Hero background positioning tuned for phone/tablet/desktop.
- Horizontal page overflow prevention and responsive media defaults.
- Existing reduced-motion handling retained.

### V11 production CSS cleanup
- Removed Tailwind Play CDN from all pages.
- Compiled the Tailwind utilities used by this static project into `assets/css/tailwind.css` using the installed Tailwind compiler.
- All pages now load local static CSS; no Tailwind runtime is required in the browser.
- Removed `loading="lazy"` from the small set of local marketing/catalog images on the landing page to avoid Edge's lazy-image intervention console notice; optimized WebP assets and async decoding remain.
- JavaScript syntax and all local asset references were revalidated.

### V11.1 Smart Rental Catalog fix
- Reworked category filters into a clean segmented control with one visually active category.
- Removed the unwanted border appearance from every category button.
- Added ARIA tab semantics and visible keyboard focus.
- Mobile category filter becomes a compact 2-column control.
- Softened the search/filter panel background and standardized catalog-card borders.

### V11.2 catalog event-scope fix
- Fixed `filteredRender is not defined` when clicking Smart Rental Catalog categories.
- `filteredRender` is now explicitly exported on `window` because category buttons are generated with inline `onclick` handlers.
- Existing input/select listeners continue using the same local function.

### V11.3 catalog events hardened
- Removed all inline category `onclick` handlers, including the legacy `render()` category path.

### V11.4 About & Contact
- Added an About SURFSENE section explaining the rental → connectivity → permanent-monitoring service path.
- Added contact block for Natchapon Makkunchon with LINE and tap-to-call actions.
- Added About to desktop/mobile navigation and a compact contact shortcut in the footer.
