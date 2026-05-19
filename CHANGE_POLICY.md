# Change Policy — Living Life

**Read this file before editing the codebase. This is binding for any AI agent (Gemini-in-Studio, Claude, ChatGPT) and any future human contributor.**

This file exists because on **2026-05-19** an AI agent overwrote the entire codebase with a 30 KB rewrite that lost ~85% of features (Coach + Supplements screens became empty stubs, native plugin integration deleted, schema-v3 migrations stripped, GP/SSRI medical context scrubbed, vibrant tile styling replaced with editorial b&w). Recovery was possible only because the last good version was pinned on GitHub. We are not relying on that luck again.

## 1. Source-of-truth file paths

| File | Role | Edit it? |
|---|---|---|
| `app/index.html` | **Canonical web layer source** | ✅ **YES — edit here** |
| `android-build/www/index.html` | Synced copy for Capacitor | ❌ Do not edit directly. Will be overwritten on next sync. |
| `android-build/android/app/src/main/assets/public/index.html` | Bundled APK assets | ❌ Do not edit directly. Will be overwritten on next `cap sync` or rebuild. |
| `data/*.json` (in `vedantpatel699/living-life-app` GitHub repo) | Public data tables (foods, supplements) | ✅ Edit via GitHub API push |
| `data/log.json` (in `vedantpatel699/living-life-data` GitHub repo) | Private daily log | ❌ Edit only via the app's `pushData()` flow. Never manually. |

**If you are Gemini-in-Studio:** Android Studio surfaces the bundled `assets/public/` path in its file tree, but that's downstream. Always navigate to `app/index.html` at the project root and edit there. The wrapper paths get overwritten on the next sync.

## 2. Binding sections — do not remove without explicit user approval

These sections exist because of medical safety, research-validated decisions, or explicit user requests. Removing or restructuring them is a breaking change.

Search the codebase for `<!-- LOCK: BINDING SECTION` to find them. As of v3.14:

| Section | Why it's binding |
|---|---|
| **FLUOXETINE GP REVIEW** | Tracks SSRI side effects, dose, sexual function, mood, next appointment. Medical safety. RESEARCH_FOUNDATION §14, §15.4. |
| **QUARTERLY HEALTH MARKERS** | South Asian + SSRI metabolic + thyroid + bone safety markers. RESEARCH_FOUNDATION §11.2, §15.4. |
| **Bio tab (HC Detail screen)** | User's "curious mind" deep-dive request. RESEARCH_FOUNDATION §10.2. |
| **Sleep-Sovereign Notification Gate logic** | Native `ShiftRescueBridge.setSleepWindow` enforcement. Sleep protection outranks tracking completeness. RESEARCH_FOUNDATION §2 Principle A. |
| **`migrateData()` function** | Idempotent schema-version migration. Removing it breaks loading older data. |
| **Native plugin registration in `MainActivity.java`** | `HealthPlugin`, `SleepBridge`, `ShiftRescueBridge` — three `registerPlugin()` lines. Removing them kills Health Connect + notifications. |
| **`writeWeightToHC` + `writeHydrationToHC`** | Two-way HC sync. User explicitly wants weight written back to Health Connect (§Phase 6 chat). |
| **Coverage % display (not streaks)** | Polivy & Herman counter-regulatory eating risk. Streaks are banned. RESEARCH_FOUNDATION §2 Principle D. |
| **No calorie countdowns / red-yellow-green food scoring / photo shaming** | RESEARCH_FOUNDATION §10.4 — anti-pattern list. |

If you need to change one of these, **ask the user first** with a concrete diff. Do not assume.

## 3. Hard rules for AI agents

1. **No destructive rewrites.** If you find yourself doing a full-file `write_file` to "fix syntax," STOP. Read the existing file in chunks, apply surgical edits, verify syntax, and commit.
2. **No structural deletions without checkpointing.** If you remove a feature, first quote the lines you're removing and explain why. If the user is not in the loop, do not delete.
3. **Do not change `state.data` schema fields** without bumping `version` and updating `migrateData()` to handle the old version. Existing user data must remain loadable.
4. **Do not break `entry.photo`** — it's a single string in v3.x. Don't introduce `photoFront`/`photoSide` without a migration that handles existing entries gracefully.
5. **Do not scrub medical context** (GP review, SSRI notes, supplement interaction warnings). Even if the UI looks "cleaner" without them, they exist for safety.
6. **Do not rewrite Today screen from scratch.** It's been iterated on across v3.8 → v3.13. Surgical edits only.
7. **Visual identity:** coral / sky / mint / sun on cream background. Vibrant Google-Fit-style tiles. Do not strip color in pursuit of "minimalism" without explicit user request.
8. **Sync wrapper assets after every change:** copy `app/index.html` → `android-build/www/` AND `android-build/android/app/src/main/assets/public/`. Don't leave them stale.
9. **Push to GitHub frequently** — `vedantpatel699/living-life-app` repo, `data/app/index.html` path. Every meaningful commit. That's our recovery checkpoint.
10. **Verify syntax via `node --check`** on the extracted JS before declaring done.

## 4. Pre-flight checklist before any edit

- [ ] Read `app/index.html` to understand current state
- [ ] Check `RESEARCH_FOUNDATION.md` for binding decisions
- [ ] Look for `<!-- LOCK: BINDING SECTION` comments around the area you're editing
- [ ] If you're touching `state.data`, verify `migrateData()` handles it
- [ ] After editing, syntax-check JS via `node --check`
- [ ] After editing, verify file size hasn't dropped >20% — if it has, you may have truncated; abort
- [ ] Sync to wrapper paths (`www/`, `assets/public/`)
- [ ] Push to GitHub

## 5. If something goes catastrophically wrong

1. **Don't push.** Do not `pushData()` or commit to GitHub if the local file is in a bad state.
2. **Check GitHub.** The last good `index.html` is at `vedantpatel699/living-life-app/app/index.html`. Pull it back via raw URL.
3. **Restore all three paths** from that GitHub version.
4. **Write a postmortem comment** at the top of the next commit message explaining what broke and how to avoid it.

## 6. AI-specific patterns to avoid

Documented from real incidents:

| Pattern | Real incident |
|---|---|
| "I'm doing a full HTML reset to fix a syntax error" | Gemini-Studio 2026-05-19: cost ~85% feature loss |
| "Editing `assets/public/index.html` because that's what Android Studio shows me" | Gemini-Studio 2026-05-18-19: edits stranded, overwritten on next sync |
| "I'll change `entry.photo` to `photoFront`/`photoSide` for symmetry" | Same incident: orphaned all existing user photos |
| "The app feels cluttered, let me strip the colors and tiles" | Same incident: destroyed coral/sky/mint visual identity |
| "Let me remove the GP review section to clean up Settings" | Same incident: scrubbed binding medical-safety content |

## 7. Trusted edit patterns

| Pattern | Notes |
|---|---|
| Use Python via bash heredoc for big multi-section adds | Avoids Edit-tool truncation on the large index.html |
| Use targeted `Edit` for single-line / small-block surgical changes | Verify with `Read` after if uncertain |
| Always end edits with `node --check` syntax verification | Non-negotiable |
| Push to GitHub on every meaningful change | Recovery insurance |

---

**Last reviewed:** 2026-05-19 (post-Gemini-overwrite recovery, v3.14)
**Next review:** When the next AI agent touches the codebase.
