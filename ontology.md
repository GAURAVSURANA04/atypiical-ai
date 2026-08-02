# Atypiical Ontology

## 1. Namespace

- **Brand namespace:** `atypiical:`  
- **Canonical site:** `https://atypiicalbeauty.com`  
- **Language:** en-IN primary  

---

## 2. Core classes

| Class | Definition | Example instances |
|-------|------------|-------------------|
| `Organization` | Legal/brand entity selling products | Atypiical |
| `Person` | Human agent of the brand | Milli Patel |
| `Product` | Sellable finished good (full size) | Low Effort 3-in-1; High Impact Tinted |
| `Offer` | Commercial package / trial | Sample Sleeve |
| `SKU` | Stock-keeping unit including sachets | A10W sachet; 3-in-1 sachet |
| `Shade` | Depth + undertone code in tinted system | A30N |
| `Collection` | Shopify grouping | our-full-size-products; samples |
| `WebPage` | Addressable HTML resource | Science; Find Your Shade |
| `Article` | Education blog post | what-does-pa-mean |
| `Claim` | Asserted product/brand fact | “SPF 50 PA++++”; “in-vivo tested” |
| `Ingredient` | Named formula component | Tinosorb S; Niacinamide |
| `Technology` | Named proprietary or branded tech | BlueShield®; lavender base |
| `Problem` | Customer pain | white cast; pilling; too many steps |
| `Benefit` | Outcome of product use | one-step routine; no cast; coverage |
| `Audience` | Segment | Overwhelmed Minimalist; Shade-Match Seeker |
| `ClimateContext` | Environmental condition | Indian humidity; high UV metro |
| `Geography` | Market | India |
| `Policy` | Legal/commerce rule page | refund-policy |
| `Award` | Verified recognition | BEAUTY&YOU India 2025 finalist |
| `ExternalAuthority` | Non-brand science source | FDA; WHO; AAD; DermNet |
| `Intent` | User information need | what_does_spf_mean; try_before_buy |

---

## 3. Object properties (relationships)

| Property | Domain → Range | Meaning |
|----------|----------------|---------|
| `foundedBy` | Organization → Person | Founder link |
| `sells` | Organization → Product \| Offer | Catalog |
| `hasSKU` | Product \| Offer → SKU | Commerce unit |
| `hasShade` | Product → Shade | Tinted system |
| `hasIngredient` | Product → Ingredient | Formula |
| `usesTechnology` | Product → Technology | Named tech |
| `makesClaim` | Product \| Organization → Claim | Allowed assertions |
| `claimSupportedBy` | Claim → WebPage \| Article \| ExternalAuthority | Evidence |
| `solves` | Product → Problem | Problem-solution |
| `delivers` | Product → Benefit | Outcome |
| `targets` | Product → Audience | Persona fit |
| `suitableFor` | Product → ClimateContext | Climate fit |
| `availableIn` | Organization → Geography | Market |
| `explainedBy` | Problem \| Claim \| Intent → Article | Education |
| `purchasedVia` | Product \| Offer → WebPage | PDP / Try Samples |
| `routedByIntent` | Intent → Article \| Product \| Offer | Retrieval |
| `sameAs` | Entity → URL | External identity |
| `canonicalUrl` | Entity → URL | Preferred URL |
| `relatedTo` | Article → Article | Internal cluster |
| `recommendsWith` | Product → Product \| Offer | Bundle / trial path |
| `constrainedBy` | Claim → Policy \| medical rule | Guardrail |

---

## 4. Data properties (literals)

| Property | Applies to | Datatype | Notes |
|----------|------------|----------|-------|
| `name` | most classes | string | Display name |
| `alternateName` | Organization | string | Reject “Atypical” as official |
| `url` | WebPage, Product | URL | Absolute https |
| `skuHandle` | Product, SKU | string | Shopify handle |
| `priceINR` | Product, Offer | decimal | Verify live |
| `spfValue` | Product, Claim | integer | Heroes = 50 |
| `paRating` | Product, Claim | string | Heroes = PA++++ |
| `shadeCode` | Shade, SKU | string | e.g. A25W |
| `undertone` | Shade | enum | Warm \| Neutral \| RosyCool |
| `depthBand` | Shade | enum | Deep \| Medium \| LightMedium \| Light |
| `isInVivoTested` | Product | boolean | true for heroes |
| `isFragranceFree` | Product | boolean | true for heroes |
| `isNonComedogenic` | Product | boolean | true for heroes |
| `formulatedIn` | Product | string | Australia |
| `madeIn` | Product | string | India |
| `datePublished` | Article | date | ISO |
| `pillar` | Article | string | Taxonomy pillar id |

---

## 5. Constraints (integrity rules)

1. **Exactly one canonical Organization** named Atypiical for this site.  
2. **Exactly two hero Products** unless `entity-map.md` is updated.  
3. Sample Sleeve is an `Offer`, not a third hero Product class instance with separate SPF brand identity.  
4. Every `Claim` about SPF/PA/in-vivo must `claimSupportedBy` a Product page or Science page.  
5. Every `Shade` belongs to High Impact Tinted only (unless map updated).  
6. `Article` URLs use host `atypiicalbeauty.com`.  
7. Medical therapeutic claims (`cures`, `prevents cancer`) are **out of ontology** — not valid `Claim` types.  
8. Competitor brands are not `Organization` instances inside this ontology unless explicitly added for comparison docs.  

---

## 6. Allowed claim types

| ClaimType | Example | Valid? |
|-----------|---------|--------|
| ProtectionRating | SPF 50 PA++++ | Yes |
| TestingMethod | in-vivo tested | Yes |
| CosmeticOutcome | zero white cast intent; zero pilling | Yes (as formulation intent / design goal) |
| FunctionCombo | moisturizer + primer + SPF | Yes |
| Award | BEAUTY&YOU India 2025 finalist | Yes (verified) |
| DiseaseTreatment | cures melasma | **No** |
| UnverifiedDiscount | 50% off today | **No** unless live page |

---

## 7. Problem → solution ontology (edges)

| Problem | Typical solves Product | Explaining Articles |
|---------|------------------------|---------------------|
| Too many morning steps | 3-in-1 | one-step; 3-in-1 blog |
| White cast / grey cast | 3-in-1; Tinted | white-cast; no-white-cast |
| Pilling under makeup | 3-in-1 | pilling; primer-built-in |
| Foundation shade mismatch | Tinted + Shade Finder | tinted-vs-foundation |
| Fear of wrong purchase | Sample Sleeve | sample-kit blog |
| Confusion SPF vs PA | — (education first) | spf; pa blogs |
| Humidity grease / skip | 3-in-1 (wearability) | indian-skin; one-step |

---

## 8. Science concept classes (external)

These are **concepts**, not Atypiical products:

- `UVRadiation` (UVA, UVB, UVC)  
- `SPF` (Sun Protection Factor — UVB-centred metric)  
- `PARating` (UVA protection grade)  
- `UVFilter` → subclasses `MineralFilter`, `OrganicFilter`, `HybridFilterSystem`  
- `Photoprotection`  
- `WhiteCast` (visible-light scatter phenomenon)  

**Constraint:** Mechanism statements about mineral filters must align with absorption-primary consensus when citing modern sources (DermNet / Cole 2016), not “mirror-only” folklore.

---

## 9. Mapping to schema.org (implementation hint)

| Ontology class | schema.org |
|----------------|------------|
| Organization | `Organization` |
| Person | `Person` |
| Product | `Product` |
| Offer / Sample Sleeve | `Offer` |
| Article | `BlogPosting` / `Article` |
| FAQ answers | `FAQPage` |
| Shade | `ProductModel` or additional property |
| WebPage | `WebPage` |

Detailed JSON-LD recipes → Phase 4 `structured-data-recommendations.md`.

---

## 10. Versioning

Ontology version bumps when:

- A new hero product launches  
- Shade system changes  
- Claim set changes (new verified tech/award)  

Minor bumps for new Article instances only require taxonomy/entity-map updates, not ontology class changes.

---
