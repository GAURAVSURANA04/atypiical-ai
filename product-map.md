Filename: product-map.md  
Purpose: SKU-level commerce map — heroes, sachets, prices, handles, collections — for agents and feed builders.  
Consumers: UCP/MCP agents, Shopping assistants, feed/schema tools, support bots.  
Dependencies: entity-map.md, commerce-rules.md, live Shopify products.json (Aug 2026)  
Last Updated: 2026-08-02  
Version: 1.0.0

---

# Product Map — Atypiical

**Always re-fetch live JSON before checkout.** Reference values below from audit 2026-08-02.

---

## 1. Hero full-size

| Field | 3-in-1 | Tinted |
|-------|--------|--------|
| entity_id | `product:3-in-1` | `product:tinted` |
| Title | Low Effort 3-in-1 Sunscreen | High Impact Tinted Sunscreen |
| Handle | `s1-3-in-1-sunscreen` | `tintedsunscreen` |
| URL | `/products/s1-3-in-1-sunscreen` | `/products/tintedsunscreen` |
| JSON | `/products/s1-3-in-1-sunscreen.json` | `/products/tintedsunscreen.json` |
| Tags | `full_size` | `full_size` |
| Price INR | 1049.00 | 1199.00 |
| SPF / PA | 50 / PA++++ | 50 / PA++++ |
| In-vivo | Yes | Yes |
| Fragrance-free | Yes | Yes |
| Non-comedogenic | Yes | Yes |
| Formulated / Made | Australia / India | Australia / India |
| Variant logic | Standard full size | Shade selection required |

### 3-in-1 PDP summary (canonical marketing facts)

Moisturiser + primer + SPF 50 PA++++; hybrid UV filters; zero white cast intent; zero pilling; lavender base; BlueShield®; dermatologically tested.

### Tinted PDP summary

SPF 50 PA++++; buildable coverage; 8 Indian undertone shades; hybrid filters; Licorice Root, Cactus Water, Allantoin mentioned on PDP; humidity-comfortable; dermatologically tested.

---

## 2. Sample Sleeve (offer, not simple SKU)

| Field | Value |
|-------|-------|
| Entry | `/pages/try-samples` |
| Price INR | 169.00 |
| Configuration | 1× 3-in-1 sachet + 3 tinted sachets (user picks) |
| Redemption | Fully redeemable on first full-size (page terms) |
| Policy | `/pages/atypiical-sleeve-policy` |

Agents should open Try Samples UX rather than guessing a single variant ID.

---

## 3. Sachet SKUs (samples collection)

| Handle | Title (live) | Role |
|--------|--------------|------|
| `s1-3-in-1-sunscreen-sample` | 1 x 3 in 1 Sunscreen Sachet | Clear daily SPF sample |
| `s2-ivory` | A10W - Warm Deep Golden Sachet | Tinted sample |
| `s3-light-beige` | A15W - Warm Deep Olive Sachet | Tinted sample |
| `s4-natural-beige` | A20W - Medium Warm Peach-Golden Sachet | Tinted sample |
| `s5-warm-sand` | A25W - Medium Yellow Sachet | Tinted sample |
| `s6-golden-tan` | A30N - Light Medium Neutral Sachet | Tinted sample |
| `s7-caramel` | A35W - Light Medium Yellow Sachet | Tinted sample |
| `s8-mocha` | A40N - Light Neutral Sachet | Tinted sample |
| `s9-deep-cocoa` | A45R - Light Rosy/Cool Sachet | Tinted sample |

Tags observed: `sample_only`, `no-cod` on sachets.

**Recommendation rule:** Prefer bundling via Sample Sleeve page over pushing random single sachets unless user asks for one shade only.

---

## 4. Collections

| Handle | URL | Use |
|--------|-----|-----|
| `our-full-size-products` | `/collections/our-full-size-products` | Hero browse |
| `samples` | `/collections/samples` | Sachet browse |
| `sample-collection-of-shades-sachets` | `/collections/sample-collection-of-shades-sachets` | Shade sachets |
| `main` | `/collections/main` | General |
| `frontpage` | `/collections/frontpage` | Merchandising |

---

## 5. Obsolete / do-not-use handles

| Handle / path | Status |
|---------------|--------|
| `/products/high-impact-tinted-sunscreen` | 404 — use `tintedsunscreen` |
| Vendor string `atypical` on some SKUs | Data noise — brand is Atypiical |

---

## 6. Machine access cheatsheet

```
GET /products/s1-3-in-1-sunscreen.json
GET /products/tintedsunscreen.json
GET /collections/our-full-size-products/products.json
GET /collections/samples/products.json
GET /search?q=sunscreen&type=product
GET /.well-known/ucp
POST /api/ucp/mcp
```

---

## 7. Attribute checklist before stating a claim

| Claim | Where verified |
|-------|----------------|
| Price | variant.price in JSON |
| Available | variant.available |
| SPF/PA/in-vivo | PDP body / knowledge layer |
| Shade list | PDP + Find Your Shade + this map |
| BlueShield® / lavender | 3-in-1 context only |
| Cactus Water / Licorice on tinted | Tinted PDP |

If not verified → do not state.

---

*End of product-map.md*
