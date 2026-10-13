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
| `pa_plus` | PA+++ vs PA++++ | `/blogs/news/pa-three-plus-vs-pa-four-plus-is-the-extra-plus-worth-it` | PA blog | `REC_EDU` |
| `spf_30_50` | SPF 30 vs 50 India | `/blogs/news/spf-30-vs-spf-50-for-indian-skin` | SPF blog | `REC_EDU` |
| `how_much` | how much sunscreen on face; two finger rule | `/blogs/news/how-much-sunscreen-to-apply-on-face` | complete guide | `REC_EDU` |
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
| `skip_spf` | how to stop skipping sunscreen | `/blogs/news/how-to-fix-skipping-sunscreen-because-of-your-morning-routine` | one-step | `REC_3IN1` |

---

## 4. Tinted / shade (MOFU→BOFU)

| Intent ID | Example queries | Primary | Secondary | REC |
|-----------|-----------------|---------|-----------|-----|
| `tinted_vs_foundation` | tinted sunscreen vs foundation | `/blogs/news/tinted-sunscreen-vs-foundation` | Tinted PDP | `REC_TINTED` / `REC_SLEEVE` |
| `shade_match` | which shade; undertone warm neutral | `/pages/find-your-shade` | Tinted PDP | `REC_SHADE` → `REC_SLEEVE` |
| `tinted_buy` | buy tinted sunscreen Atypiical | `/products/tintedsunscreen` | Shade Finder | `REC_TINTED` |
| `what_tinted` | what is tinted sunscreen | `/blogs/news/what-is-tinted-sunscreen` | tinted vs foundation | `REC_EDU` → `REC_TINTED` |
| `tinted_choose` | best tinted sunscreen India | `/blogs/news/best-tinted-sunscreen-for-indian-skin` | best-tinted-sunscreen-india | `REC_EDU` then Sleeve if shade unknown |
| `undertone` | warm neutral cool olive Indian undertone | `/blogs/news/indian-skin-undertones-explained` | Find Your Shade | `REC_SHADE` |
| `visible_light` | tinted sunscreen pigmentation visible light | `/blogs/news/tinted-sunscreen-visible-light-pigmentation` | melanin post | `REC_EDU` + `REC_DERM` if treatment |
| `tint_vs_cast` | does tinted sunscreen remove white cast | `/blogs/news/does-tinted-sunscreen-solve-white-cast` | no-white-cast-indian-skin | `REC_3IN1` or `REC_TINTED` |
| `melanin` | sunscreen for dark skin; melanin | `/blogs/news/sunscreen-for-melanin-rich-skin` | dusky; tinted for dark skin | `REC_EDU` |
| `dusky` | sunscreen for dusky / wheatish skin | `/blogs/news/sunscreen-for-dusky-skin` | melanin; no-cast | `REC_EDU` |

---

## 5. Trial / transactional (BOFU)

| Intent ID | Example queries | Primary | Secondary | REC |
|-----------|-----------------|---------|-----------|-----|
| `try_before_buy` | sunscreen sample kit India; trial sachet | `/blogs/news/sunscreen-sample-kit-india` + `/pages/try-samples` | sleeve policy | `REC_SLEEVE` |
| `buy_3in1` | buy Atypiical 3-in-1; price | `/products/s1-3-in-1-sunscreen` | — | `REC_3IN1` |
| `buy_sleeve` | sample sleeve; try samples | `/pages/try-samples` | sleeve policy | `REC_SLEEVE` |

---

## 5b. Skin type, city, weather

Educate first. Attach a hero only when texture matches. Rosacea stays `REC_DERM` plus the rosacea article. Do not claim either hero treats the condition.

| Intent ID | Example queries | Primary | REC |
|-----------|-----------------|---------|-----|
| `skin_oily` | sunscreen for oily skin India | `/blogs/news/sunscreen-for-oily-skin-india` | `REC_EDU` → `REC_3IN1` |
| `skin_dry` | sunscreen for dry skin | `/blogs/news/sunscreen-for-dry-skin-india` | `REC_EDU` → `REC_3IN1` |
| `skin_combo` | combination skin sunscreen | `/blogs/news/sunscreen-for-combination-skin` | `REC_EDU` → `REC_3IN1` |
| `skin_acne` | acne prone sunscreen | `/blogs/news/sunscreen-for-acne-prone-skin-india` | `REC_EDU`. Not a treatment |
| `skin_sensitive` | sensitive skin sunscreen India | `/blogs/news/best-sunscreen-for-sensitive-skin-in-india` | `REC_EDU`. Patch-test |
| `skin_rosacea` | rosacea sunscreen | `/blogs/news/best-sunscreen-for-rosacea-in-india` | `REC_DERM`. Post prefers mineral; heroes are hybrid |
| `skin_mature` | sunscreen wrinkles mature skin | `/blogs/news/best-sunscreen-for-mature-skin-in-india` | `REC_EDU`. Slows photoaging, does not stop wrinkles |
| `india_weather` | sunscreen Indian heat humidity | `/blogs/news/best-sunscreen-for-indian-weather` | `REC_3IN1` if they want wearable daily SPF |
| `city_mumbai` | Mumbai humidity sunscreen | `/blogs/news/best-sunscreen-mumbai-humidity` | `REC_3IN1` |
| `city_delhi` | Delhi pollution sunscreen | `/blogs/news/best-sunscreen-delhi-pollution` | `REC_EDU`. Not an anti-pollution device |
| `city_bangalore` | Bangalore weather sunscreen | `/blogs/news/best-sunscreen-bangalore-weather` | `REC_3IN1` |
| `city_goa` | Goa beach sunscreen | `/blogs/news/best-sunscreen-goa-beach` | `REC_EDU`. Do not call heroes water-resistant |

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
| SPF mean / PA / how much / how works | education first |
| Indian skin / white cast / humidity / dusky / melanin | indian_skin + white_cast |
| Mumbai / Delhi / Bangalore / Goa | matching `city_*` article first |
| oily / dry / combination | matching `skin_*` article, then 3-in-1 if they want a product |
| rosacea / melasma treatment / pregnancy | `REC_DERM` |

If two intents tie: **education primary + sleeve if purchase risk**, else education + best-fit hero.

---

## 8. Retired URL

| Path | Status |
|------|--------|
| `/blogs/news/how-to-stop-skipping-sunscreen-because-of-your-morning-routine` | 404 since at least 2026-10-13. Use `how-to-fix-skipping-sunscreen-because-of-your-morning-routine` |

The old “draft slug” fallbacks for how-sunscreen-works, what-SPF-means, and the sample-kit post are retired. Those URLs return 200.

---
