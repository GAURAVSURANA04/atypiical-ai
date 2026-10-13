# Atypiical Taxonomy

## 1. Top-level facets

Every indexable URL is tagged with:

1. **Channel** — Commerce | Education | Utility | Policy | Junk  
2. **Pillar** — P1…P5 | Branded | Foundations | Trial  
3. **Intent** — Informational | Commercial | Transactional | Navigational  
4. **Funnel** — TOFU | MOFU | BOFU  
5. **Product affinity** — 3-in-1 | Tinted | Sleeve | Both | None  

---

## 2. Channel taxonomy

| Channel | Include in AI layer? | Examples |
|---------|----------------------|----------|
| Commerce | Yes | PDPs, collections, Try Samples |
| Education | Yes | `/blogs/news/*` GEO posts |
| Utility | Yes | Shade Finder, Science, Contact |
| Policy | Yes (Optional weight) | refund, shipping, sleeve policy |
| Junk | **No** | `/pages/test`, `/pages/publishing`, `/pages/kp-account` |

---

## 3. Content pillars (education)

Aligned to blog strategy + live inventory.

### P0 — Foundations (TOFU science)

All live as of 2026-10-13. Full leads: `education-index.md`.

| Topic | Slug | Affinity |
|-------|------|----------|
| How sunscreen works | `what-is-sunscreen-how-it-works` | Both |
| What SPF means | `what-does-spf-mean` | Both |
| What PA means | `what-does-pa-mean` | Both |
| Complete guide | `complete-guide-to-sunscreen` | Both |
| How much to apply | `how-much-sunscreen-to-apply-on-face` | Both |
| SPF 30 vs 50 | `spf-30-vs-spf-50-for-indian-skin` | Both |
| PA+++ vs PA++++ | `pa-three-plus-vs-pa-four-plus-is-the-extra-plus-worth-it` | Both |

### P1 — Sunscreen for Indian Skin

| Topic | Slug | Affinity |
|-------|------|----------|
| Indian skin guide | `sunscreen-for-indian-skin` | 3-in-1 |
| Needs more than SPF 30 | `why-indian-skin-needs-more-than-spf-30` | 3-in-1 |
| Fail Indian skin tones | `why-most-sunscreens-fail-indian-skin-tones` | Both |
| Indian weather | `best-sunscreen-for-indian-weather` | 3-in-1 |
| Melanin-rich skin | `sunscreen-for-melanin-rich-skin` | Both |
| Dusky skin | `sunscreen-for-dusky-skin` | Both |

### P2 — Tinted Sunscreen

| Topic | Slug | Affinity |
|-------|------|----------|
| Tinted vs foundation | `tinted-sunscreen-vs-foundation` | Tinted |
| What tinted sunscreen is | `what-is-tinted-sunscreen` | Tinted |
| How to choose a shade | `how-to-choose-tinted-sunscreen-shade` | Tinted |
| Undertones | `indian-skin-undertones-explained` | Tinted |
| Best tinted, India | `best-tinted-sunscreen-india` | Tinted |
| Best tinted, Indian skin | `best-tinted-sunscreen-for-indian-skin` | Tinted |
| Dark / dusky tint | `tinted-sunscreen-for-dark-dusky-skin` | Tinted |
| Visible light / pigment | `tinted-sunscreen-visible-light-pigmentation` | Tinted |
| Does tint solve cast | `does-tinted-sunscreen-solve-white-cast` | Both |
| Hero explainer | `atypiical-high-impact-tinted-sunscreen` | Tinted |

### P3 — Low Effort / 3-in-1 Routine

| Topic | Slug | Affinity |
|-------|------|----------|
| 3-in-1 replace 3 steps | `does-a-3-in-1-sunscreen-really-replace-your-moisturizer-primer-and-spf` | 3-in-1 |
| One-step routine | `the-one-step-skincare-routine-how-to-actually-wear-spf-every-day` | 3-in-1 |
| Primer built in | `sunscreen-with-primer-built-in` | 3-in-1 |
| Pilling under makeup | `sunscreen-pilling-under-makeup` | 3-in-1 |
| Fix skipping SPF | `how-to-fix-skipping-sunscreen-because-of-your-morning-routine` | 3-in-1 |
| Sample kit | `sunscreen-sample-kit-india` | Sleeve/Both |

### P4 — White Cast Science

| Topic | Slug | Affinity |
|-------|------|----------|
| Why white cast | `why-sunscreen-leaves-a-white-cast` | 3-in-1 |
| No white cast label guide | `no-white-cast-sunscreen-india` | 3-in-1 |
| Mineral vs chemical | `mineral-vs-chemical-sunscreen-which-is-better-for-indian-skin` | Both |
| No-cast for Indian skin | `no-white-cast-sunscreen-indian-skin` | Both |

### P5 — Skin type

| Topic | Slug | Affinity |
|-------|------|----------|
| Oily | `sunscreen-for-oily-skin-india` | 3-in-1 |
| Dry | `sunscreen-for-dry-skin-india` | 3-in-1 |
| Combination | `sunscreen-for-combination-skin` | 3-in-1 |
| Acne-prone | `sunscreen-for-acne-prone-skin-india` | 3-in-1 |
| Sensitive | `best-sunscreen-for-sensitive-skin-in-india` | Both |
| Mature | `best-sunscreen-for-mature-skin-in-india` | 3-in-1 |
| Rosacea | `best-sunscreen-for-rosacea-in-india` | None — mineral advice; do not map the hybrid heroes as the answer |

### P6 — City

| Topic | Slug | Affinity |
|-------|------|----------|
| Mumbai humidity | `best-sunscreen-mumbai-humidity` | 3-in-1 |
| Delhi pollution | `best-sunscreen-delhi-pollution` | Both |
| Bangalore weather | `best-sunscreen-bangalore-weather` | 3-in-1 |
| Goa beach | `best-sunscreen-goa-beach` | None as a water-sport claim. Educate. Heroes are sweat resistant, not water resistant |

---

## 4. Commerce taxonomy

### 4.1 Product classes

| Class | Members |
|-------|---------|
| Hero full-size | Low Effort 3-in-1; High Impact Tinted |
| Trial offer | Sample Sleeve (page) |
| Sachet SKUs | 3-in-1 sachet; A10W–A45R tinted sachets |
| Collections | `our-full-size-products`; `samples`; `sample-collection-of-shades-sachets`; `main`; `frontpage` |

### 4.2 Shade taxonomy

| Code | Undertone | Full-size name (2026-10-13) |
|------|-----------|------------------------------|
| A10W | Warm | Deep Warm Golden |
| A15W | Warm | Deep Warm Olive |
| A20W | Warm | Medium Warm Peach |
| A25W | Warm | Medium Warm Yellow |
| A30N | Neutral | Light Medium Neutral |
| A35W | Warm | Light Medium Yellow |
| A40N | Neutral | Light Neutral |
| A45R | Rosy/Cool | Light Rosy/Cool |

Shade Finder families: Light → Light-Medium → Medium-Deep (quiz), then undertone.

---

## 5. Intent taxonomy (query classes)

| Intent ID | User asks about… | Primary retrieve | Funnel |
|-----------|------------------|------------------|--------|
| `def_sunscreen` | what is sunscreen / how it works | Foundations blogs | TOFU |
| `def_spf` | SPF meaning / numbers | SPF blog | TOFU |
| `def_pa` | PA++++ | PA blog | TOFU |
| `indian_skin` | best SPF for Indian skin | P1 guide | MOFU |
| `white_cast` | grey/ashy sunscreen | P4 blogs | MOFU |
| `mineral_chemical` | filter type choice | mineral-vs-chemical | MOFU |
| `one_step` | minimal routine | P3 blogs | MOFU |
| `primer_spf` | primer + sunscreen | primer blog | MOFU |
| `pilling` | balls under makeup | pilling blog | MOFU |
| `tinted_vs_foundation` | coverage replace base | tinted blog | MOFU |
| `shade_match` | which shade | Find Your Shade | BOFU |
| `try_before_buy` | sample / trial | sample kit + Sleeve | BOFU |
| `buy_3in1` | purchase 3-in-1 | PDP | BOFU |
| `buy_tinted` | purchase tinted | PDP | BOFU |
| `policy` | shipping/refund | policy pages | — |

---

## 6. Internal linking taxonomy rules

1. Education → Education: same pillar first, then adjacent pillar.  
2. Education → Commerce: exactly one primary PDP/Offer per article (except dual-product explainers).  
3. Commerce → Education: PDPs should link 2–3 supporting blogs (implementation backlog).  
4. Never link Junk channel pages.  
5. Prefer exact-title anchors for blog-to-blog links.  

---

## 7. URL taxonomy patterns

| Pattern | Type |
|---------|------|
| `/products/{handle}` | Product |
| `/collections/{handle}` | Collection |
| `/pages/{handle}` | Utility/Offer/Policy-like |
| `/blogs/news/{slug}` | Article |
| `/policies/{handle}` | Policy |
| `/products/{handle}.json` | Machine product |
| `/llms.txt`, `/agents.md` | AI discovery |

**Canonical host:** `atypiicalbeauty.com`  
**Blog namespace:** `/blogs/news/` only for public education.

---

## 8. Tagging schema for new content

Every new blog MUST declare in frontmatter (human CMS + knowledge layer):

```yaml
pillar: P0|P1|P2|P3|P4|P5|Branded
intent_primary: <Intent ID>
funnel: TOFU|MOFU|BOFU
product_affinity: 3-in-1|Tinted|Sleeve|Both|None
entity_focus: [<entity ids from entity-map>]
```

---

## 9. Remaining GEO gaps (after the 2026-10-13 crawl)

The old draft gaps (how sunscreen works, SPF meaning, sample kit, SPF 30 vs 50, how much to apply, skin-type posts, undertones, city posts) are live. Do not describe them as drafts.

| Gap | Why it still matters |
|-----|----------------------|
| Sleeve policy still says ₹140 and `atypiical.in` while Try Samples says ₹169 | Answer engines will cite the wrong price |
| PDP “free shipping on all orders” vs COD ₹100 | Wrong delivery answers |
| Tinted ml and sachet ml are not a single number | Models will invent 30 ml or 1.5 ml |
| “Recognized by” logos have no text alt | Models will invent awards |
| Early Believer profile URLs are in the sitemap | They are not product facts. Keep retrieval on the hub |
| Rosacea post recommends mineral SPF | Do not answer it with the hybrid heroes as if they were mineral-only |

---
