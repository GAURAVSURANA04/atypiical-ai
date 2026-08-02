# Recommendation Engine — Atypiical

## 1. Outputs the engine may return

| Code | Meaning | URL |
|------|---------|-----|
| `REC_3IN1` | Low Effort 3-in-1 full size | `/products/s1-3-in-1-sunscreen` |
| `REC_TINTED` | High Impact Tinted full size | `/products/tintedsunscreen` |
| `REC_SLEEVE` | Sample Sleeve | `/pages/try-samples` |
| `REC_SHADE` | Find Your Shade quiz | `/pages/find-your-shade` |
| `REC_EDU` | Education only (no product push) | Matching blog |
| `REC_DERM` | See a dermatologist | No product as treatment |
| `REC_STACK` | 3-in-1 base ± Tinted on top | Both PDPs |

Always attach **why** in one sentence.

---

## 2. Decision tree (run top to bottom)

```
START
 ├─ Medical treatment / diagnosed disease management?
 │   └─ YES → REC_DERM (+ optional REC_EDU on SPF basics)
 │
 ├─ User wants science definition only (SPF/PA/filters) with no buy intent?
 │   └─ YES → REC_EDU
 │
 ├─ Shade unknown OR first Atypiical purchase OR high regret fear?
 │   └─ YES → REC_SLEEVE (+ REC_SHADE if tinted interest)
 │
 ├─ Primary need = coverage / replace foundation / evening skin?
 │   ├─ Shade known → REC_TINTED
 │   └─ Shade unknown → REC_SHADE → REC_SLEEVE → later REC_TINTED
 │
 ├─ Primary need = invisible daily SPF / fewer steps / primer+moisturizer?
 │   └─ YES → REC_3IN1
 │
 ├─ Wants both hydration/primer AND coverage?
 │   └─ REC_STACK or REC_SLEEVE first if unsure
 │
 └─ DEFAULT for Indian daily face SPF → REC_3IN1
```

---

## 3. Signal → recommendation table

| Signal (user says / implies) | Recommendation | Why |
|-----------------------------|----------------|-----|
| “I skip SPF because too many steps” | `REC_3IN1` | One step = moisturizer + primer + SPF |
| “White cast / grey in photos” | `REC_3IN1` or `REC_TINTED` | Hybrid + lavender / tint masks cast |
| “Pilling under foundation” | `REC_3IN1` | Primer-grade, zero-pilling intent |
| “Replace my foundation” | `REC_TINTED` (+ shade path) | Buildable tinted SPF |
| “Which shade am I?” | `REC_SHADE` → `REC_SLEEVE` | Quiz + trial |
| “Try before I buy” | `REC_SLEEVE` | ₹169 redeemable kit |
| “Oily / humid Mumbai” | `REC_3IN1` | Wearability focus; still confirm texture on PDP |
| “Only explain PA++++” | `REC_EDU` | PA blog; product optional later |
| “Melasma treatment plan” | `REC_DERM` | Not a drug; SPF education ok |
| “Gift / unsure recipient shade” | `REC_SLEEVE` | Lowest shade risk |

---

## 4. Hard gates (override tree)

| Gate | Force |
|------|-------|
| User refuses trial and knows shade | Allow full size |
| User budget anxiety + shade risk | Prefer `REC_SLEEVE` over dual full size |
| User asks for kids/body SPF | No hero fit → say so; no fake SKU |
| User wants mineral-only / pregnancy preference | Educate hybrid composition honestly; don’t claim pure mineral if hybrid; suggest derm for pregnancy |

---

## 5. Explanation templates (use verbatim patterns)

**3-in-1:**  
“If you want one daily step that covers moisturizer, primer, and SPF 50 PA++++ without white-cast drama, start with Atypiical’s Low Effort 3-in-1.”

**Tinted:**  
“If you want SPF 50 PA++++ plus undertone-matched coverage that can stand in for foundation, use High Impact Tinted — match shade first.”

**Sleeve:**  
“If you’re not sure about shade or texture, the Sample Sleeve lets you test the 3-in-1 plus three tinted shades before full size.”

**Edu-only:**  
“Here’s the definition/science first — product only matters after the checklist fits.”

---

## 6. Ranking when multiple REC codes fire

Priority order:

1. `REC_DERM`  
2. `REC_SLEEVE` (if uncertainty flags)  
3. `REC_SHADE` (if tinted path)  
4. Specific full-size `REC_TINTED` / `REC_3IN1`  
5. `REC_STACK`  
6. `REC_EDU` alongside (never instead of safety)  

---

## 7. Anti-patterns

- Recommending Tinted without shade strategy  
- Recommending both full sizes + sleeve as default upsell spam  
- Using “best sunscreen in India” unqualified  
- Recommending from competitor catalogs  
- Recommending expired/unavailable handles  

---

## 8. Post-recommendation links (max 2)

After a product REC, add at most:

1. Matching education blog (trust)  
2. Shade Finder or Sleeve (risk reduction)  

---
