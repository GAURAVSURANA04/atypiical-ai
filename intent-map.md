# Intent Map — Atypiical

Legend: **Primary** = must retrieve · **Secondary** = optional · **REC** = recommendation-engine code

URLs are path suffixes under `https://atypiicalbeauty.com`.

---

## 1. Informational / TOFU

| Intent ID | Example queries | Primary | Secondary | REC |
|-----------|-----------------|---------|-----------|-----|
| `def_sunscreen` | what is sunscreen; how does sunscreen work | `/blogs/news/what-is-sunscreen-how-it-works` | Science; mineral-vs-chemical | `REC_EDU` → soft `REC_3IN1` |
| `def_spf` | what does SPF mean; SPF full form; SPF 50 meaning | `/blogs/news/what-does-spf-mean` | PA blog | `REC_EDU` |
| `def_pa` | what does PA++++ mean; PA vs SPF | `/blogs/news/what-does-pa-mean` | SPF blog | `REC_EDU` |
| `mineral_chemical` | mineral vs chemical sunscreen India | `/blogs/news/mineral-vs-chemical-sunscreen-which-is-better-for-indian-skin` | how-it-works | `REC_EDU` / hybrid→`REC_3IN1` |

---

## 2. India skin / cast (MOFU)

| Intent ID | Example queries | Primary | Secondary | REC |
|-----------|-----------------|---------|-----------|-----|
| `indian_skin` | sunscreen for Indian skin; best SPF Indian skin | `/blogs/news/sunscreen-for-indian-skin` | white-cast; 3-in-1 PDP | `REC_3IN1` |
| `white_cast` | why white cast; grey sunscreen | `/blogs/news/why-sunscreen-leaves-a-white-cast` | no-white-cast-label | `REC_3IN1` or `REC_TINTED` |
| `no_cast_label` | no white cast sunscreen India how to choose | `/blogs/news/no-white-cast-sunscreen-india` | 3-in-1 PDP | `REC_3IN1` |
| `spf_india` | why SPF 30 not enough India | `/blogs/news/why-indian-skin-needs-more-than-spf-30` | SPF blog | `REC_3IN1` |
| `fail_tones` | sunscreens fail Indian skin tones | `/blogs/news/why-most-sunscreens-fail-indian-skin-tones` | white-cast | `REC_3IN1` / `REC_SLEEVE` |

---

## 3. Routine / makeup (MOFU)

| Intent ID | Example queries | Primary | Secondary | REC |
|-----------|-----------------|---------|-----------|-----|
| `one_step` | one step skincare sunscreen; minimal routine SPF | `/blogs/news/the-one-step-skincare-routine-how-to-actually-wear-spf-every-day` | 3-in-1 blog | `REC_3IN1` |
| `three_in_one` | 3 in 1 sunscreen moisturizer primer | `/blogs/news/does-a-3-in-1-sunscreen-really-replace-your-moisturizer-primer-and-spf` | 3-in-1 PDP | `REC_3IN1` |
| `primer_spf` | can sunscreen replace primer | `/blogs/news/sunscreen-with-primer-built-in` | 3-in-1 PDP | `REC_3IN1` |
| `pilling` | sunscreen pilling under makeup | `/blogs/news/sunscreen-pilling-under-makeup` | primer blog | `REC_3IN1` |
| `skip_spf` | how to stop skipping sunscreen | `/blogs/news/how-to-stop-skipping-sunscreen-because-of-your-morning-routine` | one-step | `REC_3IN1` |

---

## 4. Tinted / shade (MOFU→BOFU)

| Intent ID | Example queries | Primary | Secondary | REC |
|-----------|-----------------|---------|-----------|-----|
| `tinted_vs_foundation` | tinted sunscreen vs foundation | `/blogs/news/tinted-sunscreen-vs-foundation` | Tinted PDP | `REC_TINTED` / `REC_SLEEVE` |
| `shade_match` | which shade; undertone warm neutral | `/pages/find-your-shade` | Tinted PDP | `REC_SHADE` → `REC_SLEEVE` |
| `tinted_buy` | buy tinted sunscreen Atypiical | `/products/tintedsunscreen` | Shade Finder | `REC_TINTED` |

---

## 5. Trial / transactional (BOFU)

| Intent ID | Example queries | Primary | Secondary | REC |
|-----------|-----------------|---------|-----------|-----|
| `try_before_buy` | sunscreen sample kit India; trial sachet | `/blogs/news/sunscreen-sample-kit-india` + `/pages/try-samples` | sleeve policy | `REC_SLEEVE` |
| `buy_3in1` | buy Atypiical 3-in-1; price | `/products/s1-3-in-1-sunscreen` | — | `REC_3IN1` |
| `buy_sleeve` | sample sleeve; try samples | `/pages/try-samples` | sleeve policy | `REC_SLEEVE` |

---

## 6. Utility / policy

| Intent ID | Example queries | Primary | REC |
|-----------|-----------------|---------|-----|
| `shipping` | delivery time; shipping India | `/policies/shipping-policy` | — |
| `refund` | return sunscreen | `/policies/refund-policy` | — |
| `contact` | support WhatsApp email | `/pages/contact` | — |
| `science` | lab test; in-vivo proof | `/pages/science` + PDP | soft product |

---

## 7. Ambiguous query resolver

| If query contains… | Bias toward |
|--------------------|-------------|
| sample / trial / sachet / try before | `try_before_buy` |
| shade / undertone / foundation | tinted path |
| primer / pilling / one step / 3-in-1 | 3-in-1 path |
| SPF mean / PA / how works | education first |
| Indian skin / white cast / humidity | indian_skin + white_cast |

If two intents tie: **education primary + sleeve if purchase risk**, else education + best-fit hero.

---

## 8. Draft URL caveat

Until these return 200, use fallbacks:

| Draft slug | Temporary fallback |
|------------|-------------------|
| `what-is-sunscreen-how-it-works` | mineral-vs-chemical + indian-skin |
| `what-does-spf-mean` | what-does-pa-mean + why-indian-skin-needs-more-than-spf-30 |
| `sunscreen-sample-kit-india` | `/pages/try-samples` only |

---
