# KERAMIN — Online Store Website

Multi-page, shop-style website for the **Keramin** moisturising skin-care cream (Spanish, Salvadoran market), produced for **ACURELLA LIMITED** (Reg. no. CY10378872I).

| | |
|---|---|
| **Client** | ACURELLA LIMITED — CY10378872I |
| **Source code** | `github.com/9452296506/ACU_11_2026_SITE_CODE` |
| **Documentation** | `github.com/9452296506/ACU_11_2026_SITE` |
| **Product** | Keramin — crema para el cuidado de la piel, efecto hidratante · 60 ml tube |
| **Market / language** | El Salvador · Spanish (es-SV) |
| **Price shown** | $39.00 (USD, IVA incluido) |
| **Type** | Static multi-page storefront: 5 main pages + 3 legal pages, cart + checkout |

## Pages & navigation

Main navigation: **Inicio | Producto | Cuidado diario | Ingredientes | FAQ**. Cart icon with item count and a "Comprar ahora" (Buy now) button in the header on every page; "Añadir al carrito" / "Comprar ahora" in the shop blocks.

| Page | File | Content |
|---|---|---|
| Home | `index.html` | Editorial hero with scene chips (4 moments: text + lifestyle photo with tappable hotspots, polaroid overlays, decorative ring), zone tiles, intro statement, shop block (qty + add to cart + buy now), trust ticker, image pair, texture essay, formula feature cards, "how to buy" steps, brand story, "no surprises" cards, review rail, mini FAQ, contact + quick-order form |
| Product | `producto.html` | Gallery (7 photos), product info, qty selector, add to cart / buy now, details accordion, description & usage, packaging, 8 ingredients, application zones + expectations, precautions, reviews (6), delivery & payment table, quick-order form, sticky mobile buy bar, JSON-LD `Product` |
| Daily care | `cuidado-diario.html` | Dose (thin layer · 1–2×/day · 4 weeks), morning and evening routines, technique by zone, combining with other cosmetics, storage, 4-week programme |
| Ingredients | `ingredientes.html` | Urea (featured), salicylic acid, shea butter, aloe vera, calendula, vegetable oil, menthol, allantoin — purpose and INCI; synergy; banner |
| FAQ | `faq.html` | 15 questions in 2 groups, JSON-LD `FAQPage`, quick-order form |
| Legal | `privacidad.html`, `cookies.html`, `terminos.html` | Privacy Policy, Cookie Policy, Terms & Conditions (El Salvador consumer law), linked in every footer |

## Design

Palette derived from the packaging: white, sand (`#f7f4ef`), brick red (`#a8322b`, action colour), deep navy (`#1f2a44`), ink (`#1f2433`), green accent (`#5f7f62`). Font: **Roboto** (Google Fonts) for headings and body; italic accent words in headings. Tokens in `css/base.css`.

References agreed with the client: storefront structure of professional Shopify skincare shops (organicskincareshop.lt, berkovicz.pl); home-page block rhythm after kafiro.shop (text-led hero with hotspots, category tiles, product block, image pair, editorial text, numbered steps, brand story, promise cards, FAQ, contact).

## Cart & checkout

- `js/cart.js`: single product, quantity selector, add to cart, **Buy now** (adds the chosen quantity and opens checkout directly), drawer with subtotal, `localStorage` persistence (`km_cart_v1`), header badge, USD formatting (`$39.00`)
- Checkout modal: step indicator, order summary with quantity controls, Name + Phone + consent form; on success the cart is cleared
- Quick-order forms (Name + Phone) on Home, Product and FAQ as an alternative to the cart

## Order forms & lead integration

Forms: Name + Phone + privacy checkbox, each tagged with a `source` value (`home`, `producto`, `faq`, `checkout`). Client-side validation: name ≥ 2 characters, phone ≥ 8 digits, consent required.

Integration point in `js/main.js`:

```js
var LEAD_ENDPOINT = ''; // client's lead-submission URL
// POST JSON: { name, phone, product, qty, price, total, source, page }
```

While `LEAD_ENDPOINT` is empty, the forms validate and show the success state without sending. Once set, each valid submission is POSTed as JSON; a response `{ ok: false, message }` is shown inline. No server-side code ships with the site: the back-end is the client's existing lead-submission method.

## Features

- Sticky header, announcement bar, site search overlay (product, pages, sections, ingredients, FAQs), mobile slide-in menu
- Product hotspots on the home hero, hover-swap product images, trust marquee, horizontally scrolling review rail
- Product gallery, accordions (FAQ, product details, mini FAQ), breadcrumbs, back-to-top, smooth anchor scrolling, sticky buy bar on the product page (≤ 1000 px)
- Cookie notice with accept/decline, persisted in `localStorage` (`km_cookie_consent`)

## Responsive

Breakpoints: 1200 / 1100 / 1000 / 620 / 400 px. Verified at 1440, 1024, 820 and 390 px: no horizontal scroll.

## SEO

- Unique `<title>` and meta description per page; one `h1` per page
- Canonical URLs, Open Graph (`es_SV`), JSON-LD `Product` (USD) and `FAQPage`
- `sitemap.xml`, `robots.txt` (legal pages excluded)
- Optional `.htaccess`: clean extensionless URLs, asset caching, WebP/SVG MIME types
- Domain used in canonicals/sitemap/robots: `https://keramin.sv/`

## Tech stack

HTML5, CSS3, JavaScript + jQuery 3.7. Static site, no build step. CSS: `base`, `components`, `sections`, `home`. JS: `ui`, `cart`, `main`. Google Fonts (Roboto) and Font Awesome via CDN. Images: client photography downscaled to ≤ 1600 px (JPEG q84 / WebP q84), AVIF sources converted to JPEG for universal browser support, descriptive Spanish file names; SVG + PNG favicon.

## Project structure

```
/
├── index.html              Home
├── producto.html           Product
├── cuidado-diario.html     Daily care
├── ingredientes.html       Ingredients
├── faq.html                FAQ
├── privacidad.html         Privacy Policy
├── cookies.html            Cookie Policy
├── terminos.html           Terms & Conditions
├── css/                    base.css, components.css, sections.css, home.css
├── js/                     ui.js, cart.js, main.js
├── images/                 product photography + lifestyle photography, favicon
├── robots.txt, sitemap.xml, .htaccess
├── README.md, CHANGELOG.md, DELIVERY.md
```

## Deployment

1. Upload all files (optionally without `README.md`, `CHANGELOG.md`, `DELIVERY.md`) to the document root of the server/domain provided by the client.
2. `index.html` must be served as the default document.
3. In `js/main.js`, set `LEAD_ENDPOINT` to the lead-submission URL to activate order submissions.
4. If the production domain differs from `keramin.sv`, replace it in canonical URLs, Open Graph tags, `sitemap.xml` and `robots.txt`.
5. Apache: keep `.htaccess` for clean URLs. Nginx or static hosts: ignore it or add `try_files $uri $uri.html =404;`.

The site also runs locally by opening `index.html`.

## Site data

| Item | Value | Where |
|---|---|---|
| Operating company | ACURELLA LIMITED, Reg. CY10378872I, 27, 25 Martiou Str., D. Michael Tower, Office 105A, Engomi, 2408 Nicosia, Cyprus | footer, contact block, legal pages |
| Customer e-mail | info@keramin.sv | footer, contact block, FAQ, legal pages |
| Phone | not published; orders are confirmed by an outbound call from the client's call centre | — |
| Domain | keramin.sv | canonicals, OG, `sitemap.xml`, `robots.txt` |
| Price | $39.00 IVA incluido | all pages, `js/cart.js`, `js/main.js`, JSON-LD |
| Delivery terms | 1–3 business days San Salvador & metropolitan area, 2–5 rest of the country; cash on delivery; returns 7 days unopened | `producto.html`, `faq.html`, `terminos.html`, `index.html` |
| Reviews | 6 customer reviews adapted from the client's product materials (Spanish names and Salvadoran cities), 4.8 / 5 | `index.html`, `producto.html`, JSON-LD |

---

Prepared for ACURELLA LIMITED · Developer: Oleh Vozniak
