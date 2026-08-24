# FHP Training Templates — Program Blueprints (Study Notes)

Source: Najib's playlist #12 (13 instructional videos for FHP's Excel program templates; #01 & #09 have no subtitles; #12 combat-sports skipped as off-topic). These aren't science videos — they're walkthroughs of how a professional structures sellable hypertrophy programs. **This is the closest thing to a design spec for GymLog v2's built-in programs.** Raw transcripts in [transcripts/](transcripts/).

## The FHP template architecture (the reusable pattern)

Every fixed template shares one engine:

1. **Volume-first workflow** — you don't pick exercises first; you pick **weekly sets per muscle** from built-in recommendation ranges → the template auto-fills each exercise's set count, including scaled-down deload values.
2. **Mesocycle shape: 5 weeks, deload FIRST** — week 1 runs at REDUCED volume as an introduction/unload, weeks 2–5 are identical overloading weeks. (Note the inversion: RP puts the deload LAST; FHP front-loads an easy familiarization week. Both manage fatigue — FHP's version doubles as technique re-learning.)
3. **Rep philosophy**: rough hypertrophy band **6–30 reps**; going below 6 allowed on compounds for strength bias; per-exercise proximity prescribed as RIR *or* RPE.
4. **Direct-set counting rule**: shoulders/triceps/biceps volumes count DIRECT sets only — indirect work from presses/rows is deliberately ignored (simple and conservative).
5. **Category slots**: each day is fixed movement-category slots (e.g., "horizontal push") filled by dropdown; swaps allowed only within category; custom exercises addable.
6. **Meso-end ritual**: review response → recycle (adjust volumes/exercises) or repeat unchanged.

## The four fixed splits — example volume picks (weekly sets)

| Muscle | Full-Body 3-day | Upper/Lower 4-day | UL+Shoulders&Arms 5-day | PPL 6-day |
|---|---|---|---|---|
| Chest | 12 | 14 | 14 | 16 |
| Back | 12 | 12 | 10 | 14 |
| Quads | 12 | 9 | 9 | 12 |
| Glutes+Hams | 9 | 9 | 9 | 9 |
| Side delts | — | — | 3 | 4 |
| Rear delts | — | — | 5 | 8 |
| Triceps (direct) | 9 | 6 | 9 | 6 |
| Biceps (direct) | 12 | 10 | 12 | 10 |
| Calves | 9 | 8 | 8 | 8 |

Patterns worth stealing: back volume DROPS on splits where arms get their own day (arms day includes pulling); PPL pushes chest highest (two dedicated press days); glutes+hams pinned at 9 everywhere; small muscles live in 3–12 direct sets.

Weekly layouts: FB3 = full body ×3 · UL4 = upper/lower ×2 · UL-SA5 = upper/lower/upper/lower + arms&shoulders day · PPL6 = push/pull/legs ×2 (d1&4 chest+shoulders+triceps, d2&5 back+biceps, d3&6 legs) · UUL6 variant = upper×4 + legs×2.

## Program Creator v2 (the blank canvas)

- Any days/week, any exercises/session (dropdowns with search + muscle filter), any length 2–10 weeks.
- Per-exercise optional rep-target + RIR; log actual reps/load per set.
- **Volume Tracker tab**: auto-computes total sets/muscle/week vs chosen target — plan until targets hit. This single feature IS GymLog v2's planned muscle-volume dashboard.
- No automated progression/deload — user-prescribed (an opportunity gap for GymLog: we can automate what FHP leaves manual).

## Design lessons for GymLog v2 (analysis-only, no app changes yet)

| FHP pattern | GymLog implementation idea |
|---|---|
| Pick volume targets before exercises | Onboarding wizard: choose weekly sets/muscle → app builds sessions automatically |
| Week-1-as-intro meso shape | Block builder defaults: week 1 at ~70% volume labeled "آشنایی" |
| Category slots + dropdowns | Program editor with movement-pattern slots; swaps constrained to same category (prevents unbalanced programs) |
| Direct-only counting for arms/delts | Volume dashboard toggle: count indirect or direct-only |
| Manual progression (their weakness) | Our advantage: auto-RIR ramps, reactive deloads, ACWR — automate everything FHP sells as manual spreadsheets |
| Meso review ritual | End-of-block review screen (from periodization notes) |

Combined with earlier notes: RP gives landmarks & signals; FHP-periodization gives levers; **FHP-templates give the UX of packaging it all into ready programs**. The v2 spec is now ~complete across all three dimensions.
