# Living Life — Research Foundation

**The complete evidence base behind every design decision in Living Life.** Built from 7+ rounds of structured research using both Gemini-in-Studio (codebase-aware) and ChatGPT (independent cross-validation). Every recommendation in the app traces back to a citation here.

**Status:** Living document. Updated 2026-05-18. Final research batch (Q1-Q5 on TRE + HRV + habit + SSRI long-term + gaps) still pending — see §13.

**Reading guide:**
- §1 = the user (constraint set every feature must serve)
- §2 = cross-validated non-negotiables (where both AIs agreed)
- §3-9 = research by domain
- §10 = feature roadmap with P0/P1/P2
- §11 = Vedant-specific physiology notes
- §12 = master citation list
- §13 = pending research

---

## 1. User profile — the constraint set

The single most important document section. Every design decision derives from these constraints.

### Identity
- 28-year-old male
- 5'6" (167 cm), ~78 kg starting (BMI ~28 European-equivalent, **~30+ South Asian-equivalent** — see §11.2)
- Indian lacto-vegetarian: dairy yes (paneer, dahi, milk, ghee), pulses, grains, nuts. **No eggs, meat, fish.**
- Calgary, Canada (51°N latitude — Arctic-level winter photoperiod, Oct-Mar)
- Introvert. Solo home workouts only. No gym, no social fitness mechanics.

### Schedule
- Amazon **night shifts 1:20 AM – 11:30 AM**, 2-4 days/week
- Home ~12:15 PM after shift
- **1-2 hours decompression window** before sleep (variable — does things at home)
- Sleep window on shift days: **~1:30 PM – 9:30 PM** (target 7.5-8h)
- Off days: normal night sleep

### Medical / pharmacological context
- **On fluoxetine (SSRI)** — long-term
  - CYP1A2 inhibitor → caffeine half-life doubles to ~10-12h
  - Possible emotional blunting
  - SIADH/hyponatremia risk (low absolute risk in young male, but real)
  - Long half-life of parent (~4-6 days) + active metabolite norfluoxetine (~7-15 days)
- **Multiple lipomas** on arms and legs — benign, tracked in notes for GP visits only. **Weight loss does NOT shrink lipomas** (Mayo Clinic; StatPearls 2024). Not surfaced as fitness-app feature.

### Equipment
- Garmin watch (HR, HRV, Body Battery, sleep, VO2max)
- Pixel 8 Pro
- Health Connect (Android) — pulls all biosensor data
- **Workouts run in external app** (Home Workout No Equipment) — Living Life is a tracker, NOT a workout prescriber
- No 10k-lux light therapy box yet (recommend Carex Day-Light Sky or Verilux HappyLight Luxe, ~$40-80 CAD)

### Goals (priority order)
1. Sustainable fat loss at ~0.5 kg/week (78 → ~65-67 kg per South Asian BMI thresholds)
2. Preserve/build muscle during deficit
3. Survive shift work without breaking habits (sleep + circadian + meals)
4. Address overeating tendencies — **environment-based rules over willpower**
5. Build daily habits sustainable for 12+ months

### Stated preferences (binding design constraints)
- No social/sharing features
- No streaks (one shift wreck breaks the loop)
- No calorie/macro auto-optimizer
- No AI meal planning
- No prescriptive dieting
- No notifications during sleep window (12:00 PM – 9:30 PM on shift days)
- Tracker > coach. Less is more.

---

## 2. Cross-validated principles (where Gemini + ChatGPT + literature converged)

These are the non-negotiables. Strong consensus across independent sources = ship.

### Principle A — Sleep sovereignty
Sleep protection outranks tracking completeness, adherence prompts, hydration nudges, and coach commentary. A "helpful" notification that delays sleep onset by 10 minutes nets negative for fat loss + mood.
- Cites: Pielot 2014, Trauer 2015 (CBT-I meta), Eastman & Burgess 2009, Nedeltcheva 2010

### Principle B — Pre-decided > real-time self-control
Implementation intentions (if-then planning) outperform in-the-moment restraint, especially after night work when motivational priority shifts toward immediate reward.
- Cites: Gollwitzer 1999, Adriaanse 2011 meta-analysis (d ≈ 0.51 for healthy eating), Inzlicht 2014 (refuting depleted-resource model)

### Principle C — Daily noise vs trend signal
Daily weight, daily calories, daily active calories are observations, not decisions. Trend windows: 7-day moving average for current direction, 28-day rate vs target for real progress.
- Cites: Walker (Hacker's Diet 1991), Shcherbina 2017 Stanford (27-93% wearable kcal error), Bhutani 2017 PMC

### Principle D — Coverage > streaks
Hard streaks are fragile — one missed shift breaks engagement. Use "5 of 7 days protected" framing. Loss aversion is real (Kahneman/Tversky) but streak loss triggers what-the-hell.
- Cites: Polivy & Herman 1985 counter-regulatory eating, Kahneman & Tversky 1979, Cochran & Tesser

### Principle E — Gain-framed copy, never loss-framed
SSRI users prone to rumination + introvert profile + overeating risk = loss framing actively backfires. All app copy uses gain frames ("Eat the saved meal") or neutral declaratives ("Plate done. Kitchen closed").
- Cites: Rothman & Salovey 1997, Polivy & Herman 1985, Heatherton & Baumeister 1991

### Principle F — Situational hierarchy, not static
Today screen shows different primary content depending on day type (shift day / off day / recovery day / transition day). Information scent dictates what the user needs first.
- Cites: Pirolli & Card 1999 information foraging, Choe et al. 2014 quantified-self practices, Miller 1956 chunking

### Principle G — JITAI rules, not scheduled notifications
Prompts fire only when 2+ risk signals coincide. Scheduled time-based reminders cause fatigue and erode trust within weeks.
- Cites: Klasnja & Hekler 2018, Nahum-Shani et al. 2018, Pielot 2018

### Principle H — South Asian phenotype reframing
Use BMI 23 (overweight) / 25 (obese) cutoffs for South Asians, not WHO European 25/30. Vedant's target should be ~64-67 kg (not the originally-planned 70 kg) per metabolic-risk thresholds.
- Cites: Misra & Khurana 2008, WHO 2004 expert consultation, INTERHEART (Yusuf 2004) Lancet

### Principle I — Fluoxetine pharmacology shapes the protocol
Caffeine cutoffs tighter (CYP1A2 inhibition doubles half-life). Ashwagandha removed. St. John's Wort, 5-HTP, SAMe, tryptophan permanent NO. Sodium attention required (SIADH risk).
- Cites: Wormhoudt 1999 CYP1A2; Jacob & Spinler 2006 hyponatremia

---

## 3. Supplement protocol

### 3.1 Tier 1 — daily core stack

| Supplement | Dose | Timing | Why | Evidence |
|---|---|---|---|---|
| **Creatine monohydrate** | 5 g/day | Anytime (post-workout typical; wake-up on shift days) | Strength + muscle; **also SSRI mood adjunct** | Lyoo 2012 RCT n=52: 52% remission creatine+SSRI vs 26% SSRI alone in women w/ MDD, NNT≈4. Kious 2019 review confirms brain phosphocreatine mechanism. Roitman 2007 — unipolar OK, caution bipolar |
| **Whey protein** | 25-50 g as needed to close protein gap | Post-workout or breakfast | Convenience to hit 130-140 g protein daily. **High leucine (~2.5g/scoop)** — hits MPS threshold for vegetarian | Witard 2014; Phillips & van Loon 2011 |
| **Vitamin D3** | **3000-4000 IU winter** (Oct-Mar), 2000 IU summer — pending 25(OH)D test | With breakfast (fat needed) | Calgary 51°N + South Asian skin = high deficiency risk. Target serum >75 nmol/L | Heaney 2003 dose-response (~1000 IU → +12 nmol/L); Holick/Endocrine Society 2011; Mithal 2009 (70-90% Indians deficient); Aloia 2008 (darker skin needs higher dose) |
| **Vitamin B12 (methylcobalamin)** | 500 µg/day OR 2,500 µg/week | Anytime (morning typical) | ~62% of vegetarians have low B12 ([Pawlak 2014](https://pubmed.ncbi.nlm.nih.gov/24667752/)). Methylcobalamin > cyanocobalamin for absorption | Allen 2009; Pawlak 2014 |
| **Algal omega-3 EPA-forward** | **≥1g EPA/day** (≥60% EPA ratio, not combined EPA+DHA) | With breakfast (fat needed) | Vegetarians convert <10% ALA→EPA. **SSRI mood adjunct + cardiometabolic** | Liao 2019 meta-analysis 26 RCTs (d≈0.39 vs placebo for depression); Mocking 2016; Mischoulon ICEPC 2019 consensus 1-2 g EPA/day |

**Product upgrade needed:** current omega-3 is sub-1g EPA. Switch to **iwi Life Omega-3** or **Testa Omega-3** (verified ≥60% EPA algal) at 1-2g EPA/day.

### 3.2 Tier 2 — shift-work additions

| Supplement | Dose | Timing | Notes |
|---|---|---|---|
| **Melatonin (low-dose)** | **0.3-0.5 mg sublingual** | 30-60 min pre-sleep on shift days (target ~12:30-1:30 PM) | **NOT 3-5 mg.** Higher doses cause grogginess + may blunt endogenous production. **User had 5 mg — switch immediately.** Canadian options: Pure Encapsulations Melatonin 0.5 mg, Webber Naturals Easy-Dose, Source Naturals 1 mg splittable |
| **Magnesium glycinate** | 200-400 mg elemental | 30-60 min pre-sleep | NOT oxide/citrate (GI issues). Sleep onset + general status (shift workers tend to be lower) |
| **L-theanine** | 100-200 mg | Pre-sleep OR paired with shift caffeine | Smooths caffeine arousal without sedation. Suntheanine-branded best-studied |
| **Glycine** | 3 g | 30-60 min pre-sleep (optional) | Core body temp drop. Cheap. Weak-moderate evidence |
| **Electrolytes (Na/K/Mg)** | 1 scoop ~500 mL water | Pre-run or during Amazon shifts if heavy sweating | LMNT, Liquid IV, Nuun. Critical given SSRI hyponatremia risk |
| ~~Caffeine~~ | **REMOVED PER USER** | — | User opted out of caffeine tracking entirely (2026-05-18). Removed from supplements.json + Today-screen card + shift schedule slot. If you reintroduce caffeine consumption: cutoff 4 AM shift days / noon off days, calibrate to personal sleep latency (not the previously-claimed pharmacokinetic doubling — see §11.4) |

### 3.3 Tier 3 — REMOVED / never take

| Supplement | Why removed |
|---|---|
| **Ashwagandha** | SSRI interaction (mild serotonergic + GABAergic); ≥15 published case reports of cholestatic hepatitis. With fluoxetine's long half-life, any washout is slow |
| **St. John's Wort** | Serotonin syndrome risk on SSRI. Never. |
| **5-HTP** | Serotonin syndrome risk on SSRI. Never. |
| **SAMe** | Serotonin syndrome risk on SSRI. Never. |
| **Tryptophan** | Serotonin syndrome risk on SSRI. Never. |
| **BCAAs** | Total protein adequate makes redundant (Wolfe 2017 JISSN). Cost without benefit |
| **Glutamine** | No meaningful effect in healthy lifters. Burn/critical patients only |
| **Fat burners / thermogenics** | Caffeine + filler + side effects. Just take caffeine |
| **Tribulus / test boosters / DHEA** | No T effect in normal-range men. Save money |
| **Detox/cleanse pills** | No mechanism. Liver and kidneys do this |
| **CLA, Garcinia, ACV pills** | Null trials; one (Garcinia) has liver injury reports |
| **Pre-workout proprietary blends** | Hides doses |
| **Mass gainers** | Sugar + cheap protein. Eat dal-rice-paneer |
| **Apigenin** | Marketing-heavy, weak human data |
| **Tart cherry** | To get meaningful melatonin dose costs $40-60/mo; direct melatonin cheaper |
| **Vitamin K2 MK-7** | No shift-work-specific evidence |
| **CoQ10** | No evidence for fatigue/energy in healthy adults |
| **Probiotics** | Mixed trials. Food sources (dahi, kefir) first |
| **Rhodiola** | Modest effect; redundant with caffeine strategy |

### 3.4 Pending changes to current stack

- [ ] Omega-3 → swap to EPA-forward ≥1g EPA/day (iwi Life or Testa)
- [ ] Vitamin D → blood test → bump to 3000-4000 IU winter
- [ ] Melatonin → drop from 5 mg to 0.3-0.5 mg
- [ ] Iodine → audit kitchen salt (iodized vs Himalayan/sea)
- [ ] Per-meal **leucine tracking** added to protein density tracker

---

## 4. Sleep — shift-work adaptation protocol

### 4.1 Mechanism (why daytime sleep is hard)

- Day-sleep is ~30% lower quality than night-sleep for most people (Akerstedt 1998)
- Circadian "wake drive" is strongest in afternoon — your 1:30 PM sleep onset fights biology
- Cortisol AM peak normally; you're asleep through it → mismatch
- Light leakage = single biggest sleep-quality determinant (Crowley 2003)

### 4.2 Phase-shift principles for rotating shifts

**Goal: compromise phase position, NOT full inversion.** You work 2-4 nights then return to days. Full circadian flip would wreck off-days. Aim for partial adaptation that protects daytime sleep without locking you out of normal-day living.

- **Eastman & Burgess 2009, Sleep Med Rev** — bright light + scheduled dark + sunglasses shift phase; light avoidance during biological morning matters more than the light box dose
- **Burgess 2010, J Pineal Res** — melatonin phase response curve: low-dose 0.5 mg taken 2-4h pre-sleep gives strongest phase delay
- **Crowley & Eastman 2003** — sunglasses on morning commute home is one of the highest-leverage interventions (lab studies show 30-60 min sleep latency reduction)

### 4.3 Melatonin — what the evidence actually says

- **Brzezinski et al. 2005 meta-analysis** — dose-response **plateaus at 0.3-1 mg** for sleep onset. Higher doses cause more side effects without faster onset.
- **Burgess PRC work** — 0.5 mg = active dose for phase shifting
- **5 mg (Vedant's current)** is supraphysiological — plasma elevated 8-10h, may blunt endogenous production, morning grogginess common
- **Action:** drop to **0.3-0.5 mg sublingual** taken ~30-60 min pre-sleep on shift days only

### 4.4 CBT-I principles for shift workers

- **Trauer 2015 meta-analysis** (J Sleep Res) — CBT-I improved sleep onset latency by ~19 min, wake after sleep onset by ~26 min, sleep efficiency by ~10%
- For shift workers: **stimulus control** (bed = sleep only; leave bed if awake >20 min) + **protected fixed sleep opportunity** are the high-yield CBT-I components
- **Avoid sleep restriction therapy** after heavy Amazon shifts — already sleep-deprived; SRT can backfire

### 4.5 Bedroom environment — ranked by effect size

| Intervention | Effect | Cost | Priority |
|---|---|---|---|
| **Blackout curtains/film** | Large — single biggest sleep-quality lever for shift workers | ~$30-60 CAD | **#1 purchase** |
| **Room cooling to 18°C** | Moderate (~30 min onset latency reduction) | Free | #2 |
| **White noise 60-65 dB** | Moderate (Stanchina 2005) | $20 | #3 |
| **Eye mask backup** | Smaller (Hu 2020) but useful if curtains imperfect | $10 | #4 |
| **Earplugs** | Useful in noisy households | $5 | Optional |

Citations: Crowley 2003, Boivin lab, Hagai Or 2019 thermoregulation, Hu 2020 ICU sleep mask, Stanchina 2005 white noise in ICUs.

### 4.6 Chronotype assessment

- **MCTQShift** (Juda & Roenneberg 2013, J Biol Rhythms) — chronotype questionnaire specifically validated for shift workers. Takes ~10 min.
- Predicts shift tolerance, not destiny. Strong morning types tolerate night shifts worse; strong evening types better.
- **Action:** take MCTQShift once. Surface result in app as "tolerance profile." If strong morning type → app treats every shift day as elevated risk.

### 4.7 Nap protocols

- **Sallinen 2003** — 20-30 min nap before night shift reduces microsleeps
- **Akerstedt 2002** — sleep inertia worse after 30-60 min naps than 20-min
- **For Vedant's schedule:** 30 min wake-to-shift window is too tight for naps; main wake at 9:30 PM serves the purpose. If needed: 15-20 min only, never 45+

### 4.8 Smart alarm research

- Smart alarms (waking in light sleep within window) are **plausible, not well-validated**
- Akerstedt: sleep inertia is worse when waking from slow-wave sleep
- Consumer device sleep-stage detection has variable accuracy
- **Recommendation:** Garmin smart alarm 9:00-9:30 PM **window with hard backup at 9:30 PM**. Don't let "clever timing" shave 20-30 min off sleep duration

### 4.9 Hyponatremia / SSRI risk

- **Jacob & Spinler 2006** — SSRI-associated hyponatremia/SIADH incidence 0.5-32% in older-adult literature
- Risk factors: older age, female sex, low body weight, diuretics — **all mostly absent in 28M young athletic profile**
- But Amazon physical work + plain water overload + SSRI = elevated relative risk
- **Practical rule:** drink to thirst; pair high-volume fluids with electrolytes if sweating; red flags = confusion, severe headache, vomiting, sudden weakness, seizures

### 4.10 Vedant-specific P1 sleep protocol

| # | Time | Action | Why |
|---|---|---|---|
| 1 | 10:30-11:00 AM (still at Amazon) | Take 0.5 mg melatonin sublingual. Dark sunglasses BEFORE exit | Phase-delay anchor + light avoidance |
| 2 | 11:30 AM-12:15 PM (commute) | Sunglasses on. No errands. No bright windows on drive | Single morning bright-light exposure can erase 30+ min sleep latency |
| 3 | 12:15-1:30 PM (decompression) | Dim-light only. Screens <30% + night mode. Shower lukewarm. Reading on paper. **No workout. No new caffeine.** | Crowley 2003 — light in this window erodes deep sleep 30-90 min |
| 4 | 12:30 PM | Saved post-shift meal (protein-anchored, ~400-450 kcal) | Pre-decided, no kitchen searching |
| 5 | 1:30 PM | **Kitchen closed.** Final bathroom. Phone DND | Hydration cutoff — prevents 4 AM bathroom waking |
| 6 | 1:30-2:00 PM | Blackout drawn. Room 18°C. White noise. Eye mask backup | Environment defaults |
| 7 | 2:00 PM | Sleep. Hard backup alarm 9:30 PM | |
| 8 | 9:00-9:30 PM | Wake. Bright indoor light 20 min. Electrolytes (not plain water bolus) | Bright-light entrainment + SSRI hyponatremia avoidance |
| 9 | 9:30-10:00 PM | Pre-workout meal: small carb + protein | Day-start anchor |
| 10 | 10:00-11:00 PM | Workout (45 min max on shift days) | Pre-shift, protects daytime sleep block |
| 11 | 11:00 PM-12:30 AM | Dinner + shift prep | |
| 12 | 12:30-1:00 AM | Out the door | |

---

## 5. Notifications & JITAI design

### 5.1 Notification cost research

- **Pielot 2014, MobileHCI** — in-situ study: high notification volume → "overwhelmed, stressed, interrupted, annoyed" emotions
- **Mehrotra & Musolesi 2017** — context-aware delivery reduces emotional cost
- **Mark 2008** — interrupted work is faster but stress + frustration higher
- **Adamczyk & Bailey 2004** — recovery time after interruption ~25 min for cognitive work
- **No study quantifies "per-notification cost for a fatigued, SSRI-medicated brain after a 10h Amazon shift"** — but the synthesis is: treat every push notification after 10:30 AM as expensive unless safety-critical

### 5.2 JITAI design principles

- **Nahum-Shani et al. 2018, Ann Behav Med** — JITAIs are characterized by decision points + tailoring variables + intervention options + decision rules. They are NOT "ping whenever you see risk."
- **Klasnja & Hekler 2018, MRT design** — timing rules require testing; "vibes" don't cut it
- **Minimum signal strength rule:** push only when 2+ risk signals coincide AND there's a clear one-tap action available
- **Trust degradation:** false-positive prompts erode trust quickly; user dismisses → ignores → uninstalls

### 5.3 Framing — what to say

- **Rothman & Salovey 1997, Psychol Bull** — message framing matters: gain frames better for prevention behaviors, loss frames better for detection behaviors
- For Vedant's app: most prompts are prevention (sleep protection, protein adherence) → **gain frames only**
- **Polivy & Herman 1985** — restrictive/loss framing triggers counter-regulatory eating
- **Ban these phrasings:** "you failed," "don't ruin," "streak at risk," "calories over," "you're losing your goal"
- **Use these phrasings:** "eat the saved meal," "protect tomorrow," "plate done," "next step is…"

### 5.4 Sleep-Sovereign Notification Gate (single most important rule)

```
Living Life never pushes notifications from 12:00 PM to 9:30 PM
on shift days, except for true safety-critical alerts (e.g., HR
anomaly). All coaching, hydration, protein, supplement, and trend
feedback waits for wake time or appears only on app-open.
```

### 5.5 JITAI rule table

| Trigger | Channel | Urgency | Framing |
|---|---|---|---|
| 10:30 AM @ Amazon (melatonin reminder + sunglasses) | Push (tactile-only vibration) | Med | "Darkness signal: 0.5 mg melatonin + sunglasses on before exit" |
| Caffeine logged after 2:30 AM cutoff | Push | High | "Caffeine late for today's sleep window. Stop here to protect 2 PM sleep" |
| 11:30 AM shift ended + protein floor not met + food log empty | In-app card on app-open only | Med | "Post-shift landing: eat saved protein meal, then sleep setup" |
| 11:45 AM + heavy active shift + no water | In-app card only | Low | "Drink to thirst. If sweating heavily, pair fluids with food/electrolytes" |
| 12:00 PM – 9:30 PM sleep window | Silent data update only | None | No message |
| 9:30 PM wake + sleep <6.5h | In-app card on open | Med | "Recovery mode today: keep it small. Protein, water, workout only if reasonable" |
| 9:30-10:30 PM workout window | No push | None | No message |
| 2+ missed supplement slots in 7 days | In-app card | Low | "Supplement drift detected. Review shift-day slot" |
| Weight spike + low sleep + high RHR | Progress-screen annotation | Low | "Likely noise: poor sleep + high RHR distort scale weight. Hold calories steady" |
| 3+ days low protein + weight loss >0.7 kg/week | In-app card + weekly coach | Med | "Muscle-retention risk up. Prioritize protein anchors before changing calories" |
| App unopened by 10:45 PM on shift day | One push max | Med | "Set up shift day in 60 sec: meal, caffeine cutoff, sleep target" |
| Any prompt dismissed twice in 7 days | Suppress for 7 days | Trust-preserving | No message |

**Daily push cap on shift days: 2 max** (excluding safety alarms). Everything else = in-app cards.

---

## 6. Overeating intercept

### 6.1 Mechanism — the post-shift perfect storm

Five overlapping drivers. None alone is the explanation; the stack is.

| Mechanism | Evidence | Effect size | Citation |
|---|---|---|---|
| **Sleep restriction → ghrelin/leptin shift** | 2 nights 4h sleep → leptin -18%, ghrelin +28%, hunger +24%, appetite +23%, high-carb cravings +33-45% | Large | Spiegel et al. 2004, Ann Intern Med |
| **Habitual short sleep + appetite hormones** | 5h vs 8h habitual → leptin -15.5%, ghrelin +14.9% | Large | Taheri et al. 2004, PLoS Med |
| **Circadian misalignment** | Eating during biological night worsens leptin, glucose, insulin, cortisol regulation | Strong for metabolism | Scheer et al. 2009, PNAS; Bandín 2015 |
| **Sleep loss → food reward sensitivity** | Restricted sleep increases brain reward activation to food cues | Medium | St-Onge et al. (AJCN); Boswell & Kober meta r≈0.33 |
| **Counter-regulatory "what-the-hell" effect** | Perceived diet violation triggers escalating disinhibition | Strong classic theory | Polivy & Herman 1985; Heatherton & Baumeister 1991 binge-as-escape |

### 6.2 The contested mechanism: ego depletion

- **Inzlicht 2014** refuted Baumeister's "willpower as depleted resource" model
- Better framing: night work causes **shifts in motivational priority** (immediate reward valuation up; long-term goal valuation down). Not "you can't"; it's "your brain de-values the long goal."
- **Design implication:** don't ask the fatigued user to "choose wisely." Remove the choice.

### 6.3 SSRI-specific appetite effects

- **Fluoxetine** in short-term: weight-neutral or modest weight loss (Michelson 1999)
- Long-term: variable; some weight regain on remission
- **Emotional blunting** reduces salience of breaking environment rules
- **Watch out:** fluoxetine may reduce shame about overeating (good for mental health, but removes a negative-affect inhibitor)

### 6.4 Intervention evidence — what works for post-shift / late-night / disinhibited eating

| Intervention | Effect size | Evidence | Citation |
|---|---|---|---|
| **Implementation intentions (if-then)** | d ≈ 0.51 healthy eating; d ≈ 0.29 unhealthy eating | Strong, modest magnitude | Adriaanse 2011 meta-analysis (n=23 studies) |
| **Replacement plans (not negation)** | Negation plans can backfire when habits strong | Strong | Adriaanse — "what not to eat" ironic effects |
| **Cognitive defusion (ACT)** | d ≈ 0.7-0.9 vs suppression for food cravings | Strong | Forman 2007; Hayes ACT 2006 |
| **Self-compassion after slip** | Reduces post-violation eating in restrictive eaters | Moderate, narrow sample | Adams & Leary 2007; Neff & Germer 2013 |
| **Environment / cue reduction** | Cue-reactivity predicts eating r≈0.33 | Strong conceptually | Schachter cue-reactivity; **NOT Wansink** (discredited, retracted papers) |
| **MB-EAT (mindful eating)** | Reduces binge episodes in BED populations | Moderate, not shift-specific | Kristeller 2014; Mason 2016 |
| **Appetite awareness training (15-min wait)** | Moderate; mostly pediatric/clinical evidence | Moderate-weak | Boutelle |

**Key insight:** **pre-decided replacement behavior** outperforms real-time self-control. Saved meal default + if-then phrasing beats any in-app coach copy when the user is post-shift cooked.

### 6.5 Post-shift landing flow (12:15-1:30 PM on shift days)

Pre-shift setup (do ONCE, not every shift):

| Item | Why |
|---|---|
| Cook saved post-shift meal BEFORE leaving for work | Decision happens when cognition is fresh |
| Define default add-on (e.g., 1 whey scoop in milk) | Eliminates "what else can I eat" loop |
| Write your own if-then sentence | Self-authored phrasing ~2× adherence vs canned text (Adriaanse) |

Meal templates (Indian lacto-veg, leucine ≥2.5g, ~400-450 kcal, ~30g protein):

| Option | Protein | Leucine | Notes |
|---|---|---|---|
| Greek yogurt 200g + 25g whey + berries | 32g | 2.8g | Easiest |
| Paneer wrap: 100g paneer + 1 ata roti | 28g | 2.0g | Pair with dahi for leucine |
| Tofu bhurji 150g + 1 roti | 24g | 2.5g | Good for cycle variety |
| Liquid backup: 30g whey + 250 mL milk + 1 banana | 33g | 3.5g | Use if too tired to chew |

Landing flow:

| Step | Trigger | App copy (gain-framed, no shame) |
|---|---|---|
| 1 | App opens between 12:15-1:30 PM after shift | "Post-shift landing. Run the script — no optimizing." |
| 2 | If-then confirm | "If I'm home after shift, then I eat my saved meal before opening anything else." [Confirm] |
| 3 | Log saved meal | One-tap from defined default |
| 4 | After meal | "Plate done. 15-min wait timer starts." |
| 5 | If add-on requested | "Choose ONE planned add-on: [defined whey/yogurt/dahi]." Not "anything." |
| 6 | Kitchen closed | "Meal closed. Next: shower → sleep prep." |
| 7 | If slip happened | Defusion + self-compassion: "I'm noticing a shift-driven urge. This is biology, not failure. Log roughly. Next correct action: kitchen closed." |

### 6.6 Anti-patterns — never build these

| Pattern | Why not | Citation |
|---|---|---|
| "X kcal remaining" countdown | Triggers restrictive pathology + what-the-hell binge | Polivy & Herman 1985 |
| Red/yellow/green food scoring | Moralizes food; unfair to Indian veg mixed meals; encourages all-or-nothing | Counter-regulatory eating literature |
| Photo-shaming / body comparison | Increases self-awareness in the binge-trigger way | Heatherton & Baumeister 1991 |
| Public weigh-ins / social accountability | App abandonment for introverts + SSRI users | Lazar 2015 |
| Hard streaks (perfect-day rings) | One bad shift = identity damage = quit | Cross-validated by both AIs + Polivy/Herman cascade |
| "Make up for yesterday" deficit prompts | Encourages restrict-binge cycling | Counter-regulatory eating |
| Snack prohibition lists | Negation plans backfire with strong habits | Adriaanse 2011 |
| Wansink-style hacks as core science | Cornell academic-misconduct findings; many papers retracted | Cornell 2018 statement |

---

## 7. Display hierarchy

### 7.1 Foundational research

- **Pirolli & Card 1999** — information foraging theory: users follow "scent" toward perceived high-value information at low cost
- **Miller 1956** — working memory limit ~7±2 chunks
- **Card serial-position effects** — primary info goes first, recovery/next-action info last; never bury the key signal in the middle
- **Choe et al. 2014** — quantified-self abandonment patterns: too much data + poor interpretation + maintenance burden = abandonment
- **Lazar et al. 2015** — devices abandoned when data not useful, effort too high, or incompatible with identity

### 7.2 Per-screen priority table (cross-validated)

| Screen | PRIMARY (above fold, <2 sec glance) | SECONDARY | TERTIARY (one-tap) | CUT |
|---|---|---|---|---|
| **Today** | Day-type chip + Move Ring + protein density gauge OR caffeine clearance curve (whichever is relevant) | Water, supplements due, environment rule checklist, energy/mood quick-tap | Full nutrient breakdown, raw HC detail | Raw sync timestamps, mineral DV% (unless abnormal), wearable active-kcal trend |
| **Progress** | 7-day weight MA + 28-day rate vs target | Sleep avg, RHR trend, photo strip, protein adherence | Daily weigh-ins, photo timelapse, raw food logs | Daily scale headline; active calories as trend |
| **History** | Selected day type + adherence outcome | Foods, sleep, water, supplements, mood, notes | Raw HC stats, full nutrient table | Uncontextualized red/green failure labels; full mineral DV |
| **Log Entry** | Saved-meal default OR "edit grams"; protein anchor count | Water, mood/energy, notes, supplement-taken toggle | Custom food builder, photo JSON, full micros | Gemini confidence/debug output |
| **Supplements** | Due now + next due + missed safety-relevant item | 7-day adherence by slot, shift vs off schedule | Supplement details, monthly adherence | "Optimization stack" prompts, serotonergic supplement suggestions |
| **Coach** | One decision summary ("Hold / Adjust / Recover") | 3 suggested prompts based on current data + weekly reflection | Full 30-day data context, chat history | Generic motivation, daily unsolicited advice, guilt language |

### 7.3 Watch-out (cross-validated)

**Do NOT make the primary UI a calorie scoreboard.** That pushes restriction, ignores sleep/circadian stress, and underweights vegetarian protein constraints. The primary UI should answer **"What protects the plan today?"** — not "How much did I eat?"

---

## 8. Trends — signal vs noise

### 8.1 The Stanford caveat that runs through everything

**Shcherbina et al. 2017, Stanford** — wearable energy-expenditure error 27% (best device) to 93% (worst). **Never let active kcal drive trend decisions.** Heart rate is reliable; calorie burn is not.

### 8.2 Per-metric trend rules

| Metric | Signal window | Comparison | Best chart | Don't trend when… | Noise to de-emphasize |
|---|---|---|---|---|---|
| **Weight** | 7-day MA, 28-day rate | Rolling 28 vs prior 28 vs -0.5 kg/wk target | Daily faint dots + 7-day line + target band | <14 weigh-ins, major sleep disruption week, illness/travel | High-sodium meals, constipation, hard workouts, low sleep, shift transitions |
| **Food / kcal** | 7-day avg + logging completeness | Shift vs off; week-over-week | Calendar heatmap + weekly bar | <5 logged days/week, obvious missing meals | Restaurant meals, photo-recognition uncertainty |
| **Protein** | 7-day floor adherence + per-kcal density | Shift vs off; meal-anchor count | Weekly bars + daily anchor dots | <5 logged days/week | One low-protein day after shift |
| **Water** | 7-day goal adherence (not daily perfection) | Workdays vs non-workdays | Calendar heatmap | <4 logged days/week | Heavy Amazon shifts, salty meals |
| **Supplements** | 7-day + 28-day adherence by slot | Shift slots vs normal slots | Slot heatmap | Schedule changed midweek | Stock-outs, intentional skips |
| **Sleep** | 7-day avg duration + 14-day sleep debt | Shift days vs off (matched) | Sleep debt bank + sparkline | Wearable missed naps, <4 sleep records/week | Daytime sleep misclassification, split sleep |
| **RHR** | 7-day avg vs personal 28-day baseline | Current 7-day vs prior 28-day | Sparkline + baseline band | <7 valid nights, illness, device change | Late caffeine, leg day, stress, dehydration |
| **Steps** | 7-day total + consistency | Same day-of-week; shift vs off | Weekly bars + calendar heatmap | Phone/watch not worn | Amazon shift steps ≠ structured training |
| **Active kcal** | **DO NOT trend as decision signal** | Use as rough daily context only | Tiny secondary number only | Almost always for decision-making | Wearable kcal error |
| **Mood/energy** | 7-day median | Shift vs off; sleep debt overlay | Calendar heatmap + sleep overlay | <5 entries/week, med change, life event | One bad post-shift rating |
| **VO2max** | 8-12 week direction only | vs 3-month baseline | Step-line, not daily | <3 values, algorithm changed | Weight change, watch inconsistency |
| **Workouts** | 7-day count + 28-day consistency | Shift vs off; planned vs completed | Calendar dots + weekly count | External app missing data | Soreness skips, post-severe-sleep-debt skips |
| **Lipoma notes** | **No fitness trend** | "New / changed / GP follow-up" only | Separate medical log | Always keep out of fitness dash | Weight-loss interpretation, body-image comparison |
| **Weekly reflections** | 4-week recurring blockers | Current month vs prior | Short text cards by theme | <3 reflections | One unusually bad week |

### 8.3 Auto-annotation — the most important UX rule for trends

**The dangerous false signal:** "weight up after a shift = fat gain."

The app must auto-annotate weight spikes when ANY of these are present:
- Sleep debt high (last 7 days <6h average)
- RHR elevated >baseline
- Sodium intake high (logged)
- Hard workout in last 48h
- Shift transition (last 24h)
- Recent constipation (logged or implied)

Annotation copy: "Likely noise — poor sleep / high RHR / shift transition can distort scale weight. Hold calories steady. Wait 4 days."

Citations: Walker (Hacker's Diet 1991), Bhutani 2017 PMC composition of two-week body weight change.

---

## 9. Engagement psychology

### 9.1 Self-Determination Theory as the engagement backbone

**Deci & Ryan 1985, 2000** — three universal needs:
- **Autonomy** — user chooses framing (normal / shift survival / recovery day)
- **Competence** — user feels effective ("protected the plan" > "perfect day")
- **Relatedness** — for an introvert app: connection to future-self, NOT social sharing

For Vedant specifically, autonomy is the strongest lever: shift constraints are real, and the app's job is to support his choices, not prescribe.

### 9.2 What kills engagement

| Killer | Mechanism | Citation |
|---|---|---|
| **Binary streak failure** | One missed log after brutal shift → "week ruined" | Polivy & Herman 1985 |
| **Hard calorie/ring perfection** | Work schedule makes perfect structurally impossible | Ordóñez 2009 "Goals Gone Wild" |
| **Notification noise** | Post-shift sleep fragile; interruptions actively harmful | Pielot 2014 |
| **Willpower framing** | After night shift, problem is fatigue + cue exposure, not moral weakness | Inzlicht 2014 |
| **Raw data overload** | Many metrics → app feels like homework | Choe 2014, Lazar 2015 |
| **Generic AI cheerleading** | Discordant with SSRI emotional blunting | (Synthesis from Bickmore/Picard relational-agent work) |

### 9.3 Mechanic → mechanism mapping

| Mechanic | Psych mechanism | Evidence | Build for Vedant? |
|---|---|---|---|
| **Streaks** | Loss aversion (Kahneman/Tversky 1979) | Fragile; one miss → collapse | ❌ Avoid. Use coverage % instead |
| **Progress bars** | Goal-gradient effect (Kivetz 2006) | Supported in reward contexts | ✅ For daily completion ("2 of 3 survival actions done") |
| **Identity framing** | Identity-based motivation (Oyserman 2007, Burke & Stets 2003) | Supported, context-sensitive | ✅ "I protect my plan on shift days" > "I'm a disciplined dieter" |
| **Implementation intentions** | If-then cue-action plans (Gollwitzer 1999) | Strong (Adriaanse 2011 meta d=0.51) | ✅✅ Build heavily |
| **WOOP / MCII (mental contrasting)** | Oettingen | Small-to-medium effect; possible publication bias | ✅ Weekly/monthly for recurring obstacles, not daily |
| **JITAI** | Adaptive intervention timing | Strong framework (Klasnja & Hekler 2018; Nahum-Shani 2018) | ✅ At high-risk moments only |
| **Daily self-monitoring** | Self-regulation feedback loop | Strong for weight loss (Burke 2011); burden matters | ✅ Lightweight daily + weekly interpretation |
| **Reflective prompts** | Sensemaking | Strong qualitative (Choe 2014) | ✅ Ask "what made today easier/harder?" not "why did you fail?" |
| **Passive auto-tracking** | Friction reduction | Useful but insufficient alone (Lazar 2015) | ✅ Trigger context, not replace reflection |
| **Public leaderboards** | Social comparison | Causes abandonment for introverts | ❌ Never |
| **Gamified rewards / badges** | Operant conditioning | Often extrinsic-motivation crowding | ❌ Avoid (Deci/Ryan undermining effect) |

### 9.4 The single evidence-supported feature to build

**Shift-Day If-Then Rescue Engine** — a rule editor where Vedant pre-defines 5-8 implementation intentions, and the app fires them as gentle in-app prompts when conditions match.

Combines: implementation intentions (Gollwitzer), context-cued habits (Wood), Fogg ability reduction (B=MAP), JITAI timing (Klasnja/Hekler).

Example rules:
| Trigger | App response |
|---|---|
| Post-shift + low sleep + protein not met | Show saved meal + kitchen-close checklist |
| Caffeine logged too close to sleep | Sleep-protection warning, no shame |
| 2+ missed supplement slots in 7 days | Drift note (not nag) |
| Weight spike + low sleep / high RHR | "Don't adjust calories yet" message |
| Shift day + incomplete food log | Minimum Viable Day logging |

### 9.5 Most common mechanic to NOT build

**Unbroken streaks / perfect-day rings / "close all rings" history.**

Maps directly onto Polivy & Herman counter-regulatory eating + Ordóñez goal-failure cascade. For Vedant specifically: one disrupted shift week → identity damage → quit.

---

## 10. Feature roadmap

### 10.1 P0 — build first (cross-validated by both AIs)

| Feature | Why P0 | Status |
|---|---|---|
| **Shift-Day If-Then Rescue Engine** | Convergent #1 pick — Gemini's "Caffeine Clock + Low-Cognition Template" = ChatGPT's "Minimum Viable Day Mode + Autopilot Timeline" | Not built |
| **Caffeine Clearance Simulator** | SSRI-adjusted PK curve; Gemini's single highest-leverage feature given CYP1A2 + 2 PM sleep | Not built |
| **Sleep debt tracker (14-day banking, shift-vs-off matched)** | Both AIs flagged | Not built |
| **Protein floor + leucine threshold per-meal** | Critical for vegetarian fat loss / muscle preservation | Foods.json has nutrients; tracker needs leucine surface |
| **Coverage % (not streaks)** | "5 of last 7 shift landings protected" | Not built |
| **Implementation intentions rule editor** | Highest-evidence single mechanic (Adriaanse d=0.51) | Not built |
| **Weight-trend noise auto-annotation** | Prevents what-the-hell after water-weight bounce | Not built |
| **Caffeine cutoff JITAI alert** | Only when triggered; fluoxetine half-life context | Not built |
| **Post-shift overeating intercept (saved meal landing flow)** | ChatGPT's full intercept design | Not built |
| **Sleep-Sovereign Notification Gate** | Single most important policy | Spec only |

### 10.2 P1 — next month

| Feature | Why P1 |
|---|---|
| **Photoperiod / 10k-lux light reminder** for Calgary winter (after light box purchased) | Calgary 51°N + South Asian skin |
| **Waist-circumference monthly tracking** | South Asian phenotype — better signal than BMI |
| **MCTQShift chronotype profile** (one-time) | Personalizes shift tolerance |
| **Environment rules checklist** (3-5 max) | Zero-willpower compliance |
| **Body Battery x caloric buffer JITAI** | If Body Battery <20 + low protein → surface protein-anchor card |
| **Off-day transition planner** | Shift→day-shift transition is brutal Thursday |
| **Muscle Retention Risk Score** | Composite of protein adherence + workout freq + sleep + rate of loss |
| **Supplement Drift Detector** | Pattern alert (not single miss) |

### 10.3 P2 — later

| Feature | Why P2 |
|---|---|
| High-risk day predictor (auto-activates MVDM) | Promising but risk of feeling "creepy" |
| Habit timeline extended for shift workers | Lally 2010 needs adaptation |
| Photo time-lapse (uses existing camera + ghost data) | Nice-to-have visual motivation |

### 10.4 Never build (cross-validated NO list)

- ❌ Hard streaks
- ❌ Calorie countdown / "kcal remaining"
- ❌ Red/yellow/green food scoring
- ❌ Photo-shaming
- ❌ Social comparison / leaderboards / public weigh-ins
- ❌ "Make up for yesterday" deficit prompts
- ❌ Snack prohibition lists
- ❌ Wansink-cited micro-hacks (academic misconduct)
- ❌ AI prescriptive meal planning
- ❌ Calorie/macro auto-optimizer
- ❌ Daily scheduled hydration/supplement reminders (notification noise)
- ❌ Lipoma anatomical body map (user choice)
- ❌ Workout programming features (external app handles)
- ❌ Gamified badges / rewards
- ❌ Generic "you got this!" cheerleader copy (SSRI blunting + introvert)

---

## 11. Vedant-specific physiology + context notes

### 11.1 Calgary 51°N photoperiod

- **October-March:** essentially zero UVB-effective sun. Vitamin D synthesis ≈ 0
- Sun angle too low even on clear days
- Snow cover increases reflected light → useful for circadian entrainment after waking if outdoors during daylight
- His 9:30 PM wake = fully dark in winter → outdoors won't entrain. Must use indoor bright light or light box.

### 11.2 South Asian BMI threshold

| Threshold | European/WHO | South Asian (Misra & Khurana 2008; WHO 2004) |
|---|---|---|
| Overweight | ≥25 kg/m² | **≥23 kg/m²** |
| Obese | ≥30 kg/m² | **≥25 kg/m²** |

**For Vedant at 5'6" (167cm):**
- BMI 23 (healthy upper bound) = **64 kg**
- BMI 25 (obese threshold) = **70 kg**
- BMI 28 (current) = equivalent metabolic risk to a European at BMI ~30-31

Implications:
- Original "goal 70 kg" is at the obesity threshold by South Asian standards
- **Healthier endpoint: 64-67 kg** — discuss with GP
- **Track waist circumference monthly:** goal <85 cm; high risk >90 cm
- **INTERHEART 2004 (Yusuf, Lancet)** — waist-hip ratio outperforms BMI in South Asians for MI risk prediction
- South Asians carry 3-5% higher body fat at equivalent BMI (Razak 2007)
- **TOFI phenotype** ("thin outside, fat inside") risk — visceral adiposity at lower outward BMI

### 11.3 Iodine in Indian lacto-veg

- **Pearce 2007** — vegetarians who swap iodized table salt for "natural" salts (Himalayan/sea) at high risk for deficiency
- Indian dairy: variable iodine (depends on cow feed)
- Canadian table salt: iodized by federal regulation since 1949
- **Action:** check kitchen salt label
  - If iodized: probably fine
  - If Himalayan/sea: switch one daily cooking meal to iodized OR add 150 µg/day via multi
- **Test:** urinary iodine spot test OR TSH+free T4 on annual labs
- Wolff-Chaikoff effect risk if blindly supplementing high-dose iodine

### 11.4 Fluoxetine — full interaction map

| System | Interaction | Action |
|---|---|---|
| **CYP2D6** (primary), CYP1A2 (weak/inconsistent) | ⚠️ **Earlier "fluoxetine doubles caffeine half-life" claim was wrong.** That's the **fluvoxamine** effect (Jeppesen 1996, Culm-Merdek 2005). Fluoxetine's primary CYP target is 2D6; its CYP1A2 effect is weak and inconsistent. Caffeine cutoff is still prudent (track your own sensitivity), but don't market it as scientifically required doubling. | Conservative cutoff ~2-4 AM on shift days; calibrate to personal sleep-latency response, not pharmacokinetics |
| **Serotonergic supplements** | Permanent NO: ashwagandha, St. John's Wort, 5-HTP, SAMe, tryptophan | Banned from supplement DB |
| **Sodium** | SIADH/hyponatremia risk | Electrolytes (not plain water bolus) post-shift |
| **Bone density (long-term SSRI)** | Diem 2007, Haney 2007 — higher fracture risk + lower bone density. Clinical meaningfulness in 28M unclear | DEXA scan worth discussion at 5+ year mark? (Pending Q4 research) |
| **Thyroid** | Possible TSH/T4 drift over years | Annual TSH + free T4 on labs |
| **Sexual function / PSSD** | Real but variable. Discuss with prescriber at annual review | Not app's territory |
| **Emotional blunting** | 46% of SSRI users report narrowed affect | App copy stays neutral, utilitarian — never "you got this!" |
| **Discontinuation** | Long half-life (parent 4-6 days, norfluoxetine 7-15 days) makes Vedant's taper easier than sertraline/paroxetine | When and if relevant — separate conversation |

### 11.5 Caffeine math — corrected after Q4 finding

**Corrected:** The "fluoxetine doubles caffeine half-life via CYP1A2" claim is wrong — that's fluvoxamine. Fluoxetine's CYP1A2 effect is weak/inconsistent.

Normal caffeine half-life: 5-6 hours. **On fluoxetine: likely similar to normal**, with modest individual variability.

For sleep onset at 2 PM, normal pharmacokinetics:
- <25% remaining at sleep = 2 half-lives = 10-12h prior cutoff = 2-4 AM
- <50% remaining = 1 half-life = 5-6h prior cutoff = 8-9 AM
- Many people are caffeine-sensitive enough that <50% still impacts sleep latency (Drake 2013)

**Practical cutoff: 4 AM (conservative) on shift days, noon on off days.** Earlier is better; calibrate based on your own sleep-latency tracking, not pharmacokinetics theory.

**Bigger point:** the relevant variable isn't "is fluoxetine doubling clearance?" — it's **your own subjective response and sleep latency**. Track Garmin sleep latency on days with caffeine at different times; the personal data will be far more accurate than any pharmacology rule.

If anxiety or tremor is present, that's also a signal to cut back regardless of half-life math.

### 11.6 Lipomas — minimal scope in app

- Multiple lipomas in young adult → rule out Familial Multiple Lipomatosis (autosomal dominant), Dercum's Disease (painful + fatigue), Madelung's (symmetric, alcohol-associated)
- **Weight loss does NOT shrink lipomas** ([Mayo Clinic](https://www.mayoclinic.org/diseases-conditions/lipoma/diagnosis-treatment/drc-20374474); StatPearls 2024)
- App role: lipoma note text field for GP visit prep. **No anatomical body map** (user choice). No fitness-dashboard surfacing. Keep medical context separate from fitness metrics.

### 11.7 Vegetarian protein density realities

Leucine per typical serving (per Witard, Phillips, van Loon):

| Source | Leucine | MPS-threshold (≥2.5g)? |
|---|---|---|
| Whey isolate 30g | ~3.0g | ✅ |
| Soya chunks 50g dry | ~2.5g | ✅ borderline |
| Paneer 100g | ~1.7g | ✗ subthreshold |
| Greek yogurt 200g | ~1.6g | ✗ subthreshold |
| Tofu 100g | ~1.0g | ✗ way below |
| Dahi 250g | ~1.0g | ✗ way below |
| Milk 250mL | ~0.7g | ✗ way below |
| Lentils 100g cooked | ~0.7g | ✗ way below |

**Implication:** most Indian lacto-veg meals undershoot leucine threshold. Fix:
- Anchor each meal with a high-leucine source (whey scoop, soya chunks, paneer)
- Stack two veg proteins (legumes + dairy together raises via complementation)
- Add a per-meal **leucine display** in the protein density tracker — flag meals <1.5g as "MPS subthreshold"

---

## 12. Master citation list

Organized by domain. All cross-validated against PubMed where possible.

### Sleep + Circadian
- Akerstedt T et al. 1998. *Subjective and objective sleep quality* — day-sleep ~30% lower quality
- Akerstedt T et al. 2002 — sleep inertia + wake timing
- Boivin DB et al. 2012 — circadian midpoint + bathroom waking
- [Brzezinski A et al. 2005 *Sleep Med Rev*](https://pubmed.ncbi.nlm.nih.gov/15649737/) — melatonin dose-response plateaus at 0.3-1mg
- Burgess HJ et al. 2010, *J Pineal Res* — melatonin PRC
- [Crowley SJ & Eastman CI 2003 *J Biol Rhythms*](https://pubmed.ncbi.nlm.nih.gov/14667152/) — bright light + dark + sunglasses for night shift
- [Eastman CI & Burgess HJ 2009 *Sleep Med Rev*](https://pubmed.ncbi.nlm.nih.gov/12531129/) — compromise phase position for rotating shifts
- Hagai Or H et al. 2019 — thermoregulation + sleep
- Hu RF et al. 2020 — ICU eye masks + earplugs
- [Juda M, Vetter C, Roenneberg T 2013 *J Biol Rhythms*](https://pubmed.ncbi.nlm.nih.gov/23606612/) — MCTQShift
- [Nedeltcheva A 2010 *Ann Intern Med*](https://www.acpjournals.org/doi/10.7326/0003-4819-153-7-201010050-00006) — sleep + fat loss crossover trial (55% less fat lost on 5.5h sleep)
- Pielot M et al. 2014, MobileHCI — notification cost
- Sallinen M et al. 2003 — prophylactic nap
- Stanchina ML et al. 2005 — white noise in ICU
- [Trauer JM et al. 2015 *Ann Intern Med*](https://pubmed.ncbi.nlm.nih.gov/26054060/) — CBT-I meta-analysis

### Nutrition / supplements / metabolism
- Adams CE & Leary MR 2007 — self-compassion + restrictive eating
- Aloia JF 2008 — vitamin D dose by skin pigmentation
- Bandín C et al. 2015 — meal timing + metabolism
- Boswell RG & Kober H — food craving meta r≈0.33
- Boutelle KN — appetite awareness training
- Brantsæter AL et al. 2013 *J Nutr* — vegan/veg iodine deficiency
- Cienfuegos S et al. 2022 — TRE general
- Crispim CA et al. 2011 — last meal before sleep
- Diem SJ 2007 — SSRI + bone density
- Fava M et al. 2000 — fluoxetine + weight long-term
- Forman EM et al. 2007 *Behav Modif* — ACT vs control for food cravings (d=0.7-0.9)
- Garaulet M et al. 2013 — meal timing + weight loss
- Garthe I et al. 2011 — 0.7%/wk vs 1.4%/wk loss + lean mass
- [Heaney RP 2003](https://academic.oup.com/ajcn/article/77/1/204/4689629) — vitamin D dose-response
- Helms ER, Aragon AA, Fitschen PJ 2014 — protein in deficit
- [Holick MF, Endocrine Society 2011](https://academic.oup.com/jcem/article/96/7/1911/2833671) — vitamin D guidelines
- Jacob S & Spinler SA 2006 *Ann Pharmacother* — SSRI + hyponatremia
- [Kious BM, Kondo DG, Renshaw PF 2019 *Nutrients*](https://pubmed.ncbi.nlm.nih.gov/30866536/) — creatine + depression review
- [Liao Y et al. 2019 *Transl Psychiatry*](https://pubmed.ncbi.nlm.nih.gov/31383846/) — EPA-forward omega-3 + depression meta
- [Longland TM et al. 2016 *AJCN*](https://pubmed.ncbi.nlm.nih.gov/26817506/) — high protein in deficit RCT (1.2g/kg vs 2.4g/kg)
- [Lyoo IK et al. 2012 *Am J Psychiatry*](https://pubmed.ncbi.nlm.nih.gov/22864465/) — creatine + escitalopram RCT
- Manoogian ENC & Panda S 2017 — TRE
- [Michelson D 1999](https://pubmed.ncbi.nlm.nih.gov/10450256/) — fluoxetine weight 1-year trial
- Mischoulon D — ICEPC consensus 2019 — 1-2g EPA/day for unipolar depression
- [Misra A & Khurana L 2008 *J Clin Endocrinol Metab*](https://pubmed.ncbi.nlm.nih.gov/18840641/) — South Asian BMI cutoffs
- Mithal A et al. 2009 *Osteoporos Int* — Indian vitamin D deficiency
- Mocking RJT et al. 2016 *Transl Psychiatry* — EPA + depression meta
- Pawlak R et al. 2014 — B12 in vegetarians
- Pearce EN et al. 2007 *Thyroid* — vegetarian iodine deficiency
- Phillips SM & van Loon LJC 2011, *J Sports Sci* — protein dose-response
- Razak F et al. 2007 *Circulation* — South Asian body fat at equivalent BMI
- Roitman S et al. 2007 *Bipolar Disord* — creatine in depression
- [Scheer FAJL et al. 2009 *PNAS*](https://www.pnas.org/doi/10.1073/pnas.0808180106) — circadian misalignment + metabolism
- [Spiegel K et al. 2004 *Ann Intern Med*](https://pubmed.ncbi.nlm.nih.gov/15583226/) — sleep restriction + leptin/ghrelin
- St-Onge MP et al. — sleep loss + brain food reward
- Sussman N et al. 2003 — SSRI weight effects
- Taheri S et al. 2004 *PLoS Med* — habitual short sleep + appetite hormones
- WHO Expert Consultation 2004 — Asian BMI cutoffs
- [Witard OC et al. 2014 *AJCN*](https://pubmed.ncbi.nlm.nih.gov/24257722/) — leucine threshold for MPS
- Yusuf S et al. 2004 *Lancet* — INTERHEART
- [Mayo Clinic — Lipoma](https://www.mayoclinic.org/diseases-conditions/lipoma/diagnosis-treatment/drc-20374474)

### Behavioral / engagement psychology
- Adamczyk PD & Bailey BP 2004 — interruption recovery time
- [Adriaanse MA et al. 2011 *Appetite*](https://pubmed.ncbi.nlm.nih.gov/20851732/) — implementation intentions meta-analysis (d=0.51)
- Adriaanse MA — "what not to eat" ironic effects
- Bandura A — self-efficacy (referenced indirectly)
- Bickmore TW & Picard RW 2005 *TOCHI* — relational agents + trust
- Burke LE et al. 2011 — self-monitoring + weight loss
- Burke PJ & Stets JE 2003 — role-identity theory
- Choe EK et al. 2014, CHI — quantified-self pitfalls
- Deci EL & Ryan RM 1985, 2000 — Self-Determination Theory
- Eyal Peer (& Loewenstein) — broken-seal streak effects
- Fogg BJ — Behavior Model (B=MAP)
- Forman EM et al. 2007 — ACT for cravings
- [Gollwitzer PM 1999 *Am Psychol*](https://kops.uni-konstanz.de/bitstreams/14cc2a36-5f01-4dc1-b9ca-f2d0ca0c8930/download) — implementation intentions
- [Heatherton TF & Baumeister RF 1991](https://pubmed.ncbi.nlm.nih.gov/1891520/) — binge eating as escape from self
- Inzlicht M et al. 2014 — refuting ego depletion
- Kahneman D & Tversky A 1979 *Econometrica* — prospect theory / loss aversion
- Killgore WDS 2010 — sleep deprivation cognition reviews
- Kivetz R et al. 2006 — goal-gradient effect
- Klasnja P & Hekler EB 2018 — JITAI MRT design
- Kristeller JL et al. 2014 — MB-EAT for binge eating
- Lally P et al. 2010 — habit formation 66-day median
- [Lazar A, Koehler C, Tanenbaum J 2015 *UbiComp*](https://amandalazar.net/papers/2015_p635-lazar.pdf) — why we abandon smart devices
- Mark G et al. 2008 — interrupted work stress
- Mason AE et al. 2016 — MB-EAT weight loss
- Mehrotra A & Musolesi M 2017 — context-aware notifications
- Miller GA 1956 *Psychol Rev* — magical number seven
- Mischel W — delay of gratification (referenced for self-regulation context)
- Nahum-Shani I et al. 2018 *Ann Behav Med* — JITAI design framework
- Neff KD & Germer CK 2013 — self-compassion + mindful self-compassion
- Oettingen G — mental contrasting / WOOP
- Ordóñez LD et al. 2009 HBS WP — "Goals Gone Wild"
- Oyserman D, Fryberg SA, Yoder N 2007 *J Pers Soc Psychol* — identity-based motivation
- Patel MS et al. 2015 *JAMA* — wearable adherence
- Pielot M 2014 — notification volume + emotion
- Pielot M 2018 — notification design
- Pirolli P & Card S 1999 — information foraging theory
- Polivy J & Herman CP 1985 — counter-regulatory eating
- Pousman Z & Stasko J 2006 — ambient information systems taxonomy
- Rothman AJ & Salovey P 1997 *Psychol Bull* — gain vs loss message framing
- Schachter S 1971 — external eating cues
- Stets JE & Burke PJ 2003 — role-identity theory
- Trope Y & Liberman N — construal level theory (referenced)
- Wansink B — DISCREDITED (Cornell 2018 misconduct finding); use Schachter cue-reactivity instead
- Wood W et al. — context-cued habits / habit automaticity

### Other / measurement
- Bhutani S et al. 2017 *Curr Obes Rep* — composition of two-week body weight change
- Bourdillon N et al. 2017 — within-day HRV variability (pending Q2)
- Plews DJ et al. — HRV trends (pending Q2)
- [Shcherbina A et al. 2017 *Stanford*](https://med.stanford.edu/news/all-news/2017/05/fitness-trackers-accurately-measure-heart-rate-but-not-calories-burned.html) — wearable energy expenditure error 27-93%
- Walker JF (Hacker's Diet) 1991 — moving-average weight tracking

---

## 13. Pending research

**Status: RESOLVED.** All Q1-Q5 responses landed from both Gemini and ChatGPT. Cross-validated synthesis is in §15. Foundation is now considered complete.

---

## 14. Living-document conventions

- Update this file when new research lands or when user constraints change
- Every feature in the app should be traceable to a section here
- When a feature is built, link the code/PR/commit back from the relevant §10 row
- Anti-patterns in §10.4 are binding. Don't ship anything that violates them.
- Citations: include PubMed/DOI links where available; minimum researcher + year for everything
- When AIs disagree, prefer the citation-grounded answer; flag the disagreement in the relevant section
- User overrides (e.g., "no anatomical lipoma map," "drop ashwagandha") are binding even if research supports the opposite — note them as binding constraints, not gaps

---

**End of foundation.**

---

## 15. Final research batch — Q1-Q5 cross-validated synthesis

Both Gemini-in-Studio and ChatGPT answered the final batch independently. Convergent picks below; disagreements flagged.

### 15.1 Time-restricted eating (TRE) for shift workers

**Convergent verdict: implement TRE as a meal-timing guardrail, NOT as a weight-loss engine.**

**Evidence:**
- **Liu et al. 2022, NEJM** ([PMID 35443107](https://pubmed.ncbi.nlm.nih.gov/35443107/)) — 12-month RCT: 8h TRE + calorie restriction was NOT superior to calorie restriction alone for weight, body fat, or metabolic risk. **TRE's "magic" is mostly the calorie restriction it produces.**
- **Manoogian & Panda Healthy Heroes 2022** ([PMC9536325](https://pmc.ncbi.nlm.nih.gov/articles/PMC9536325/)) — 10h TRE in 24h firefighter shift workers: feasible, safe, improved QoL + VLDL particle size; HbA1c/BP benefits concentrated in participants with abnormal baseline markers.
- **Scheer 2009 PNAS** ([PMID 19255424](https://pubmed.ncbi.nlm.nih.gov/19255424/)) — circadian misalignment worsens leptin/glucose/insulin regulation.
- **Chellappa 2021** — daytime eating during simulated night work prevented internal circadian misalignment of glucose rhythms.
- **Crispim 2011** ([PMC3227713](https://pmc.ncbi.nlm.nih.gov/articles/PMC3227713/)) — food intake near sleep negatively associated with sleep quality.
- **Garaulet 2013** — late main-meal timing predicted slower weight loss even with matched energy/expenditure/sleep.

**Disagreement flagged:**
- Gemini recommended shift-day window **1:00 AM – 11:00 AM** (during shift)
- ChatGPT recommended shift-day window **9:45 PM – 7:45 AM** (10h core starting from pre-shift workout meal)

**Reconciliation:** ChatGPT's window is more physiologically defensible (front-loads calories into the awake/active block, last meal ~3h before sleep). Gemini's is more "Amazon-shift compatible" but pushes the eating window late into your shift. **Recommendation:** use ChatGPT's window as default, but allow an optional small landing meal at 12:15-12:45 PM if hungry post-shift (saved-meal default applies).

**Meal-timing rule table for the app:**

| Day type | Eating window | Last meal | Notes |
|---|---|---|---|
| **Shift day (ideal)** | 9:45 PM – 7:45 AM | 7:45 AM (mid-shift) | Closed by post-shift home time |
| **Shift day (realistic)** | 9:45 PM – 7:45 AM + small planned 12:15-12:45 PM | 12:45 PM | Saved meal only, no kitchen-search mode |
| **Off day** | 10 AM – 8 PM (or 11 AM – 9 PM) | 8 PM | Standard daytime |
| **Transition day** | No strict TRE | Variable | Prioritize protein floor + no post-midnight grazing |

**Watch out (Indian veg specific):** Lentils/beans are high-fiber. Eating heavy legumes at 11 AM right before 2 PM sleep → gastric distress + bloating in biological afternoon. Late-shift meal should be lower-fiber protein (whey shake, paneer, dahi) not dal-heavy plate.

**Anti-pattern:** Don't show TRE as red/green fasting score. Show as "eating window quality" soft metric.

---

### 15.2 HRV / Garmin Body Battery as JITAI input

**Convergent verdict: Body Battery is ONE input in stacked rules, NEVER the sole trigger. Use personal baseline only, not generic norms.**

**Evidence:**
- **Plews et al. 2013** ([PMID 23852425](https://pubmed.ncbi.nlm.nih.gov/23852425/)) — HRV valid as a within-person trend marker for training adaptation; single-point readings noisy.
- **Bourdillon 2017** — within-day HRV variability is high; one reading isn't a behavioral oracle.
- **Kemp et al. 2010** ([PMID 20138254](https://pubmed.ncbi.nlm.nih.gov/20138254/)) — depression is associated with lower HRV; SSRIs effects on HRV are mixed (less clearly harmful than TCAs).
- **Garmin Body Battery** — proprietary composite of HRV + stress + sleep + activity. Not independently validated as a "readiness" score in peer-reviewed RCTs.
- **2025 consumer-wearable validation study** ([PMC12367097](https://pmc.ncbi.nlm.nih.gov/articles/PMC12367097/)) — agreement on nocturnal RHR/HRV varies; Oura/Whoop generally better than Garmin Fenix/Polar in that sample.

**Key clinical caution (Gemini's catch):** SSRIs **may suppress HRV** through reduced parasympathetic tone. If true for fluoxetine specifically, Body Battery will be artificially depressed regardless of actual recovery → using BB <20 as automatic trigger would **shame you on every shift day**, triggering counter-regulatory eating.

**Rule for the app:**

| Trigger condition | Action |
|---|---|
| Body Battery <20 alone | In-app context only ("Low recovery context"), NO push |
| BB <20 + shift day + sleep <6.5h | Surface Shift-Day Rescue card |
| BB <20 + sleep window | Silent annotation only; never push |
| BB <20 + low protein day | In-app card, gain-framed |
| Build a personal threshold over 8-12 weeks | Track whether your own BB <X% predicts your overeating/logging misses |

**Display language:** "Low recovery context" — NOT "you are depleted" or "rest day required."

**Anti-pattern:** Do NOT make Body Battery the primary fatigue signal. **Use 7-day RHR trend** (Gemini's call — has stronger reliability + less SSRI distortion).

---

### 15.3 Habit formation in chaotic schedules + identity-based change

**Convergent verdict: count EXPOSURES, not calendar days. Use identity framing scoped to action ("I protect my plan on shift days"), not character ("I'm a fitness guy").**

**Evidence:**
- **Lally et al. 2010** ([Wiley](https://onlinelibrary.wiley.com/doi/full/10.1002/ejsp.674)) — median 66 days to automaticity for **daily** actions. Range: **18-254 days**. If cue happens 2-4×/week, your post-shift landing routine likely needs **30-60 successful exposures**, not 66 calendar days.
- **Wood, Quinn & Kashy 2002** ([USC Dornsife](https://dornsife.usc.edu/wendy-wood/wp-content/uploads/sites/183/2023/10/Wood.Quinn_.Kashy_.2002_Habits_in_everyday_life.pdf)) — habits depend on repeated behavior in stable contexts. "Home after Amazon shift" is a better cue than "12:30 PM."
- **Oyserman 2007** ([PMID 18072851](https://pubmed.ncbi.nlm.nih.gov/18072851/)) — identity-based motivation works when health behaviors feel identity-congruent; can backfire when they feel out-group.
- **Patel et al. 2015 JAMA** ([PMID 25569175](https://pubmed.ncbi.nlm.nih.gov/25569175/)) — wearables are facilitators, not drivers, of behavior change.
- **Lazar 2015** ([paper](https://amandalazar.net/papers/2015_p635-lazar.pdf)) — devices abandoned when data is not useful, maintenance burdensome, or no longer fits self-concept.

**Three design principles for 12-month adherence:**

| Principle | App implementation | Why for Vedant |
|---|---|---|
| **Exposure-based habit building** | "Post-shift landing reps: 18 completed" counter | More accurate than streaks for 2-4 shifts/week |
| **Identity as protection, not performance** | "I protect the sleep window after work" framing | Matches shift-work reality; avoids gym-bro identity mismatch |
| **Useful minimum data** | Weekly "Hold / Adjust / Recover" decision card | Prevents abandonment from data overload |

**Anti-pattern:** Don't make the app say "you're someone who logs every day." That identity is brittle under night shifts and breaks the first time Vedant misses 24h. Better identity: **"I run the rescue script when the day is hard."**

**Concrete build:** Replace any streak counter in the app with a **Landing Reps counter** for post-shift routine completion. No streak loss.

---

### 15.4 SSRI long-term safety markers — annual monitoring checklist

**Convergent verdict: symptom-aware annual baseline, not daily medicalized tracking. Most concerns are GP territory, not app territory.**

**Evidence-weighted monitoring table:**

| Marker | Risk basis | Monitoring need | Citation |
|---|---|---|---|
| **Sodium / SIADH** | Incidence 0.5-32% in SSRI users, driven by **older age, female sex, low body weight, diuretics**. Young active male = lower baseline risk but still real if combined with heavy sweating + water overload | Annual CMP if GP agrees; symptom check anytime | [Jacob & Spinler 2006](https://www.ncbi.nlm.nih.gov/books/NBK554406/) |
| **Bone density (BMD)** | Diem 2007 (older women) + Haney 2007 (older men): hip BMD ~3.9% lower, spine ~5.9% lower in SSRI users. Clinical relevance **mostly older/high-risk populations**, not young male | NO routine DEXA at 28. Discuss only if fracture history, hypogonadism, very low D, eating disorder, or steroid use | [Diem 2007 PMID 17592096](https://pubmed.ncbi.nlm.nih.gov/17592096/) |
| **Thyroid (TSH/T4)** | Evidence weak/mixed — some studies show mild SSRI-related TSH drift, others show none. Magnitude likely clinically marginal | Annual TSH ± fT4 if symptomatic, family history, or fatigue unexplained by shifts | [De Carvalho 2009 PMID 19583486](https://pubmed.ncbi.nlm.nih.gov/19583486/) |
| **PSSD (post-SSRI sexual dysfunction)** | **Ben-Sheetrit 2023:** estimated risk **~1 in 216 / 0.46%** in males on serotonergic antidepressants. Real but rare; recognition still imperfect | Monthly private symptom note (libido, erection, orgasm, genital sensation, emotional blunting). Discuss with GP **before** any taper decision | [Ben-Sheetrit 2023 PMID 37085865](https://pubmed.ncbi.nlm.nih.gov/37085865/) |
| **Discontinuation syndrome** | Fluoxetine's long half-life (parent 4-6d, norfluoxetine 7-15d) usually means milder withdrawal than paroxetine/venlafaxine — but **not zero risk** | If/when relevant: GP-guided taper over MONTHS (not weeks). Horowitz & Taylor — hyperbolic taper better tolerated | [RCPsych guidance](https://www.rcpsych.ac.uk/mental-health/treatments-and-wellbeing/stopping-antidepressants) |
| **Mental-health review** | NICE recommends ≥6-month review for ongoing antidepressant treatment — mood, side effects, relapse risks, life/environment factors | Add 6-month GP review reminder in app (no daily mood policing) | [NICE NG222](https://www.nice.org.uk/guidance/ng222/chapter/recommendations) |

**Recommended annual blood panel for Vedant (NOT app-prescribed; bring to GP):**

| Category | Items |
|---|---|
| Basic | CMP (Na, K, creatinine/eGFR, ALT/AST) |
| Metabolic | HbA1c, fasting glucose, lipid panel |
| Thyroid | TSH ± fT4 |
| Nutrient | 25(OH)D, B12 + homocysteine, ferritin |
| Mental health | PHQ-9 / GAD-7 self-rate every 3-6 months |
| Cardiometabolic | Waist circumference monthly (no lab needed) |

**Anti-pattern:** Don't let the app become a medical-anxiety generator. Keep SSRI monitoring in a **private "GP Review" section** in Settings, NEVER on the Today screen.

**Concrete build:** Add a **Fluoxetine GP Review Log** in Settings: sodium symptoms, sexual side effects, emotional blunting, sleep impact, dose changes, annual lab dates.

---

### 15.5 Gap analysis — what we missed before

Both AIs flagged the same three meaningful gaps. All three are in.

**Gap 1 — South Asian visceral fat / TOFI ("Thin Outside, Fat Inside")**

- **Misra 2008** + **PMC8191592** review — South Asians carry higher visceral fat + insulin resistance at lower BMI; "thin-fat" phenotype well-described.
- For Vedant: BMI 28 is not "slightly overweight." It's high-risk territory for visceral adiposity + insulin resistance.
- **Action: weekly waist circumference log. If weight stalls but waist shrinks → you're losing visceral fat. Track A1c + lipids quarterly via GP.**

**Gap 2 — Muscle retention as a paired metric (protein + resistance consistency)**

- **Morton 2018** ([BJSM](https://bjsm.bmj.com/content/52/6/376)) — protein supplementation enhances strength + lean-mass gains with resistance training.
- **Helms 2014** — slower loss rates (≤0.5%/week) and higher protein (≥1.8 g/kg) better preserve lean mass during energy restriction.
- **Phillips 2017** — progressive overload (one more rep/set than last week) is the muscle-retention signal, NOT calories burned.
- **Flahr 2018 review** — physical-activity interventions in shift workers have limited RCT evidence; data suggest exercise improves body comp/fitness/sleep but adherence under shift cycles is the constraint.
- **Action: track workout consistency + protein floor as a pair**. If protein floor missed AND workout missed for 3+ days during deficit → muscle-retention risk up; app should de-prioritize calorie talk and surface protein anchor card.

**Gap 3 — Periodic mental-health treatment review (NICE 6-month)**

- **NICE NG222** — review ongoing antidepressant treatment at least every 6 months: mood, side effects, relapse, life factors.
- Chronic shift work can mimic or worsen mood symptoms — fatigue/anhedonia/sleep complaints overlap with depression resurgence.
- **Action: 6-month review reminder card. Topics: "How is fluoxetine working? Side effects? Sleep? Sexual function? Have you and your GP discussed continuation?"**

**Bonus gap — Amotivational syndrome (Gemini)**

Long-term fluoxetine can produce a "don't care" attitude toward goals (emotional blunting + reduced motivational salience).

**Action:** The Coach should periodically (quarterly?) ask: *"Does this plan still feel like yours, or does it feel like a chore?"* If chore → SSRI may be blunting competence drive (Deci & Ryan). That's a conversation for the GP, not a calorie deficit problem.

---

### 15.6 New build items added to roadmap from Q1-Q5

These go into §10 as P0/P1 additions:

| New item | Priority | Source |
|---|---|---|
| ~~Eating window tracker~~ | **REMOVED PER USER** (2026-05-18). User opted out of TRE/eating-window tracking entirely. Research stands (§15.1 Liu 2022 NEJM, Manoogian 2022) but not building the feature. | Q1 |
| **Waist circumference monthly log** | P0 (was P1, promoted) | Q5 |
| **Landing Reps counter** (post-shift routine completion, replaces streak) | P0 | Q3 |
| **Identity framing in copy** ("I protect my plan on shift days") | P0 | Q3 |
| **Body Battery as ONE vote in stacked-risk JITAI** | P1 | Q2 |
| **Quarterly Health Markers section** in Progress (waist, A1c, lipids, D/B12/ferritin, med review date) | P1 | Q4 + Q5 |
| **Fluoxetine GP Review Log** in Settings | P1 | Q4 |
| **6-month medication review reminder card** | P1 | Q4 |
| **Protein floor + resistance consistency PAIR** as muscle-retention signal | P1 | Q5 |
| **Coach quarterly "does this still feel like yours?" prompt** | P2 | Q5 (Gemini's amotivational catch) |
| **Caffeine cutoff reframed: 4 AM conservative on shift days; track personal sensitivity** | P1 | Q4 correction |

### 15.7 Additional citations from Q1-Q5

Added to §12:
- Liu et al. 2022 NEJM — 12-month TRE+CR RCT
- Manoogian & Panda 2022 Healthy Heroes — 10h TRE shift workers
- Chellappa 2021 — daytime eating + glucose rhythmicity during simulated night work
- Plews et al. 2013 — HRV training adaptation
- Bourdillon 2017 — within-day HRV variability
- Kemp et al. 2010 — depression + antidepressants + HRV
- Wood, Quinn & Kashy 2002 — habits in everyday life
- Diem 2007 — antidepressants + hip bone loss
- Haney 2007 — antidepressants + BMD older men
- Ben-Sheetrit 2023 — PSSD risk estimate
- Morton 2018 BJSM — protein + resistance training meta
- Flahr 2018 — physical activity interventions in shift workers (review)
- Jeppesen 1996 — fluvoxamine-caffeine interaction (NOT fluoxetine)
- Culm-Merdek 2005 — CYP1A2 inhibition + caffeine
- NICE NG222 — Depression adults treatment guideline
- De Carvalho 2009 — SSRI + thyroid function
- Drake 2013 — caffeine effects on sleep

---

## 16. Foundation status: COMPLETE

All research domains researched, cross-validated, and integrated. The app's design decisions now have a citation trail. Build mode is unlocked.

**Single-sentence summary of what Living Life is:**

> A shift-work-aware, SSRI-safe, Indian-lacto-veg fat-loss + habit tracker that protects sleep over completeness, uses pre-decided behavioral routines over willpower, surfaces situational hierarchy over static dashboards, and treats consumer wearable data as context (not truth).

