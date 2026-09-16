# Living Life

Living Life is a personal Android-first body-tracking and workout app built as a PWA wrapped with Capacitor.

## What the app does

- Weight and waist tracking
- Front and side progress photos
- Progress charts and body-history views
- Health Connect read data
- Workout scheduling, execution, timers, and history
- Prescribed-vs-actual workout tracking
- Offline-first local storage with GitHub sync

## Repositories

This repository contains the app code. `app/index.html` is the canonical web-layer source.

Personal data lives separately in the private `living-life-data` repository.

Important data paths:

```text
data/log.json
data/photos/
data/workouts/current.json
data/workouts/manifest.json
data/workouts/scheduled/
data/workouts/archive/
data/workouts/completions/
```

## Workout model

Living Life is the display, execution, and history layer. Workout prescriptions are generated externally and delivered as JSON.

- `current.json` = current assignment
- `manifest.json` + `scheduled/` = upcoming workouts
- `archive/` = historical prescriptions
- `completions/` = actual performed workouts

Prescription and execution data stay separate so the app can compare what was planned with what actually happened.

## Main screens

- **Today** — body metrics, activity summary, and today's workout
- **Progress** — body and activity trends
- **Workouts** — upcoming, today, and past workouts
- **History** — body-log history and progress photos
- **Settings** — profile, GitHub data sync, and Health Connect status

## Sync

The app is local-first. Body data syncs to `data/log.json`. Workout completions are cached locally first, then synced to `data/workouts/completions/<workoutId>.json` with SHA-aware updates.

Offline workout edits remain local and sync later.

## Health Connect

Health Connect is currently used for supported read data. Workout write/export is not currently implemented with the installed plugin.

## Development notes

1. Treat `app/index.html` as the source of truth.
2. Keep workout prescriptions separate from completion records.
3. Preserve weight, waist, photos, Progress, History, and Health Connect reads when changing workout features.
4. Do not overwrite unsynced local workout changes with remote data.
5. Re-sync/rebuild the Capacitor Android wrapper after updating the web layer.

## Product direction

Living Life is intentionally focused on **body tracking + workout execution + workout history** rather than food logging, supplements, or an in-app AI coach.
