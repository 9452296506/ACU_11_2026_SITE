# Changelog — KERAMIN Online Store Website

Prepared for **ACURELLA LIMITED** (CY10378872I). Versioning: [Semantic Versioning](https://semver.org/).

Development: daily stages of **8 working hours**, 10 – 26 November 2026 (104 h).

---

## [0.1.0] — 2026-11-10 · Project setup & UX planning (8 h)

### Added
- Brief analysis: Shopify-style store with cart and simple checkout, 5-page structure, Salvadoran market, price $39 (USD)
- Content extracted from the client's Keramin product materials (description, 8 ingredients, effects, target users, contraindications, step-by-step usage, official-store and originality notes, FAQ, testimonials) and reworked into informational page copy in Spanish
- Reference review (professional Shopify skincare stores agreed with the client) and store structure: Inicio | Producto | Cuidado diario | Ingredientes | FAQ + legal pages; cart icon and "Comprar ahora" in the header
- Wireframes for the five main pages (desktop, mobile), cart drawer and checkout flow
- Project scaffolding: `css/`, `js/`, `images/`

## [0.2.0] — 2026-11-11 · Design system & shared frame (8 h)

### Added
- Design tokens from the packaging (white / sand / brick red / deep navy), Roboto, spacing and component styles (`css/base.css`)
- Announcement bar, sticky single-row header (logo, centred navigation, search, cart with badge, "Comprar ahora"), footer (tagline, shop and customer-service links, contact)
- Wordmark with leaf mark (inline SVG), SVG + PNG favicon
- Mobile slide-in navigation with overlay, ESC and close-button handling (`js/ui.js`)
- Button, form, badge and notice primitives with validation states

## [0.3.0] — 2026-11-12 · Cart & checkout (8 h)

### Added
- Cart (`js/cart.js`): quantity selector, add to cart, **Buy now** (adds the chosen quantity and opens checkout), drawer with subtotal and perks, `localStorage` persistence, header badge, USD formatting
- Checkout modal: step indicator, order summary with quantity controls, Name + Phone + consent form, cart cleared on success
- Shop components: product card with hover-swap image, quantity control, mini shoppable card, sticky buy bar (`css/components.css`)

## [0.4.0] — 2026-11-13 · Product page (8 h)

### Added
- Gallery (7 photos) with thumbnails, product info, checklist, price, quantity + add to cart / buy now, meta strip, specification list, details accordion
- Description and usage blocks, packaging section, 8-ingredient grid
- Application zones (3 cards) + expectations timeline, precautions, reviews (6), delivery & payment table, quick-order form
- Breadcrumbs for subpages; JSON-LD `Product` (USD)

## [0.5.0] — 2026-11-16 · Home page, part 1 (8 h)

### Added
- Editorial hero on a soft gradient with a decorative ring: italic accent word, scene chips (después de la ducha / manos / codos y rodillas / piel seca) switching subtitle, text and lifestyle photo; white-ring hotspots on each photo; polaroid overlays (packshot, tube in hand); italic caption
- Zone tiles row (manos, codos y rodillas, pies y talones, brazos y piernas, descamación)
- Intro statement, shop block (wide product card with quantity, add to cart, buy now), trust marquee

## [0.6.0] — 2026-11-17 · Home page, part 2 (8 h)

### Added
- Image pair, "Textura y sensación" essay block, formula feature cards (3)
- "Cómo comprar" numbered steps (4), brand story with photo pair, "Compra sin sorpresas" promise cards (4)
- Review rail (horizontal snap scroll), mini FAQ accordion, contact block with quick-order form
- Home-only styles split into `css/home.css`

## [0.7.0] — 2026-11-18 · Daily care page (8 h)

### Added
- Page hero, dose block (thin layer · 1–2×/day · 4 weeks)
- Morning and evening routines (step grids)
- Application technique by zone (hands, elbows and knees, feet, legs and arms, flaky areas)
- Compatibility with other cosmetics, storage & travel tips
- 4-week programme cards, CTA banner

## [0.8.0] — 2026-11-19 · Ingredients page & site search (8 h)

### Added
- Split page hero with packshot
- Featured ingredient (urea) with INCI
- 7 ingredient cards (salicylic acid, shea butter, aloe vera, calendula, vegetable oil, menthol, allantoin) with INCI, INCI notice, pill strip, synergy section, banner strip
- Site search overlay with static index (`js/main.js`)

## [0.9.0] — 2026-11-20 · FAQ & legal pages (8 h)

### Added
- FAQ page: "Producto y uso" (7), "Pedidos, pago y envío" (8), quick-order form, JSON-LD `FAQPage`
- Privacy Policy, Cookie Policy, Terms & Conditions (El Salvador consumer law, USD pricing, cash on delivery, 7-day return)
- Cookie notice with accept/decline and persisted consent
- Back-to-top button, smooth anchor scrolling

## [0.10.0] — 2026-11-23 · Imagery, forms & lead integration (8 h)

### Added
- Client photography processed: packaging photos downscaled to ≤ 1600 px (JPEG q84, e.g. 3024×4032 / 1.2 MB → 1200×1600 / 105 KB), lifestyle photos to ≤ 1200 px, AVIF sources converted to JPEG, WebP kept; descriptive Spanish file names
- Image-to-section mapping on all pages, `alt` texts
- Order forms: validation (name, phone, consent), disabled submit during send, success/error messages
- Lead-submission integration point `LEAD_ENDPOINT` in `js/main.js` (JSON POST incl. qty and total, inline server message support)

## [0.11.0] — 2026-11-24 · SEO & structured data (8 h)

### Added
- Titles, meta descriptions, canonical URLs, Open Graph (`es_SV`)
- JSON-LD `Product` (USD) and `FAQPage`
- `sitemap.xml`, `robots.txt`; `.htaccess` (clean URLs, caching, WebP/SVG MIME)
- `lang="es"`, favicon links

## [0.12.0] — 2026-11-25 · Responsive, accessibility & cross-browser QA (8 h)

### Fixed
- Responsive pass at 1200 / 1100 / 1000 / 620 / 400 px on all 8 pages; zone tiles and review rail scroll horizontally on phones; sticky buy bar on the product page; no horizontal scroll
- Skip link, focus order, `aria-expanded` on accordions and hotspots, `aria-hidden` on overlays, labelled icon buttons, form error states, reduced-motion fallback for the marquee
- Cross-browser check (Chromium, Firefox, WebKit); `file://` smoke test
- Cart and checkout flows: quantity edge cases, buy now from every page, success/error states; Spanish proofreading (Salvadoran usage)

## [1.0.0] — 2026-11-26 · Final QA & delivery (8 h)

### Added
- Final link and image-weight check
- `README.md`, `DELIVERY.md`, changelog; delivery package (archive + desktop and mobile screenshots)

### Notes
- `LEAD_ENDPOINT` (`js/main.js`) must be set to the client's lead-submission URL to activate live order submissions.
- Production domain `keramin.sv` is used in canonicals, Open Graph, `sitemap.xml` and `robots.txt`; replace if the client deploys elsewhere.

---

**Engagement timeline**

| Milestone | Date |
|---|---|
| Order agreed | 2026-11-09 |
| Development (13 working days × 8 h) | 2026-11-10 → 2026-11-26 |
| Delivery & invoice | 2026-11-26 |
