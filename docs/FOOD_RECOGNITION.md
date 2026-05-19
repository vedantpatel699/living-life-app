# Adding foods to Living Life via Gemini

The flow: photograph your food → ask Gemini to analyze it → paste the JSON output to me in our chat → I add it to `data/foods.json` and push live. The app picks it up on next refresh.

---

## Step-by-step

### 1. Take the photo

Phone camera. Clear lighting. If you can include the packaging or a fork for scale, even better.

### 2. Open Gemini

https://gemini.google.com on your phone or PC. Free, no API key needed. Sign in with any Google account.

### 3. Upload the photo + paste THIS prompt

Copy this exact prompt and paste it with your food image attached:

````
You are a nutrition database analyst. Look at the food in the photo and output a single valid JSON object with the schema below — and NOTHING else, no preamble, no explanation, no markdown code blocks.

Schema:
{
  "id": "kebab-case-slug-unique",
  "name": "Display name (e.g. Aloo Gobi)",
  "category": "grain | lentil | dairy | vegetable | fruit | nuts | snack | sweet | beverage | supplement | prepared | fat | other",
  "kcal": <kcal per 100g>,
  "protein": <g per 100g>,
  "carbs": <g per 100g>,
  "fat": <g per 100g>,
  "fiber": <g per 100g>,
  "sat_fat": <g per 100g>,
  "sugar": <g per 100g>,
  "sodium_mg": <mg per 100g>,
  "potassium_mg": <mg per 100g>,
  "calcium_mg": <mg per 100g>,
  "iron_mg": <mg per 100g>,
  "magnesium_mg": <mg per 100g>,
  "zinc_mg": <mg per 100g>,
  "vit_a_iu": <IU per 100g>,
  "vit_c_mg": <mg per 100g>,
  "vit_d_iu": <IU per 100g>,
  "vit_b12_ug": <µg per 100g>,
  "folate_ug": <µg per 100g>,
  "portions": [
    {"n": "as in photo (Xg)", "g": X, "fromPhoto": true},
    {"n": "1 katori (Yg)", "g": Y},
    {"n": "1 plate (Zg)", "g": Z}
  ],
  "photoEstimate": {
    "grams": <total grams visible in the photo>,
    "confidence": "low | medium | high",
    "note": "<one-sentence reasoning for the estimate, e.g. 'plate is ~25cm, looks half-full of rice'>"
  }
}

Rules:
- Use USDA FoodData Central, Indian Food Composition Tables (NIN), or other reputable nutrition databases for values.
- For Indian dishes, base your numbers on standard household recipes (e.g. 1 tsp oil, normal salt).
- If a nutrient value is not commonly tracked for this food or you're not confident, use 0 (don't guess wildly).
- **ALWAYS estimate the portion size visible in the photo** — use the plate size, fork/spoon visible, hand if shown, or typical container as reference for scale. Add it as the FIRST entry in portions (marked "fromPhoto: true") AND as the photoEstimate object with your confidence.
- Include 2-3 additional realistic portion sizes after the photo one (e.g. "1 katori (150g)", "1 plate (250g)", "1 piece").
- The "id" must be lowercase, hyphen-separated, unique (e.g. "aloo-gobi", "rajma-curry").
- Output ONLY the JSON. No "Here is your JSON" preamble. No backticks.
````

### 4. Copy Gemini's response

It should be just a JSON object. Copy it.

### 5. Paste it into our chat

Just paste the JSON to me in our session. I'll:
- **Check for duplicates** against existing IDs in `data/foods.json`. If your new entry looks similar to one already there ("aloo paratha" vs an existing "aloo-paratha"), I'll flag it and ask: "Reuse existing, or add as a variant with a different ID?"
- Verify the structure is valid
- Add it to `data/foods.json` in the repo (or update the existing one if you want a refined estimate)
- Push live
- Confirm with the new ID and category

The app picks it up next time you open it (or hit Settings → "Refresh databases from GitHub" for immediate effect).

### Avoiding duplicates yourself (optional)

If you want Gemini to help avoid creating near-duplicates BEFORE pasting to me:

1. Open the Living Life app → tap **+ Add food** → see your current food list.
2. Note any existing IDs that look similar to what you're about to log.
3. Add this line above the prompt:
   > "Existing food IDs in my database: roti-wheat, dal-makhani, paneer-tikka, ... — if my food matches any of these, use the EXACT existing id. If similar but distinct (e.g. different recipe), use a unique id with a suffix like `-v2` or `-restaurant`."
4. Gemini will return either an existing id (then I update that entry's estimate if better) or a new unique id.

Honestly though — for now, I'll just check on my end when you paste. Less work for you.

---

## Examples of good prompts

**Generic photo:** just paste the prompt above with the photo attached.

**Restaurant meal where you know the dish name:** add a line above the prompt like:
> "This is butter chicken curry with naan, restaurant-style. Use typical North Indian restaurant recipe values."

**Packaged product (e.g. protein bar):** include a photo of the nutrition label — Gemini reads it directly:
> "This is the nutrition label for [brand + product]. Use the exact values shown."

**Homemade food:** include the recipe roughly:
> "This is dal makhani I made with: 1 cup whole urad, 2 tbsp ghee, 1 cup tomato puree, 100g cream. Estimate per-100g values."

---

## What to do if Gemini returns weird JSON

Common issues:
- **Wraps response in markdown code fences (```)** → just delete them before pasting to me. I'll handle this gracefully too.
- **Adds "Here's the JSON:" preamble** → strip it.
- **Returns wildly off values** (e.g. claims a roti is 5 kcal) → push back at Gemini: "Re-check using USDA FoodData. A typical roti is closer to 80 kcal per piece."
- **Refuses for safety reasons** → switch to ChatGPT or describe the food in text and skip the photo.

---

## Tips for accurate values

- **Stick to whole foods first.** Restaurant/complex dishes have huge recipe variance — your homemade dal might be 30% less calories than a restaurant's.
- **Per-100g basis is the gold standard.** Portions like "1 katori" are convenient but vary; per-100g is consistent and lets the app calculate any portion size.
- **Round to sensible precision.** 286 kcal not 285.73. 4 g protein not 4.27.
- **Bigger error sources, in order:** oil/ghee amount → portion size → ingredient ratios → cooking method losses.

A homemade meal estimated to ±15% of actual is great. Don't pretend ±2%.

---

## Quick reference: nutrient daily values (DV) for adult males

These are the targets the app uses for the "% DV" bars. Sources: Health Canada NIH 2023 + IOM DRIs.

| Nutrient | Daily Value |
|---|---|
| Energy | 2000-2500 kcal |
| Protein | 50-130 g (1.6-1.8 g/kg for you) |
| Carbohydrate | 275 g (45-65% of kcal) |
| Total fat | 78 g (20-35% of kcal) |
| Saturated fat | <20 g (<10% of kcal) |
| Fiber | 38 g |
| Sodium | <2300 mg |
| Potassium | 3400 mg |
| Calcium | 1000 mg |
| Iron | 8 mg (adult male) |
| Magnesium | 400 mg |
| Zinc | 11 mg |
| Vitamin A | 3000 IU |
| Vitamin C | 90 mg |
| Vitamin D | 600 IU (Canadian winter: 1000-2000 IU) |
| Vitamin B12 | 2.4 µg |
| Folate | 400 µg |

The app shows "X% DV" per meal and a daily progress bar. Numbers shown are guidance — your real needs vary by activity, season, blood tests.

---

## Why this works

You shoot the photo (knows what you ate) → Gemini extracts the macro/micro estimates (it's surprisingly accurate, food vision has improved dramatically) → I curate the addition (I check sanity, deduplicate, format) → app pulls live (no manual editing).

If you eat the same things often, the DB grows fast and most logging becomes one-tap selection from your personal library.
