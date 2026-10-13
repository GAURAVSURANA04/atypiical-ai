# Product Map — Atypiical

**Always re-fetch live JSON before checkout.** Snapshot **2026-10-13**.

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
| Size | **40 ML** (variant title) | Not stated on the variant title. Do not copy “30 ml” from a review |
| SKU | ATY10001 | ATY10002–ATY10009 by shade |
| SPF / PA | 50 / PA++++ | 50 / PA++++ |
| In-vivo | Yes, ISO 24444:2019 (Science page, both heroes) | Same |
| Sweat resistant | Badge on PDP | Badge on PDP. Not a waterproof or water-resistant claim |
| Fragrance-free | Yes | Yes |
| Non-comedogenic | Yes | Yes |
| Vegan / cruelty-free | Yes, per PDP FAQ | Yes, per PDP FAQ |
| Dermatologically tested | Yes. Science page: patch test, 26 sensitive-skin subjects, reported non-irritant | Same |
| Formulated / Made | Australia / India | Australia / India |
| Shipping line on PDP | “Free shipping on all orders” | Same. COD is not free — see shipping policy |
| Variant logic | Single variant, 40 ML | Shade required |

Availability on 2026-10-13: 3-in-1 and all 8 tinted full-size variants `available: true` in collection JSON. Re-check before saying a shade is in stock.

### 3-in-1 — what the PDP actually says

Moisturiser + primer + SPF 50 PA++++. Hybrid UV filters. Zero white cast intent. Zero pilling. Lavender base that cancels yellow undertones. BlueShield® (the explanatory block uses ®; a feature card also prints BlueShield™). Sweat-resistant badge. Two finger-lengths for face and neck. Reapply every 2–3 hours when outdoors. Can sit under the tinted sunscreen.

**Named filters (PDP FAQ + INCI):** Avobenzone (Butyl Methoxydibenzoylmethane), Octinoxate (Octyl Methoxycinnamate), Tinosorb S (Bemotrizinol), Ethylhexyl Triazone, Tinosorb M (Methylene Bis-Benzotriazolyl Tetramethylbutylphenol), Zinc Oxide, Titanium Dioxide.

**Named skin ingredients on the 3-in-1 INCI:** Niacinamide, Tocopheryl Acetate, Capsicum Annuum Fruit Extract, Betaine, Glycerin. Colour: CI 77007, CI 77491.

**Not on the 3-in-1 INCI (do not claim):** Licorice Root, Allantoin, Cactus Water. Those are tinted-formula ingredients.

### Tinted — what the PDP actually says

SPF 50 PA++++. Eight Indian undertones. Buildable light-to-medium coverage (one layer or two). Finish described as dewy on application, setting natural-matte. FAQ says it does not oxidise. Enriched with Licorice Root, Cactus Water (Opuntia Ficus-Indica Stem Water), and Allantoin.

**FAQ filters:** Zinc Oxide, Titanium Dioxide, Tinosorb M. Mineral-forward hybrid. INCI also lists iron oxides as CI 77491, CI 77492, CI 77499, and CI 77891.

**Two instructions on the same PDP — state both:**

- FAQ: it is a complete standalone SPF 50 PA++++. Layer the 3-in-1 underneath for extra moisture.
- How to use: labelled SPF 50 PA++++ needs the recommended amount, which can feel like a lot. The suggested lighter method is 3-in-1 first, then tinted for coverage.

### Full-size shade names (homepage + variant titles)

| Code | Full-size name | SKU | Sachet title still live on Try Samples | Sachet handle | Sachet SKU | Sachet available 2026-10-13 |
|------|----------------|-----|----------------------------------------|---------------|------------|------------------------------|
| A10W | Deep Warm Golden | ATY10002 | A10W - Warm Deep Golden Sachet | `s2-ivory` | ATY10017 | true |
| A15W | Deep Warm Olive | ATY10003 | A15W - Warm Deep Olive Sachet | `s3-light-beige` | ATY10016 | true |
| A20W | Medium Warm Peach | ATY10004 | A20W - Medium Warm Peach-Golden Sachet | `s4-natural-beige` | ATY10015 | true |
| A25W | Medium Warm Yellow | ATY10005 | A25W - Medium Yellow Sachet | `s5-warm-sand` | ATY10014 | **false** |
| A30N | Light Medium Neutral | ATY10006 | A30N - Light Medium Neutral Sachet | `s6-golden-tan` | ATY10013 | true |
| A35W | Light Medium Yellow | ATY10007 | A35W - Light Medium Yellow Sachet | `s7-caramel` | ATY10012 | true |
| A40N | Light Neutral | ATY10008 | A40N - Light Neutral Sachet | `s8-mocha` | ATY10011 | true |
| A45R | Light Rosy/Cool | ATY10009 | A45R - Light Rosy/Cool Sachet | `s9-deep-cocoa` | ATY10010 | **false** |

Undertone letters: W = Warm, N = Neutral, R = Rosy/Cool.

Use full-size names when talking about the hero. Use sachet titles only for sachet URLs. Sachet price in JSON: **₹42.25** each. Tags: `sample_only`, `no-cod`.

3-in-1 sachet: handle `s1-3-in-1-sunscreen-sample`, SKU ATY10018, ₹42.25, available true on 2026-10-13. Title: “1 x 3 in 1 Sunscreen Sachet”.

---

## 2. Sample Sleeve (offer, not a simple SKU)

| Field | Value |
|-------|-------|
| Entry | `/pages/try-samples` |
| Live page price | **₹169** inclusive, shown as fully redeemable |
| Policy-page price | **₹140** on `/pages/atypiical-sleeve-policy` (effective 26 March 2026, still written against `atypiical.in`) |
| What to quote | The amount on Try Samples at the moment of the answer. Mention the policy figure only as the number that page still prints |
| Configuration | 1× 3-in-1 sachet + 3 tinted sachets the buyer picks |
| Redemption on Try Samples | Full amount off the first full-size order, applied at checkout, no code |
| Redemption on the policy page | Credit valid 3 months, same account or contact, once per Sleeve, not cash, not on Amazon or Nykaa |
| Volume copy on Try Samples | Conflicts: “each sachet contains 1.5 ml” and, later, 3-in-1 as a **15 ml** sachet plus three **1.5 ml** tinted sachets. Do not pick one |
| Dispatch copy | Try Samples: 1–2 business days, delivery estimate 4–7 business days, shipping on us. Policy page: dispatch 3–5 business days; metro 2–4, tier 2/3 4–7, remote 7–10 after dispatch |
| Policy exceptions | Damaged/defective: report to info@atypiical.in within 48 hours with photo or video; replacement, not cash. Lost in transit: report within 14 days of the estimated date. Policy says Sleeve orders cannot be cancelled |

Agents open the Try Samples UX. They do not guess a single variant ID for the kit.

---

## 3. Collections

| Handle | URL | Use |
|--------|-----|-----|
| `our-full-size-products` | `/collections/our-full-size-products` | Hero browse |
| `samples` | `/collections/samples` | Sachet browse, includes the 3-in-1 sachet |
| `sample-collection-of-shades-sachets` | `/collections/sample-collection-of-shades-sachets` | Eight tinted sachets only |
| `main` | `/collections/main` | General |
| `frontpage` | `/collections/frontpage` | Merchandising |

---

## 4. Obsolete / do-not-use

| Handle / path | Status |
|---------------|--------|
| `/products/high-impact-tinted-sunscreen` | 404 — use `tintedsunscreen` |
| `/blogs/news/how-to-stop-skipping-sunscreen-because-of-your-morning-routine` | 404 — use `how-to-fix-skipping-sunscreen-because-of-your-morning-routine` |
| Vendor string `atypical` on the tinted product and sachets | Data noise. Brand is Atypiical. 3-in-1 vendor field is `atypiical` |

---

## 5. Machine access

```
GET /products/s1-3-in-1-sunscreen.json
GET /products/tintedsunscreen.json
GET /collections/our-full-size-products/products.json
GET /collections/samples/products.json
GET /search?q=sunscreen&type=product
GET /.well-known/ucp
POST /api/ucp/mcp
```

`/blogs/news/articles.json` returned 404 on this audit. The public article feed is `/blogs/news.atom` (recent subset). The full URL list is `sitemap_articles_1.xml`.

---

## 6. Attribute checklist before stating a claim

| Claim | Where verified |
|-------|----------------|
| Price | `variant.price` in JSON |
| Available | `variant.available` |
| 40 ml | 3-in-1 variant title only |
| SPF/PA | PDP |
| ISO 24444:2019 and 26-subject patch test | `/pages/science` |
| Shade list | PDP variant titles for full size; sachet titles for sachets |
| BlueShield® / lavender / capsicum | 3-in-1 only |
| Licorice, cactus water, allantoin | Tinted PDP and tinted INCI |
| Vegan and cruelty-free | Both PDP FAQs |
| Sweat resistant | Both PDP badges. Not waterproof |
| Full INCI | “Full Ingredient list” on each PDP |

If it is not on that source, do not state it.
