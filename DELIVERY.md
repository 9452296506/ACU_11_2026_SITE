# Delivery Note — KERAMIN Online Store Website

**Client:** ACURELLA LIMITED (Reg. no. CY10378872I)
**Project:** Shop-style multi-page website for the Keramin moisturising cream (Salvadoran market, Spanish), under the existing agreement
**Delivery date:** 26 November 2026

## Scope (as agreed)

Complete multi-page website in Spanish with the appearance and functionality of a modern Shopify-style online store, 5 main pages with navigation **Inicio | Producto | Cuidado diario | Ingredientes | FAQ**:

- **Home** — product presentation with images and packaging details, moisturising benefits and main ingredients, usage and daily-care recommendations, shop block, how to buy, brand/originality story, purchase conditions, reviews, FAQ, contact and quick-order form
- **Product** — description, product images and packaging details, benefits, 8 ingredients, usage instructions, application zones, precautions, price, reviews, payment and delivery information, quick-order form
- **Usage / Daily care** — dose, morning & evening routines, application technique by zone, use with other cosmetics, storage, 4-week programme
- **Ingredients** — the eight ingredients with cosmetic purpose and INCI
- **FAQ** — use, effects, availability, originality, ordering, payment, delivery, returns; quick-order form

Also: functional shopping cart with "Añadir al carrito" and "Comprar ahora" buttons; cart icon and visible "Comprar ahora" button in the header and relevant sections; simple checkout process and order form; information about payment and delivery; responsive design; working navigation and forms; cookie notice; basic SEO structure; Privacy Policy, Cookie Policy and Terms pages linked in the footer; price $39 throughout.

## Timeline

| Milestone | Date |
|---|---|
| Order agreed | 9 November 2026 |
| Development (13 days × 8 h) | 10 – 26 November 2026 |
| Delivery & invoice | 26 November 2026 |

Daily log: `CHANGELOG.md`.

## Technical requirements — status

| Requirement | Status |
|---|---|
| Clean, modern, natural and premium design, similar to professional Shopify skincare stores | ✅ Design system + per-page layouts after the references agreed with the client (`README.md`, "Design") |
| Each page with its own purpose and useful content | ✅ Informational copy per page, reworked from the client's product materials |
| Front-end: HTML5, CSS, JavaScript and jQuery | ✅ jQuery 3.7 (`js/ui.js`, `js/cart.js`, `js/main.js`) |
| Functional shopping cart with Add to Cart and Buy Now buttons | ✅ `js/cart.js`: quantity, drawer, persistence, Buy now → checkout |
| Simple checkout process and order form | ✅ Checkout modal (summary + Name/Phone form) and quick-order forms on Home, Product, FAQ |
| Basic front-end and back-end functionality | ✅ Front end complete; orders POST JSON to the client's lead-submission endpoint (`LEAD_ENDPOINT` in `js/main.js`); no separate server code is required for the agreed scope |
| Information about payment and delivery | ✅ Product page table, FAQ, promise cards on Home, Terms |
| Responsive design for desktop and mobile | ✅ Breakpoints 1200 / 1100 / 1000 / 620 / 400 px, sticky mobile buy bar |
| Working navigation, forms, cookie notice | ✅ |
| Product images and packaging details | ✅ Client photography: 7-image gallery, packaging section, hotspot figure, lifestyle photos |
| Basic SEO structure (titles, meta descriptions, headings, clean URLs) | ✅ JSON-LD `Product` and `FAQPage`, sitemap, robots, `.htaccess` for extensionless URLs |
| Privacy Policy, Cookie Policy and Terms links in the footer | ✅ Dedicated Spanish pages |
| Deployment to the server/domain provided by the client | ✅ Instructions in `README.md`; performed on access to the client's server/domain |

## Delivered components

- `index.html`, `producto.html`, `cuidado-diario.html`, `ingredientes.html`, `faq.html`
- `privacidad.html`, `cookies.html`, `terminos.html`
- `css/` — `base.css`, `components.css`, `sections.css`, `home.css`
- `js/` — `ui.js`, `cart.js`, `main.js`
- `images/` — product and lifestyle photography (web-optimised), favicon
- `robots.txt`, `sitemap.xml`, `.htaccess`
- `README.md`, `CHANGELOG.md`, `DELIVERY.md`

## Handover package

| Deliverable | Notes |
|---|---|
| Full source code | `github.com/9452296506/ACU_11_2026_SITE_CODE` |
| Delivery documentation (`README.md`, `CHANGELOG.md`, `DELIVERY.md`) | `github.com/9452296506/ACU_11_2026_SITE` |
| GitHub repository access | Granted to the client for both repositories |
| Downloadable archive of all website files | Provided with this delivery |
| Desktop & mobile screenshots | Provided with this delivery |
| Upload instructions | `README.md`, "Deployment" |

## Connecting the lead form

All order forms (checkout and quick order) post `{ name, phone, product, qty, price, total, source, page }` as JSON to the URL configured in `LEAD_ENDPOINT` (`js/main.js`). Provide the endpoint of your lead-submission method and set this value; until then the forms validate and confirm without sending.

## Before go-live

- Set `LEAD_ENDPOINT` (`js/main.js`) to the lead-submission URL.
- If the production domain differs from `keramin.sv`, replace it in canonicals, Open Graph tags, `sitemap.xml`, `robots.txt`; the customer e-mail `info@keramin.sv` should be active on that domain.
- Product claims, labelling and sanitary registration remain the client's responsibility.

## Service summary (for records)

| | |
|---|---|
| **Service (as invoiced)** | Website development / Tworzenie stron internetowych — design and front-end development of a shop-style multi-page website (UX/UI design, HTML5/CSS/JavaScript + jQuery programming incl. cart and checkout, SEO structure, content and image integration, testing, documentation, handover package) |
| **Repository (invoice reference)** | `github.com/9452296506/ACU_11_2026_SITE` — delivery documentation; `github.com/9452296506/ACU_11_2026_SITE_CODE` — source code |
| **Ordered by** | ACURELLA LIMITED, 27, 25 Martiou Str., D. MICHAEL TOWER, Office 105A, Engomi, 2408 Nicosia, Cyprus · NIP/VAT: CY10378872I (business customer, EU) |
| **Basis** | Order of 9 November 2026 under the existing framework agreement |
| **Period of performance** | 10 – 26 November 2026 (13 working days × 8 h = 104 h; daily log in `CHANGELOG.md`) |
| **Place of performance** | Performed remotely from Poland; results delivered electronically |
| **Classification** | Software-related services — programming of the website front end (PKWiU 62.01.11.0); registered lump-sum taxation (ryczałt), 12% rate |
| **Deliverables** | Full source code, documentation, downloadable archive, screenshots, repository access |
| **Settlement** | Invoiced on delivery (26 November 2026); bank transfer per the invoice terms; intra-EU B2B service — VAT reverse charge (np./na.), place of supply per Art. 28b |

## Acceptance

The project is **delivered and ready for review** as of **26 November 2026**. The client was provided with the handover package listed above. Deployment to the client's server/domain is performed once access is provided. Further changes are handled as a separate engagement.

---

Prepared for ACURELLA LIMITED · Developer: Oleh Vozniak · 26 November 2026
