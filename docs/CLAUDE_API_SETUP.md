# Setting up Claude API for the Coach

Five-minute setup. After this, your in-app Coach starts working — daily AI recommendations, weekly reflections, and chat that knows your data.

## What it costs

For your usage (one user, light chat + weekly reflection): **~$1-3 CAD/month**. Pay-as-you-go, no subscription. Anthropic charges per token used. Sonnet 4.6 is roughly $3/million input tokens and $15/million output tokens. Each Coach response is ~2-5k tokens of context + 1-2k output, so each chat is fractions of a cent.

You'll add a payment method up-front, but you control a usage limit (e.g. cap at $10/month) so it can never run away.

---

## Step 1 — Create an Anthropic account

Go to https://console.anthropic.com/

Click **Sign up** (or sign in if you already have one). Use Google or email.

You'll land on the Console dashboard.

---

## Step 2 — Add a payment method

You can't use the API without one, but the bar is low.

1. Click **Settings** (gear icon, top-left or bottom-left)
2. **Billing** → **Add payment method**
3. Add a credit/debit card. Canadian cards work fine.
4. **Set a usage limit** while you're here — under **Plans & billing** → **Limits**, set a **Monthly usage limit** of **$10** (or whatever feels safe). This caps total spend.

You'll also need to **add credits** the first time:
- Console → **Billing** → **Buy credits**
- Buy $5-10 to start. They never expire.

> Why this gates everything: Anthropic's free tier was deprecated for production API use. For a personal app, $5 of credits lasts ~2-3 months easily at typical usage.

---

## Step 3 — Generate an API key

1. From Console, click **Settings → API Keys**
2. **Create Key**
3. Name it `living-life-app` (anything, this is for your reference)
4. Set Workspace: Default
5. Set Permissions: **Default** (full read/write to messages API — you need this)
6. Click **Create Key**
7. **COPY THE KEY NOW.** It starts with `sk-ant-api03-…`. You won't see it again after closing the dialog.

If you lose it, just create a new one and delete the old.

---

## Step 4 — Paste into the app

On your phone or PC, open https://vedantpatel699.github.io/living-life-app/

1. Tap **Settings** in the bottom nav
2. Scroll to **AI COACH (CLAUDE)** section
3. Paste your key into the **Anthropic API key** field
4. Tap **Save Claude key**
5. You'll see "✓ Connected" badge

---

## Step 5 — Test it

1. Go back to the **Today** tab
2. The "TODAY" card should now show **✦ AI COACH** with a personalized recommendation
3. Tap the Coach icon in the bottom-right (or the Coach link if visible on Today)
4. Send a message: "How am I doing this week?" or "Should I rest today?"
5. Coach responds in 3-8 seconds with context-aware advice

If it fails, the error message will tell you why (most common: typo in the key, or out of credits).

---

## Step 6 — Set sensible defaults

In **Console → Settings → Limits**, configure:

- **Monthly spend limit:** $10 (alerts you when reached, you can raise if needed)
- **Rate limit warning email:** Yes
- **Model:** the app uses **Claude Sonnet 4.6** by default — best balance of quality + cost for this use case

---

## What the Coach knows about you

When you ask the Coach anything, the app sends Claude:
- Your profile (height, weight, age, goals)
- Your current phase + week + today's prescribed activity
- Your last 30 days of log entries
- Your last 10 workout sessions
- The hard rules (no aggressive deficits, no medical diagnoses, etc.)

**None of this leaves Anthropic's API** — Anthropic doesn't train on API traffic by default. You can verify this in their data policy at https://www.anthropic.com/legal/commercial-terms.

---

## Privacy & security

- The API key sits in your browser's localStorage on each device you install on. It never goes to GitHub or anywhere else.
- If you lose your phone, **revoke the key** in Console → API Keys → Delete. Generate a new one for your new device.
- Treat the API key like a credit card — if leaked, an attacker could rack up charges (capped by your monthly limit).

---

## Troubleshooting

**"Claude 401: Invalid API key"** → typo, or you deleted the key. Generate a fresh one.

**"Claude 429: Rate limit"** → unusual for personal use. Wait a minute and retry.

**"Claude 400: insufficient credits"** → buy more credits in Console → Billing.

**Coach takes >15 seconds to respond** → Anthropic's API is slow occasionally. Try again. If consistent, switch model in Settings (we default to Sonnet 4.6).

**Want to use a cheaper model?** Open the app's localStorage in browser devtools → `living-life-config-v2` → change `claudeModel` to `claude-haiku-4-5-20251001`. Cheaper, slightly less nuanced.

---

## Cost estimation table

| Usage pattern | ~Monthly tokens | Cost |
|---|---|---|
| Light (3 chat messages/week + 1 weekly reflection) | ~50k input + 5k output | $0.20 |
| Moderate (chat daily, weekly reflection, AI daily rec on Today) | ~250k input + 30k output | $1.20 |
| Heavy (lots of chat + every daily rec is AI) | ~500k input + 60k output | $2.40 |

Your **Monthly limit** in Console is your safety net. Set it once, forget it.

---

## When you're set up

Open the live app: https://vedantpatel699.github.io/living-life-app/

You should see:
- Today screen shows **✦ AI COACH** card with personalized advice
- Coach Chat link visible from Today
- Settings shows "Connected" badge under AI COACH

Now your Coach has context. Ask it things.
