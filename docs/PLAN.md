# Living Life — Back-to-Fit Plan

**Vedant • 5'6" • starting weight ~75-80 kg (to confirm with scale)**
**Started:** 2026-05-11

> **Scope note:** This app is a **tracker**, not a workout prescriber. The actual workouts are done in **Home Workout No Equipment** (or whatever you choose); Living Life records what happened via Health Connect, your meals, weight, photos, sleep, supplements, and shift-aware energy balance. The shift-work playbook lives in [SHIFT_WORK.md](SHIFT_WORK.md). Supplement timing lives in [SUPPLEMENTS.md](SUPPLEMENTS.md). The "why" behind every number is in [METHODOLOGY.md](METHODOLOGY.md).

---

## 0. Read this first — health and safety

Before doing anything:

1. **Book a GP appointment.** Get baseline blood work (CBC, lipid panel, fasting glucose, HbA1c, liver, thyroid, 25-hydroxyvitamin D, B12, ferritin), blood pressure, and resting heart rate. These give you objective markers to track alongside weight and photos. It also gets you clearance to start higher-intensity exercise.

2. **Talk to your GP about the lipomas.** Lipomas are benign fatty tumors, but they're not strongly linked to body weight in the medical literature, and they generally do **not** shrink with weight loss. If you're developing multiple lipomas — especially painful ones, or new ones appearing rapidly — your GP may refer you to a dermatologist or general surgeon. Conditions worth ruling out include **familial multiple lipomatosis**, **Dercum's disease** (painful lipomas), and **Madelung's disease**. Don't let "I'll just lose weight and they'll go away" delay this conversation.

3. **Listen to your knees, hips, and lower back.** Starting at a higher weight means joints absorb more impact. Don't ramp running too fast.

4. **Get a scale.** Cheap digital ones are fine. Weigh in once a day, first thing in the morning, after the bathroom, before eating or drinking. Same scale, same spot on the floor.

5. **Shift work changes the rules.** You work Amazon night shifts 2-4×/week. Sleep, meal timing, workout timing, supplements — all of it shifts. See [SHIFT_WORK.md](SHIFT_WORK.md).

---

## 1. Goals, in plain terms

**Primary:**
- Lose body fat sustainably (target: ~0.5 kg/week — fast enough to see progress, slow enough to keep muscle)
- Build foundational strength using bodyweight movements (done in your chosen workout app)
- Build aerobic base by walking/running on off-days

**Secondary:**
- Eat without overeating, without obsessing over calories
- Move every day, even if just a little
- Sleep better — especially around shift days

**What you're NOT trying to do:**
- Get shredded in 8 weeks
- Run a marathon by August
- Eliminate the lipomas through diet (see section 0)

A realistic 6-month outcome: 8-12 kg of fat lost, visible muscle definition starting to appear, comfortable running 5K on off-days, established daily habit. A realistic 12-month outcome: at or near a healthy BMI, real strength in pushups/pullups/squats, running 5-10K comfortably.

---

## 2. The workout side — what this app does and doesn't do

**You do the workouts in Home Workout No Equipment** (or a similar app). It has the demos, progression, timers, and routine variety. Living Life is not trying to recreate that.

**What Living Life does instead:**

- Pulls active calories, steps, distance, heart rate, sleep, and workouts from **Health Connect** automatically.
- Tracks the body-comp side: daily weight, photo, food, supplements, sleep, lipoma notes.
- Computes shift-aware energy balance (BMR + active kcal in vs. food kcal out) so you can see your real deficit.
- Holds your supplement schedule, including the shift-day flip (see SUPPLEMENTS.md).
- Gives you a 7-day moving average on weight so day-to-day noise stops messing with your head.

**Workout cadence guidance (apply inside your workout app):**

- **Off-days are your real training days.** Push intensity there — 45-60 min sessions, harder progressions.
- **Shift days = Amazon shift counts as cardio.** A 10-hour shift is ~400-700 active calories. If you train on a shift day, keep it short (30-40 min strength) and do it **before** the shift (around 9:30 PM if your shift starts at 1:20 AM). Working out after a 10-hour shift wrecks the daytime sleep block. See SHIFT_WORK.md.
- **Running:** save longer runs and the harder C25K weeks for off-days. Light walking on shift days only if you have energy for it.
- **Frequency:** 3 real workouts/week is plenty for fat loss + muscle preservation. More frequency doesn't help if it eats into sleep.
- **One rest day a week, non-negotiable.** Easy walk if you want, otherwise full rest.

---

## 3. Nutrition — three rules, no counting

You said upfront you'd burn out tracking every calorie. Good — calorie counting has high adherence costs and you've identified overeating as the issue, not nutrient ignorance. We use rules.

### Rule 1: Water before, protein first

- A glass of water 10-15 minutes before every meal.
- Eat the protein on your plate first, then vegetables, then carbs. This naturally reduces total intake without you "trying."

### Rule 2: One plate, then wait

- Serve one normal-sized plate. Eat it slowly.
- Want seconds? Wait 15 minutes. Drink water. If you're still genuinely hungry, eat a vegetable or small protein snack — not a second helping of the main meal.
- The "wait 15 minutes" rule does most of the work. Hunger is rarely as urgent as it feels in the moment.

### Rule 3: Kitchen closes after dinner

- Decide a "kitchen closes" time — on off days, e.g. 8 PM.
- On shift days, the rule flips: closes ~2 hours before your daytime sleep block (so ~10:30 AM if you sleep at 12:30 PM). See SHIFT_WORK.md for the shift-day meal schedule.

### Protein target

Roughly 1.6-1.8 g protein per kg of bodyweight. At ~78 kg that's **130-140 g/day**. You don't need to weigh it — just make sure every meal has a clear protein source (paneer, dahi, milk, dal/lentils, tofu, whey scoop).

### Calorie targets (sanity check, not obsession)

- **Off day:** ~1,800-2,000 kcal
- **Shift day:** ~2,100-2,400 kcal (Amazon shift = ~500 extra kcal burned)

The app's energy dashboard handles this automatically once Health Connect is feeding it data.

### What to avoid making rules about

- Specific foods being "good" or "bad."
- Cheat days, cheat meals, "earning" food via workouts.
- Anything that turns eating into a moral test.

You will eat too much sometimes. That is fine. The plan resumes at the next meal, not on Monday.

### Building the food database

The app's food list starts empty. You build it organically using **Gemini photo recognition**: snap the food, paste a prompt, paste the JSON back to me, I add it to the repo. Full instructions in [FOOD_RECOGNITION.md](FOOD_RECOGNITION.md). Most repeat meals only need to be tagged once.

---

## 4. What we're tracking and why

| Metric | Frequency | Why |
|---|---|---|
| Body weight | Daily, morning | Trend, not the day-to-day number |
| Physique photo | Daily (custom camera w/ ghost overlay) | The number on the scale lies; photos don't |
| Food | Each meal | Full nutrition profile — macros + vitamins + minerals + % DV |
| Supplements | Daily checkbox | Adherence on D3 / B12 / omega-3 / creatine / whey |
| Health Connect data | Auto-synced | Active kcal, steps, distance, HR, sleep, workouts, hydration, weight |
| Sleep | Daily | Especially critical on the shift-day cycle |
| Lipoma notes | When changes | Bring to GP visits |
| Mood / energy | Daily | Catch patterns — sleep, stress, eating |

**Read the trend, ignore the noise.** Weight swings 1-2 kg day-to-day from water, sodium, carb intake, and bowel content. The seven-day average is what matters. The app shows you a moving average.

**Photos:** the in-app camera shows the previous photo at 30% transparency as a ghost overlay so you can frame the new shot the same way. Same time of day (morning, post-bathroom), same lighting, minimal/tight clothing. Every photo. The 7-day comparison is brutal but honest.

---

## 5. When things go wrong

- **You skipped two days.** Resume tomorrow. Don't "make up" anything. Just do tomorrow.
- **You ate too much at a meal.** Stop eating. Drink water. The next meal is normal. Don't skip it — that's how binges start.
- **Weight went up.** Wait three more days. If the 7-day average is still trending up after two weeks, eat slightly less at dinner and walk 15 extra minutes a day. That's it.
- **A joint hurts.** Take 2-3 days off that movement pattern, swap to a different workout in your app, see your GP if it persists past a week.
- **The shift week was chaos.** Off-day intensity is your reset. A solid 60-min session on Friday undoes a lot of mid-week chaos. See SHIFT_WORK.md.
- **You hate the workout.** Swap it. Movement > nothing > "perfect" workout you'll skip.

---

## 6. The honest part

You've named overeating as a real challenge. That's worth sitting with.

For most people, persistent overeating isn't about willpower — it's about environment, stress, habits, and emotional regulation. The rules in section 3 are designed to remove decision points (kitchen closes, one plate, water first) rather than rely on you saying "no" repeatedly throughout the day.

If, after a few weeks of trying, you find that eating still feels out of control — secretive eating, eating to the point of physical discomfort, eating in response to specific emotions — please consider talking to a doctor, a registered dietitian, or a therapist who works with eating behaviors. There's nothing shameful about that conversation. People who get help with it succeed at far higher rates than people who try to white-knuckle it alone.

You being an introvert and choosing home workouts doesn't mean you have to do every part of this alone. The medical and emotional support side is worth opening up.

---

## 7. First-week checklist

- [ ] Book GP appointment (bring lipoma concern + ask for baseline blood panel)
- [ ] Buy a digital bathroom scale
- [ ] Buy proper running shoes (standard cushioning, not minimalist)
- [ ] Install **Home Workout No Equipment** app for the actual workouts
- [ ] Open Living Life, finish onboarding, paste your GitHub PAT + Claude API key
- [ ] Connect Health Connect — grant all permissions (steps, HR, sleep, workouts, weight, etc.)
- [ ] Mark your **shift days** in Settings → Profile so the energy dashboard + supplement schedule adjust
- [ ] Decide your "kitchen closes" time (off days)
- [ ] Take starting photo (use the in-app camera so it's the reference for future ghost overlays) and log starting weight
- [ ] First workout: anything 20-30 min in Home Workout No Equipment — just to break the seal

Day 1 is the hardest. Day 30 is when this starts to feel like who you are.
