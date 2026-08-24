# AGENTS.md — AI Operating Manual for GymLog v2

READ THIS FIRST if you are an AI agent asked to continue building this project. This file + `docs/knowledge/` contain everything you need. No other context is required.

## KNOWLEDGE LIBRARY ACCESS (fetch this first)

The full scientific library (23 notes, one document) is available as a single raw fetch:

https://raw.githubusercontent.com/najiballahhaqmal568-hub/myboybuildingrepo/main/KNOWLEDGE.md

Per-file versions live under docs/knowledge/ (raw fetch works per file too). If you are reviewing GymLog's coaching logic, safety boundaries, or scientific claims — read KNOWLEDGE.md; it is the evidence base.

## What this project is

**GymLog v2** (`index.html`) — a personal, scientific bodybuilding tracker built for and with **Najiballah Atal** (entrepreneur, Dari/Persian speaker, non-programmer; he decides, you implement end-to-end).

- Single-file app: HTML+CSS+JS all inline in `index.html`. No build step, no backend, no npm.
- UI language: **Dari (Persian), RTL**. Code identifiers in English. **No code comments anywhere.**
- All user data lives in the browser's `localStorage` key `gymlog_v2` on the owner's device. Nothing is transmitted anywhere.
- Live at: `https://najiballahhaqmal568-hub.github.io/myboybuildingrepo/`
- Legacy v1 lives at `gymlog-v1` branch-era file `index.html.bak`-style locally only; v2 auto-migrates old data from localStorage key `gymlog_v1` on first run. Never break that migration.

## Non-negotiable rules

1. **No nutrition/calorie module.** Owner removed it deliberately (2026-08-22). It may return only after the "next chapter" decision — do not re-add it silently.
2. Keep the **single-file architecture** unless the owner approves a change.
3. Preserve **v1 → v2 migration** and backward-compatible history entries.
4. All user-facing strings in Dari. Numbers/Latin OK inside inputs.
5. After ANY change: verify rendering (recipe below) before telling the owner it's done.

## Data model (localStorage `gymlog_v2`)

```json
{
  "version": 2,
  "settings": { "rir": true },
  "meso": { "start": "YYYY-MM-DD", "weeks": 4, "deloadFirst": true },
  "volumeTargets": { "chest":12, "back":12, "quads":9, "hams":9, "delts":8, "biceps":8, "triceps":8, "calves":6, "abs":4 },
  "history": [ { "date":"ISO", "dayId":"push|pull|legs|free", "dayName":"...", "durationMin":n,
                 "volume":kg, "deload":bool, "checkin":{"sore":0-3,"joint":bool},
                 "exercises":[ {"exId","name","sets":[{"w","r","rir"}]} ] } ],
  "prs": { "<exId>": {"w","r","date"} },
  "weights": [ {"date","kg"} ],
  "activeSession": null | {...}
}
```

## Code map (inside index.html)

- `LIB` — exercise library: `{id, n(Dari name), mk(primary muscle key), sec[](indirect muscles @0.5 set each), cls:"H|C|I"(RIR class: heavy-compound/compound/isolation), eq, how(technique cue Dari), vid?(YouTube ID)}`
- `PROGRAM` — PPL split: `[{id,name,ex:[[exId, baseSets],...]}]`
- `MK` / `MKORDER` — muscle keys ↔ Dari labels
- Views: `vHome / vWorkout / vVolume / vMeso / vHistory / vSettings`, dispatched by `render()` via `ui.tab`
- Tabs are deep-linkable: `?tab=volume` or `#tab-volume` (home/workout/volume/meso/history/settings)
- Key systems: mesocycle state (`mesoInfo`, deload = week 1 at ~half sets), weekly volume per muscle incl. indirect counting (`weekSets`), ACWR spike ratio (`acwr`), per-exercise trend within block (`trendsFor`), end-of-meso review wizard (`reviewHTML` steps 1–3), post-workout check-in modal feeding recovery flags, rest timer, PR detection via estimated 1RM.

## The science behind every feature (read on demand)

All distilled research is in `docs/knowledge/` (23 files). Map:

| Feature | Source file |
|---|---|
| Mesocycle structure, RIR-by-category held constant, reactive review | `fhp-program-creation--NOTES.md` |
| Volume landmarks (MEV/MRV), progression levers | `fhp-periodization--NOTES.md`, `fhp-load-management--NOTES.md` |
| Per-muscle exercises/volume/counting rules | `fhp-hypertrophy-mega--NOTES.md`, `fhp-hypertrophy-mega--FUNDAMENTALS-NOTES.md`, `rp-specialization--NOTES.md` |
| Program templates & split volume tables | `fhp-templates--NOTES.md` |
| Recovery monitoring triad, modality verdicts | `fhp-recovery--NOTES.md`, `huberman-galpin-series--ep5-recovery.md` |
| Injury prevention, ACWR | `fhp-injury--NOTES.md` |
| Assessment benchmarks, health metrics | `huberman-galpin-series--ep1-assessment.md`, `galpin-performance--NOTES.md` |
| Strength vs hypertrophy fundamentals | `huberman-galpin-series--ep2-strength-muscle.md`, `fhp-overload-specificity--NOTES.md` |

## Regression tests
Run the suite (iframe loads the app, exercises real flows):
`msedge --headless --dump-dom "https://najiballahhaqmal568-hub.github.io/myboybuildingrepo/test.html?v=N`"` then grep TESTSUMMARY pass=/fail= — 22 tests: parse, home render, midnight-safe local dates, one-action start, RIR visible==saved, refresh survival, save→volume+hash, no raw ISO, migration, import validation, zero console errors.

## Verification recipe (after every edit)

Headless Edge:
```
msedge --headless --disable-gpu --dump-dom "https://najiballahhaqmal568-hub.github.io/myboybuildingrepo/?tab=NAME&v=N"
```
ASCII-safe markers per tab: home=`start-suggested` · workout=`start-free` · volume=`vbar` · meso=`meso-weeks` · history=`empty` · settings=`data-tgt`. All six must pass. (Local `file://` fragments don't work in headless; use query param or live URL.)

## Deployment

GitHub Pages serves `/` from `main` branch root. To ship:
- API route (owner supplies a fresh fine-grained token with Contents RW): GET current file sha → PUT contents/index.html with base64 + sha.
- Or owner uploads manually via web UI.
Pages cache ≈10 min; bust with `?v=N`.

## Roadmap (discussed, not yet built)

- Offline PWA (service worker) — conflicts with single-file rule; needs owner decision
- ACWR per-muscle granularity (currently global)
- Strength-peak overlay (6-mesocycle template — see `fhp-long-term-periodization--NOTES.md`)
- "سلامت" health tab (Galpin metrics: RHR/HRV/sleep/grip/VO₂max) — only after next-chapter decision
- Biceps exercise video ID missing (transcript corrupt); candidate video #245 OO_l75KzO1s

## Owner context

Full profile: owner's local `My Workspace/profile.md` (not in repo). Session log there records every decision since 2026-08-22. When unsure what the owner wants: ask him directly — he decides fast and expects you to build.
