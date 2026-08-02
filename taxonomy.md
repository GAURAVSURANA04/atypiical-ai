Filename: taxonomy.md  
Purpose: Content and commerce classification system — pillars, intents, page types, and how blogs/products nest for SEO topical authority and AI retrieval.  
Consumers: Content strategists, SEO/AEO engineers, RAG chunk routers, internal linking systems.  
Dependencies: architecture.md, ontology.md, atypiical-blog-plan.md, live blog inventory  
Last Updated: 2026-08-02  
Version: 1.0.0

---

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

| Topic | Live / Draft slug | Affinity |
|-------|-------------------|----------|
| How sunscreen works | `what-is-sunscreen-how-it-works` (draft) | None→Both |
| What SPF means | `what-does-spf-mean` (draft) | 3-in-1 |
| What PA means | `what-does-pa-mean` (live) | 3-in-1 |

### P1 — Sunscreen for Indian Skin

| Topic | Slug | Affinity |
|-------|------|----------|
| Indian skin guide | `sunscreen-for-indian-skin` | 3-in-1 |
| Needs more than SPF 30 | `why-indian-skin-needs-more-than-spf-30` | 3-in-1 |
| Fail Indian skin tones | `why-most-sunscreens-fail-indian-skin-tones` | Both |

### P2 — Tinted Sunscreen

| Topic | Slug | Affinity |
|-------|------|----------|
| Tinted vs foundation | `tinted-sunscreen-vs-foundation` | Tinted |

### P3 — Low Effort / 3-in-1 Routine

| Topic | Slug | Affinity |
|-------|------|----------|
| 3-in-1 replace 3 steps | `does-a-3-in-1-sunscreen-really-replace-your-moisturizer-primer-and-spf` | 3-in-1 |
| One-step routine | `the-one-step-skincare-routine-how-to-actually-wear-spf-every-day` | 3-in-1 |
| Primer built in | `sunscreen-with-primer-built-in` | 3-in-1 |
| Pilling under makeup | `sunscreen-pilling-under-makeup` | 3-in-1 |
| Stop skipping SPF | `how-to-stop-skipping-sunscreen-because-of-your-morning-routine` | 3-in-1 |
| Sample kit | `sunscreen-sample-kit-india` (draft) | Sleeve/Both |

### P4 — White Cast Science

| Topic | Slug | Affinity |
|-------|------|----------|
| Why white cast | `why-sunscreen-leaves-a-white-cast` | 3-in-1 |
| No white cast label guide | `no-white-cast-sunscreen-india` | 3-in-1 |
| Mineral vs chemical | `mineral-vs-chemical-sunscreen-which-is-better-for-indian-skin` | 3-in-1 |

### P5 — SPF / PA Education

Covered under P0 + PA post; expand later with how-much-to-apply, SPF 30 vs 50 India, etc.

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

| Code | Undertone | Depth band (from live titles) |
|------|-----------|-------------------------------|
| A10W | Warm | Deep |
| A15W | Warm | Deep |
| A20W | Warm | Medium |
| A25W | Warm | Medium |
| A30N | Neutral | Light-Medium |
| A35W | Warm | Light-Medium |
| A40N | Neutral | Light |
| A45R | Rosy/Cool | Light |

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

## 9. Priority publish order (taxonomy gaps)

| Gap | Why it matters for GEO |
|-----|------------------------|
| Publish P0 drafts (how it works, SPF meaning) | Own definitional AI answers |
| Publish sample-kit blog | Own try-before-buy SERP vs marketplaces |
| Future: SPF 30 vs 50 India; how much to apply; oily/dry skin | Fill P1/P5 long-tails |
| Future: undertones blog (draft exists offline) | Support Shade Finder |

---

*End of taxonomy.md*
