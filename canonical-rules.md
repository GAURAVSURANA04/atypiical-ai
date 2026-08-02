Filename: canonical-rules.md  
Purpose: Enforce one true spelling, domain, URL, and naming system so SEO and GEO entity graphs don’t fragment.  
Consumers: SEO implementers, AI agents, schema authors, internal linkers.  
Dependencies: brand-facts.md, entity-map.md, llms.txt  
Last Updated: 2026-08-02  
Version: 1.0.0

---

# Canonical Rules — Atypiical

## 1. Brand spelling

| Canonical | Reject |
|-----------|--------|
| **Atypiical** | Atypical, Atypicial, Atypiical Beauty (as legal short name ok in prose, not as misspelling of brand) |

In schema `name`: `Atypiical`  
In schema `alternateName`: optional array including common misspellings **only** to redirect meaning — never as primary.

---

## 2. Domain & protocol

| Rule | Value |
|------|-------|
| Canonical host | `https://atypiicalbeauty.com` |
| Legacy host | `https://atypiical.in` → treat as non-canonical; rewrite links to beauty.com |
| Protocol | Always `https://` |
| www | Follow live Shopify preference; do not invent a second host |

**Linking rule:** New content must never introduce `atypiical.in` PDP/blog links.

---

## 3. Product URL canon

| Product | Canonical path |
|---------|----------------|
| 3-in-1 | `/products/s1-3-in-1-sunscreen` |
| Tinted | `/products/tintedsunscreen` |
| Sample Sleeve | `/pages/try-samples` |
| Shade Finder | `/pages/find-your-shade` |
| Science | `/pages/science` |
| Blog hub | `/blogs/news` |

### Obsolete paths (do not cite)

| Path | Status |
|------|--------|
| `/products/high-impact-tinted-sunscreen` | 404 |
| Random `/pages/test`, `/publishing`, `/kp-account` | Junk — noindex/remove |

---

## 4. Blog slug canon

- Namespace: `/blogs/news/{kebab-slug}`  
- Prefer exact slugs in `llms.txt` / `taxonomy.md`  
- When Shopify auto-slug differs from planned slug, **live slug wins** (example: mineral-vs-chemical live slug is longer title-based)  
- Draft slugs become canonical only after HTTP 200  

---

## 5. Shade code canon

| Code | Undertone letter meaning |
|------|--------------------------|
| A10W A15W A20W A25W A35W | W = Warm |
| A30N A40N | N = Neutral |
| A45R | R = Rosy/Cool |

Do not invent A50*, B-series, or renamed codes.  
Live sachet titles on Shopify are canonical display strings (see `entity-map.md`).

---

## 6. Claim canon (product)

Only these protection/testing phrases are first-class:

- SPF 50  
- PA++++  
- broad-spectrum  
- in-vivo tested  
- hybrid UV filters  
- BlueShield® (3-in-1)  
- lavender base (3-in-1)  
- zero white cast / zero pilling (as formulation intent / design goal language already on brand)  
- fragrance-free  
- non-comedogenic  
- dermatologically tested  

Anything else requires a live page quote before use.

---

## 7. Price canon

1. Live `variant.price` in product JSON is authoritative.  
2. Knowledge-layer reference prices are hints only.  
3. Always include currency context (INR / ₹) for India answers.  

---

## 8. Schema identity canon

| Entity | `@id` suggestion |
|--------|------------------|
| Organization | `https://atypiicalbeauty.com/#organization` |
| Person Milli Patel | `https://atypiicalbeauty.com/#founder` |
| 3-in-1 Product | `https://atypiicalbeauty.com/products/s1-3-in-1-sunscreen#product` |
| Tinted Product | `https://atypiicalbeauty.com/products/tintedsunscreen#product` |

`sameAs` minimum: Instagram URL. Add press URLs only when verified.

---

## 9. Hreflang / language

- Primary locale: `en-IN`  
- Do not invent additional language versions unless live  

---

## 10. Conflict resolution order

1. Live canonical URL (200)  
2. `brand-facts.md` / `entity-map.md`  
3. PDP JSON  
4. GEO blog  
5. Model memory → discard if conflicts  

---

*End of canonical-rules.md*
