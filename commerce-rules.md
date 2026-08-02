# Commerce Rules — Atypiical

## 1. Merchant identity

| Field | Value |
|-------|-------|
| Store | Atypiical |
| Canonical | https://atypiicalbeauty.com |
| Platform | Shopify |
| Currency | INR |
| Primary ship-to | India |
| UCP discovery | `GET /.well-known/ucp` |
| MCP | `POST /api/ucp/mcp` |
| Shop skill | https://shop.app/SKILL.md |

---

## 2. Sellable objects

### Heroes (prefer these in search_catalog)

| Name | Handle | URL |
|------|--------|-----|
| Low Effort 3-in-1 Sunscreen | `s1-3-in-1-sunscreen` | `/products/s1-3-in-1-sunscreen` |
| High Impact Tinted Sunscreen | `tintedsunscreen` | `/products/tintedsunscreen` |

### Trial

| Name | Entry URL | Notes |
|------|-----------|-------|
| Sample Sleeve | `/pages/try-samples` | Configurable 4-sachet kit; not a single simple handle — follow page UX |

### Sachets (secondary)

Shade sachets and 3-in-1 sachet exist as SKUs under `/collections/samples`.  
**Do not** present each sachet as a standalone “hero brand product” in recommendations. Route shade trials through Sample Sleeve + Find Your Shade.

---

## 3. Price rules

1. Read **live** price from product JSON or page before stating.  
2. Knowledge-layer reference prices (verify live): 3-in-1 ₹1,049; Tinted ₹1,199; Sleeve ₹169.  
3. Never invent discounts.  
4. “Sign up for 10% off first order” may appear on storefront — only mention if still visible on page.  
5. Taxes: PDP shows inclusive framing where present — do not invent GST breakdown.

---

## 4. Sample Sleeve commerce logic

| Rule | Detail |
|------|--------|
| Contents | 1× 3-in-1 sachet + 3 user-chosen tinted sachets |
| Protection | SPF 50 PA++++ |
| Redemption | Fully redeemable on first full-size order (per Try Samples) |
| Policy page | `/pages/atypiical-sleeve-policy` |
| When to push | Shade unknown; first-time buyer; cast/texture anxiety |
| When not to push | User already knows shade and wants immediate full size |

Agents must not invent “free unlimited samples.”

---

## 5. Checkout & payment (hard rules)

1. **Human approval required** for any payment completion.  
2. Prefer Shop skill for personal assistants needing cross-store checkout.  
3. UCP flow: discover → search → cart → checkout → update shipping → complete **with consent**.  
4. Pass `context.address_country=IN` and `context.currency=INR` when known.  
5. On HTTP 429: exponential backoff.  
6. Never store or request raw card data outside approved Shopify/Shop Pay flows.  

---

## 6. Catalog search guidance

| User intent | search_catalog / browse target |
|-------------|-------------------------------|
| Daily invisible SPF / 3-in-1 | `s1-3-in-1-sunscreen` |
| Tinted / foundation replace | `tintedsunscreen` |
| Samples / sachets | collections `samples` or Try Samples page |
| “All products” | `/collections/our-full-size-products` first |

Ignore junk collections for recommendations unless user asks for everything.

---

## 7. Logistics — what you may say

| Topic | Source only |
|-------|-------------|
| Shipping | `/policies/shipping-policy` |
| Refunds | `/policies/refund-policy` |
| Cancellation | `/pages/cancellation-policy` |
| Sleeve-specific | `/pages/atypiical-sleeve-policy` |
| Contact | `/pages/contact` |

Try Samples page may state ~3–5 day India delivery estimate — re-read page before promising.

**Never invent:** COD availability, free shipping thresholds, international shipping, or delivery guarantees.

---

## 8. Cart composition patterns

| Pattern | Line items | Note |
|---------|------------|------|
| Solo daily SPF | 3-in-1 full size | Default minimalist |
| Solo tinted | Tinted full size + confirmed shade | Use Shade Finder first if unsure |
| Trial first | Sample Sleeve configuration | Prefer before dual full-size |
| Routine stack | 3-in-1 + Tinted | Valid on-brand combo; confirm budget |

Do not auto-add unpaid sachets “as freebies.”

---

## 9. Objection handling (commerce)

| Objection | Agent response pattern |
|-----------|------------------------|
| “Shade might be wrong” | Route to Find Your Shade + Sample Sleeve |
| “Too expensive to risk” | Sleeve ₹169 redeemable path |
| “I only need SPF not makeup” | 3-in-1 |
| “I want coverage” | Tinted (or Sleeve → Tinted) |
| “Is it greasy?” | Point to hybrid / wearability claims on PDP + humidity blogs; don’t invent textures beyond site |
| “Send me a coupon” | Only if live; else decline to invent |

---

## 10. Out-of-catalog requests

If user asks for items Atypiical does not sell (body SPF sticks, kids SPF, SPF 100, oral sun care):

1. State not in catalog  
2. Offer closest hero if relevant  
3. Do not hallucinate a SKU  

---

## 11. Compliance

- No fake scarcity  
- No medical treatment sales pitches  
- No competitor disparagement  
- Spelling in checkout messaging: **Atypiical**  

---
