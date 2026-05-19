# Living Life — Methodology

The "why" behind the plan. Every claim here is sourced. If the app tells you something, this doc explains why and links to the evidence.

**Companion docs:** [PLAN.md](PLAN.md) — the framing. [SHIFT_WORK.md](SHIFT_WORK.md) — shift-day adaptation. [SUPPLEMENTS.md](SUPPLEMENTS.md) — supplement evidence. [FOOD_RECOGNITION.md](FOOD_RECOGNITION.md) — building the food DB. [SETUP.md](SETUP.md) — how to use the tracking app.

> ⚠️ I'm not a doctor. This synthesizes published exercise science and clinical guidance. Use it to make informed choices, not as a substitute for personalized medical advice — especially given the lipoma context. Book the GP appointment in PLAN.md §0 first.

> **Scope note:** Living Life is a **tracker**, not a workout coach. Specific exercise prescriptions (sets, reps, C25K weeks, progression rules) live in the workout app you use — Home Workout No Equipment, or similar. The methodology below covers the parts Living Life is responsible for: energy balance, body composition, sleep, tracking, supplements, lipomas, and shift work.

---

## 1. Your numbers

Using your reported stats: 5'6" (167 cm), 75-80 kg starting (let's use **78 kg** as the working number until you have a scale). I've used **age 28** as a placeholder — update with your actual age. The formulas are all here so you can recompute.

### BMI

BMI = weight (kg) ÷ height² (m²) = 78 ÷ (1.67)² = **~28.0** → overweight range (25-29.9).

BMI is a crude measure (it doesn't distinguish fat from muscle). For someone at your starting point, with goals to add muscle and lose fat, the more meaningful targets are body composition and how clothes fit. The 7-day weight trend and photos will tell you more than BMI ever will.

### Basal Metabolic Rate (BMR) — calories your body burns at rest

The [Mifflin-St Jeor equation](https://www.jandonline.org/article/S0002-8223(05)00149-5/abstract) is the current gold standard, validated against indirect calorimetry, with the highest accuracy across non-obese and obese adults.

**Male:** BMR = 10 × kg + 6.25 × cm − 5 × age + 5

For Vedant (78 kg, 167 cm, 28 yo): 10(78) + 6.25(167) − 5(28) + 5 = 780 + 1043.75 − 140 + 5 = **~1,689 kcal/day**.

The app uses `bmrPerMinute = BMR ÷ 1440` to show calories-burned-so-far-today on the energy dashboard.

### Total Daily Energy Expenditure (TDEE)

TDEE = BMR + active calories. The activity multipliers most apps use ([Academy of Nutrition and Dietetics guidance](https://www.andeal.org/template.cfm?template=guide_summary&key=621)) are crude. Living Life replaces them with **real active calories from Health Connect**, which is dramatically more accurate (your Garmin/Pixel tracks the actual movement).

For estimation when HC data is missing:

| Activity level | Multiplier | Vedant's TDEE |
|---|---|---|
| Sedentary (desk, no exercise) | 1.20 | ~2,027 kcal |
| Lightly active (1-3 sessions/week) | 1.375 | ~2,322 kcal |
| Moderately active (3-5 sessions/week) | 1.55 | ~2,618 kcal |
| Shift day (Amazon shift = ~500 active kcal) | — | ~2,500-2,800 kcal |
| Very active off-day (training + cardio) | 1.725 | ~2,914 kcal |

**On shift days**, the 10-hour Amazon shift adds ~400-700 active calories on top of BMR. Combined with a workout (~250 kcal), shift-day TDEE lands around **2,500-2,800 kcal**. The app handles this automatically once HC is connected and you've toggled shift days in Settings → Profile.

### Calorie target for fat loss

Safe rate of loss is **0.5-1% of body weight per week**, supported by [ACSM 2009 Position Stand](https://pubmed.ncbi.nlm.nih.gov/19127177/) and the [Garthe et al. 2011 RCT](https://pubmed.ncbi.nlm.nih.gov/21558571/) which showed 0.7%/week preserved lean mass better than 1.4%/week.

For you at 78 kg, that's **390-780 g/week** — roughly 0.5-0.8 kg/week. Faster than 1 kg/week starts eating muscle and tanking your training quality.

A 15-20% deficit off TDEE produces this rate:

- **Off day:** ~1,800-2,000 kcal eat target (TDEE ~2,300 × 0.85)
- **Shift day:** ~2,100-2,400 kcal eat target (TDEE ~2,700 × 0.85)

The energy dashboard surfaces your real deficit each day so you don't have to guess.

### Protein target

During a calorie deficit, protein protects muscle. The [Helms/Aragon/Schoenfeld 2014 systematic review](https://pubmed.ncbi.nlm.nih.gov/24092765/) recommends **1.8-2.7 g protein per kg bodyweight** for resistance-trained athletes in a deficit. The 2024 [Murphy & Koehler meta-regression](https://journals.lww.com/nsca-scj/fulltext/9900/effect_of_dietary_protein_on_fat_free_mass_in.179.aspx) found diminishing returns above ~2.4 g/kg.

For you at 78 kg, the supported range is **125-187 g/day**. Practical target: **130-140 g/day**.

To anchor that visually: ~25-30 g of protein per main meal × 4-5 meals, plus snacks (paneer cubes, lentils, dahi, whey scoop). The app's food DB tracks protein per item and surfaces your daily total against the 130 g target as a percent-of-DV bar.

### Heart rate zones (use these once your Garmin is set up)

Maximum heart rate via the [Tanaka formula](https://pubmed.ncbi.nlm.nih.gov/11153730/) (208 − 0.7 × age), validated on 18,712 subjects across 351 studies:

HRmax (you) = 208 − 0.7(28) = **~188 bpm**

| Zone | % HRmax | Vedant's range | What it feels like |
|---|---|---|---|
| **Z1** Recovery | 50-60% | 94-113 bpm | Walking, easy chat |
| **Z2** Aerobic base | 60-70% | 113-132 bpm | Conversational, slightly out of breath |
| **Z3** Tempo | 70-80% | 132-150 bpm | Can speak in short sentences |
| **Z4** Threshold | 80-90% | 150-169 bpm | One-word answers |
| **Z5** VO2max | 90-100% | 169-188 bpm | All-out |

Most of your running (when you add it) should be in **Z2** (the [polarized training principle](https://www.frontiersin.org/journals/physiology/articles/10.3389/fphys.2014.00033/full): ~80% easy, 20% hard). This counterintuitive truth — that easy aerobic work drives the biggest endurance adaptations — comes from Stephen Seiler's research on elite athletes and applies down to amateur level.

**MAF cross-check (Phil Maffetone's [180 formula](https://philmaffetone.com/180-formula/)):** 180 − age − adjustments. For you as an overweight beginner: 180 − 28 − 5 = **147 bpm cap** for easy aerobic work. This sits inside Z2 and is a safer ceiling early on.

---

## 2. Nutrition methodology

### Why simple meal log over calorie counting (for you)

You said upfront you'd burn out tracking every calorie. The evidence supports your instinct.

Calorie-counting error stacks are larger than most apps admit:

- **Watch / fitness-tracker calorie burn estimates** are off by 27-93% per the [Stanford 2017 study](https://med.stanford.edu/news/all-news/2017/05/fitness-trackers-accurately-measure-heart-rate-but-not-calories-burned.html) (the best device was off 27% on average; the worst, 93%). A 2022 [systematic review of wrist trackers](https://pubmed.ncbi.nlm.nih.gov/35060915/) reached the same conclusion: heart rate good, calorie burn poor.
- **Food labels** have FDA-permitted tolerance of ±20% per item.
- **Recipe variation** adds another ±10-20% for home cooking.

Stacking these, your "logged 1,800 kcal, burned 600, net 1,200" could be reality 950-1,500. The math creates an illusion of precision that doesn't exist.

The "three rules" approach in PLAN.md §3 (water before meals, one plate + 15-minute wait, kitchen closed after dinner) sidesteps this entire error stack by removing decision points instead of trying to quantify them. It works for many people who couldn't sustain calorie counting.

That said — the calorie math above (~2,000 kcal target off day, ~140-160 g protein) is useful **as a sanity check**. If after 3-4 weeks the rules-based approach isn't producing weight loss, the next step is to verify intake roughly matches the target. The app's energy dashboard gives you that sanity check passively.

### Protein — the one number worth tracking

Protein deserves explicit attention because in a deficit it determines whether you lose fat or muscle.

The [Longland et al. 2016 RCT](https://pubmed.ncbi.nlm.nih.gov/26817506/) is the cleanest evidence: groups in a calorie deficit with resistance + interval training, randomized to ~1.2 g/kg vs. ~2.4 g/kg protein. The higher-protein group **gained 1.2 kg of lean mass and lost 4.8 kg of fat**. The lower-protein group lost similar weight but gained only 0.1 kg of lean mass and lost 3.5 kg of fat. Same calorie deficit, dramatically different body-composition outcome.

**Practical:** every meal should have a clear protein anchor (paneer, dal, dahi, milk, tofu, whey scoop). If you hit 4 meals × 30 g protein = 120 g/day, you're in the supported zone. A 25-30 g whey shake post-workout or with breakfast can fill any gap easily.

### Why deeper deficits backfire

A 25%+ TDEE deficit feels productive ("I'm losing faster!") but produces three failure modes:

1. **Muscle loss accelerates.** [Helms et al. 2014](https://pubmed.ncbi.nlm.nih.gov/24092765/) found the deeper the deficit, the greater the lean-mass loss. You end up lighter on the scale but with a worse body composition.
2. **NEAT collapses.** Non-exercise activity thermogenesis — fidgeting, walking around, standing — drops involuntarily under restriction. [Levine 2004](https://journals.physiology.org/doi/full/10.1152/ajpendo.00562.2003) and the [NCBI Bookshelf NEAT review](https://www.ncbi.nlm.nih.gov/books/NBK279077/) describe this in detail. Your actual deficit shrinks because your body unconsciously moves less.
3. **Adaptive thermogenesis.** Metabolic rate drops disproportionately during weight loss, beyond what's explained by lean-mass loss alone. The Leibel/Rosenbaum work and successors document this.

Net effect: aggressive deficits produce 6 weeks of fast loss followed by a stall and a binge cycle. Steady moderate deficits produce 6 months of steady loss.

### Vegetarian-specific gaps

Indian lacto-vegetarian diet has known deficiency hotspots ([NIN guidelines](https://www.nin.res.in/RDA_short_Report_2020.html); also see SUPPLEMENTS.md):

- **Vitamin B12** — only in animal products + dairy at low levels. ~62% of vegetarians have low B12.
- **Vitamin D3** — low in Canadian winters even for non-vegetarians. South Asians have higher deficiency rates.
- **Omega-3 EPA/DHA** — flax/walnut ALA converts at <10% efficiency to EPA/DHA. Algal oil is the vegetarian fix.
- **Iron** — non-heme iron has lower bioavailability. Track ferritin in blood tests.
- **Zinc** — phytates in grains/legumes bind zinc. Soaking and sprouting helps.

These are why the supplements protocol (creatine, whey, D3, B12, omega-3 as tier 1) exists. See SUPPLEMENTS.md for full evidence.

---

## 3. Tracking & metrics — getting the signal out of the noise

### Why daily weight is mostly noise

Body weight bounces 0.5-2.5 kg day-to-day from:
- Sodium intake (water binds to sodium)
- Glycogen storage (each gram of muscle glycogen binds ~3 g of water — a high-carb meal can add 1-2 kg of "weight" overnight; [PubMed reference](https://pubmed.ncbi.nlm.nih.gov/25911631/))
- Bowel content
- Hormonal/cortisol fluctuations
- Hydration status

A single sodium-heavy meal can produce a 1-2 kg overnight gain that has zero relationship to fat balance.

If your fat-loss rate is 0.5 kg/week, that signal is **smaller than the day-to-day noise**. Reading the scale day-to-day is reading noise. You need to extract trend.

### The 7-day moving average — what to actually look at

A simple 7-day moving average eliminates most day-to-day noise while remaining responsive enough to detect real trend changes within 2-3 weeks. The "Hacker's Diet" [Signal and Noise essay](https://www.fourmilab.ch/hackdiet/e4/signalnoise.html) was the first popular write-up of this concept and remains a good read.

The app shows both daily and 7-day average. **Read the average. Ignore the dots.** When you've been steady on the average for 2-3 weeks and want to know if you should adjust, compare this week's average to two weeks ago — that's a real signal.

### Photos — the most underrated tracking tool

The scale is a single noisy number per day. A photo every day (or every two weeks at minimum) captures something the scale can't: where you're losing fat from, whether muscle is appearing, your face changes, posture.

The app's custom camera shows the previous photo at ~30% transparency as a ghost overlay so each new photo is framed the same way — same distance, same pose, same angle. That makes the comparison honest.

Protocol:
1. **Same time of day** — first thing in the morning, after the bathroom, before food/water.
2. **Same lighting** — natural daylight from a window is honest. Overhead bathroom lighting creates shadows that fake definition.
3. **Same outfit** — minimal/tight. Same color or no shirt.
4. **Same poses** — front, side, back. Relaxed (no flexing). Arms slightly away from your sides.
5. **Same camera position** — the ghost overlay handles this for you once you've got a baseline.

After 12 weeks you'll have a real time-lapse of change. After 6 months, dramatic change.

### Health Connect — the layer below the app

Living Life pulls **all** Health Connect data types: steps, distance, active/total calories, heart rate (resting + active), sleep stages, recorded workouts, hydration, weight, body fat percentage, VO2max. Anything your Garmin / Pixel records goes into the daily entry under `entry.hc`.

Two things this enables:
- **Real active-calorie numbers** instead of activity-multiplier guesses. Energy balance becomes accurate.
- **Cross-checking sleep** against the energy/weight trend. If sleep tanks for a week and weight stalls, that's a visible pattern, not a mystery.

The calorie figure from Garmin or Strava is still the algorithm's best guess and is wrong by 25-95% per the Stanford study. **Use it for trend (am I doing more this week?) but don't eat back the number it gives you.** Eat to your target; let the scale and photos verify the math.

---

## 4. Recovery, sleep, stress

### Sleep is non-negotiable during a deficit

The [Nedeltcheva 2010 *Annals of Internal Medicine* crossover trial](https://www.acpjournals.org/doi/abs/10.7326/0003-4819-153-7-201010050-00006) is the cleanest evidence: 10 overweight adults underwent identical caloric restriction with either 5.5 or 8.5 hours of sleep opportunity. Same calorie deficit. The 5.5-hour group:

- Lost **55% less fat** (0.6 kg vs. 1.4 kg)
- Lost **60% more lean mass** (i.e., more of their weight loss was muscle)
- Had **elevated ghrelin** (hunger hormone) — they were also hungrier all day

Translation: under-sleeping during fat loss **inverts the outcome you're trying to produce.** You lose less fat and more muscle.

Practical: aim for **7-8 hours**. Phone out of the bedroom is the highest-leverage habit change you can make for sleep.

### Shift-day sleep is its own problem

Day-sleep is ~30% lower quality than night-sleep for most people. On Amazon shift days (sleeping 12:30 PM – 8:30 PM), you're fighting circadian biology. The SHIFT_WORK.md doc covers the playbook in detail; the key levers:

- Blackout curtains, white noise, cool room (18-20°C)
- Caffeine cutoff 6 hours before your daytime sleep block (so no caffeine after 6:30 AM if you sleep at 12:30 PM)
- Heavy meal 2+ hours before sleep, not right before
- Don't work out after a 10-hour shift — workouts go BEFORE the shift (~9:30 PM)

### DOMS — what's normal and what isn't

Delayed onset muscle soreness peaks 24-72 hours after exercise and resolves within ~72 hours to 7 days ([Cleveland Clinic](https://my.clevelandclinic.org/health/diseases/delayed-onset-muscle-soreness); [Cheung et al. 2003](https://pubmed.ncbi.nlm.nih.gov/12617692/)).

- **Mild soreness** — train through it normally.
- **Moderate soreness** — train a different muscle group; do an easy session.
- **Severe** — barely-functional range of motion, persistent pain past 7 days, or dark urine — **see a doctor.** Severe rhabdomyolysis is rare but real, especially in unaccustomed beginners going too hard.

### Active rest > passive rest

Active rest (easy walking, mobility, light yoga) produces equal or modestly better recovery than passive rest after intense sessions. The effect size is small but real, and the activity itself costs nothing.

---

## 5. Lipomas — what the medicine says

This section is important. Repeating from PLAN.md §0 because it's worth saying twice:

### What lipomas are

Lipomas are benign soft-tissue tumors composed of mature adipocytes, encapsulated by a thin fibrous capsule. They are the **most common benign soft-tissue tumor in adults**, prevalence ~2.1 per 1,000 people, typically presenting in adults aged 40-60 ([StatPearls](https://www.ncbi.nlm.nih.gov/books/NBK507906/); [Mayo Clinic](https://www.mayoclinic.org/diseases-conditions/lipoma/diagnosis-treatment/drc-20374474)).

### Weight loss does not reliably shrink them

This is the part you may not want to hear, but it's important: **lipomas may grow somewhat with weight gain, but typically do not shrink with weight loss.** They are encapsulated and operate semi-independently from the body's normal subcutaneous adipose stores ([Medscape clinical](https://emedicine.medscape.com/article/1057855-clinical)). Many patients perceive lipomas as *more* prominent after weight loss because surrounding tissue thins.

Mayo Clinic's listed treatments are surgical excision, liposuction, or steroid injection. Diet and exercise are not on the list ([Mayo Clinic Lipoma treatment](https://www.mayoclinic.org/diseases-conditions/lipoma/diagnosis-treatment/drc-20374474)).

This doesn't mean don't lose weight — losing weight is great for many reasons (joint health, metabolic health, cardiovascular fitness, energy, mood). It means **don't pin your hopes for lipoma reduction on weight loss.** That's the wrong tool.

### Differentials worth ruling out

You mentioned "developing severe lipomas on arms and legs." Multiple lipomas in a younger adult raise several differentials ([NCBI Endotext review](https://www.ncbi.nlm.nih.gov/books/NBK552156/)):

- **Familial Multiple Lipomatosis (FML):** autosomal dominant inheritance, multiple non-painful lipomas, family history is key ([Wikipedia overview](https://en.wikipedia.org/wiki/Familial_multiple_lipomatosis)).
- **Dercum's Disease (Adiposis Dolorosa):** multiple **painful** lipomas, often with fatigue and cognitive symptoms ([StatPearls](https://www.ncbi.nlm.nih.gov/books/NBK507867/?report=reader)).
- **Madelung's Disease (Multiple Symmetric Lipomatosis):** symmetric upper-body fat masses, strongly associated with chronic alcohol use, predominantly male.

The differentiating axes: **painful vs. non-painful**, **distribution (random vs. symmetric)**, **family history**, **alcohol use**.

### When to see a doctor — soon

Any of these is a reason to book an appointment now, not "after I lose some weight":

- Rapid growth of any lipoma
- Pain or tenderness
- Hardening, fixation to deeper tissue, change in texture
- Skin changes overlying the lump
- A mass >5 cm in diameter (raises concern about liposarcoma — rare but important to exclude)
- Multiple new lipomas at a younger age (you're at age ~28, so this applies)
- Family history of multiple lipomas
- Lipomas with systemic symptoms (fatigue, cognitive changes)

The differential matters because **management differs.** FML may be observation-only. Dercum's may benefit from specific medication. Liposarcoma must be excluded surgically. Don't let anything delay the medical workup.

---

## 6. How the app supports all of this

Quick mapping from research → app feature:

| Research finding | App feature |
|---|---|
| Day-to-day weight is noise; trend is signal | 7-day moving average on Progress + Today screens |
| Photo standardization matters | Custom camera with previous-photo ghost overlay at ~30% transparency |
| Real active calories beat activity multipliers | Health Connect sync — all data types stored in entry.hc |
| BMR-per-minute × elapsed minutes = burned-so-far | Google-Fit-style energy dashboard on Today screen |
| Shift work shifts everything | Profile → Shift days toggle; energy + supplements adjust automatically |
| ~80/20 polarized cardio (when you add running) | Z2 HR target documented; HC gives real HR by activity |
| Protein matters in deficit | Food DB tracks protein per item; daily total vs 130 g target |
| Vegetarian-specific micronutrient gaps | Full vitamin/mineral profile per food + % DV bars; supplements DB |
| 7-8 h sleep matters during deficit | Sleep stages from HC; visible on Progress |
| Lipoma tracking for GP | Dedicated lipoma note field in Log Entry, compiled for GP visit |

---

## 7. The honest limits

Things I want you to know about this doc:

- **The methodology numbers (BMR, TDEE multipliers, HRmax) are starting points.** Individual variation is real — your BMR could be 10% above or below the Mifflin-St Jeor estimate. Treat numbers as starting points to be adjusted from your real-world data after 2-4 weeks.
- **Wearable calorie estimates are noisy.** Even with Health Connect feeding real data, the active-calorie number is the algorithm's best guess. Use it for trend, not as a precision instrument.
- **Conservative ≠ slow forever.** A 0.5 kg/week loss is unglamorous and works. Going faster will break the plan within 6 weeks (injury, binge, or burnout). Going slower works for years.
- **I am not your doctor.** Especially given the lipoma context: book the GP appointment. Get baseline blood work. Get cleared for higher-intensity exercise.

---

## Sources

Every claim above traces back to one of these.

**Calories / nutrition**
- [Frankenfield 2005 — RMR equations comparison](https://www.jandonline.org/article/S0002-8223(05)00149-5/abstract)
- [Helms, Aragon & Fitschen 2014 — Protein in deficit](https://pubmed.ncbi.nlm.nih.gov/24092765/)
- [Longland et al. 2016 — Higher protein in deficit RCT](https://pubmed.ncbi.nlm.nih.gov/26817506/)
- [ACSM 2009 — Weight loss position stand](https://pubmed.ncbi.nlm.nih.gov/19127177/)
- [Garthe 2011 — Weight loss rates and body composition](https://pubmed.ncbi.nlm.nih.gov/21558571/)
- [Stanford 2017 — Wearable calorie burn accuracy](https://med.stanford.edu/news/all-news/2017/05/fitness-trackers-accurately-measure-heart-rate-but-not-calories-burned.html)
- [2022 Systematic review — wrist activity trackers](https://pubmed.ncbi.nlm.nih.gov/35060915/)
- [Levine 2004 — NEAT](https://journals.physiology.org/doi/full/10.1152/ajpendo.00562.2003)

**Heart rate / cardio**
- [Tanaka, Monahan & Seals 2001 — HRmax revisited](https://pubmed.ncbi.nlm.nih.gov/11153730/)
- [Seiler 2010 — Polarized training intensity distribution](https://pubmed.ncbi.nlm.nih.gov/20861519/)
- [Stöggl & Sperlich 2014 — Polarized vs threshold RCT](https://www.frontiersin.org/journals/physiology/articles/10.3389/fphys.2014.00033/full)
- [Maffetone — 180 formula](https://philmaffetone.com/180-formula/)

**Sleep & recovery**
- [Nedeltcheva 2010 — Sleep and fat loss crossover trial](https://www.acpjournals.org/doi/abs/10.7326/0003-4819-153-7-201010050-00006)
- [Cheung 2003 — DOMS treatment](https://pubmed.ncbi.nlm.nih.gov/12617692/)

**Tracking / weight noise**
- [Fourmilab Hacker's Diet — Signal and Noise](https://www.fourmilab.ch/hackdiet/e4/signalnoise.html)
- [Muscle glycogen and water](https://pubmed.ncbi.nlm.nih.gov/25911631/)

**Lipomas**
- [Mayo Clinic — Lipoma](https://www.mayoclinic.org/diseases-conditions/lipoma/diagnosis-treatment/drc-20374474)
- [StatPearls — Lipoma](https://www.ncbi.nlm.nih.gov/books/NBK507906/)
- [StatPearls — Adiposis Dolorosa (Dercum's)](https://www.ncbi.nlm.nih.gov/books/NBK507867/?report=reader)
- [NCBI Endotext — Adipose tissue diseases](https://www.ncbi.nlm.nih.gov/books/NBK552156/)
- [Wikipedia — Familial Multiple Lipomatosis](https://en.wikipedia.org/wiki/Familial_multiple_lipomatosis)
