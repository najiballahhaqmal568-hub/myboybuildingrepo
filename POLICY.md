# POLICY.md — Product Policy & Protocol Decisions

Single source of truth for which protocol the GymLog v2 engine implements when knowledge sources disagree. Alternatives are labeled, not deleted — they live in `docs/knowledge/` as options. Last reviewed: 2026-08-24 (after external scientific audit).

## Precedence rule (always applies)

**Safety > constraints (time/equipment/pain-free) > individual response > defaults.**
If any safety condition triggers, growth rules yield automatically.

## Chosen protocols (engine behavior)

| Topic | CHOSEN for engine | Labeled alternative (docs only) | Rationale |
|---|---|---|---|
| RIR across mesocycle | Constant by category: heavy-compound 2–3, compound 1–2, isolation 0–1 | RP weekly ramp 3→0 | FHP program-creation spec; simpler, fatigue-predictable. Ramp available as future "block style" option |
| Deload placement | Front-loaded intro week (~60–65% volume) + reactive 7-day deload flag (2 negative check-ins) | RP end-of-block deload | FHP templates; doubles as technique re-entry. Both manage fatigue |
| Progression | Emergent from logged performance (double-progression suggestion: beat reps, then +5% load). No calendar-forced jumps | Weekly +1 rep/+5% schedules | FHP ep7/ep8; audit: scheduled overload ignores noise |
| Volume counting | Direct sets + 0.5 indirect (press→triceps, back→biceps) | Direct-only view | FHP fundamentals rules; single accounting method engine-wide |
| Volume bands | Start 10–20 sets/muscle/wk; autotune clamps 4–26 | MRV 18–30, 52-set outliers | Audit: individual response governs; outliers are not defaults |
| Exercise changes | Swap only after plateau (3 flat sessions) or pain; compounds kept ≥3 mesos | Weekly rotation | FHP ep42 study: consistency out-grows rotation |
| ACWR | **Load-change indicator only** — never an injury predictor | Team-sport injury-risk framing | Audit + methodological critiques (PMID 32572824, 32502973) |
| End-of-meso review | Reactive wizard: hold / volume ±1–2 / pain→swap; tired → −10% all targets | Proactive annual plans | FHP ep8; audit §3 |

## Safety boundaries (engine scope lock)

1. **Population**: healthy adults training for fitness/hypertrophy. No diagnosis, treatment, or rehabilitation guidance.
2. **Red-flag symptoms** (chest pain, unusual dyspnea, dizziness/syncope, palpitations, dark urine) → app shows seek-care guidance; never auto-adjusts sets around them.
3. **BFR, supplement dosing, blood-work interpretation, concussion protocols**: education in `docs/knowledge/` only — **never engine recommendations**. Require qualified-professional screening (see audit sources: AIS BFR guide, NIH ODS sheets, CDC TBI signs).
4. Pain rule always overrides growth rule: pain-free ROM and exercise substitution take precedence.

## Uncertainty labeling

- `autoTune` changes carry `conf:"low"` and require ≥4 sessions of data per muscle with |Δ|>2% e1RM before classifying trend.
- End-of-meso review shows the evidence line ("از لاگ: e1RM X ← Y") per muscle; missing data defaults to "ثابت" and says so.
- Suggestions are small, reversible, and re-reviewed next block.

## Known open items

- Per-muscle soreness input (current check-in is session-global) — future option
- Direct/fractional volume dual view — future option
- Screening questionnaire depth (currently first-run scope notice) — revisit if product chapter chosen

## 2026-08-24 UX-audit follow-ups (decided & shipped)

- Next-session suggestions are conditional on logged RIR vs category target: overshoot → +2 reps; undershoot → −1 rep; no RIR logged → hold load and ask for RIR. Blind "+1 rep" removed.
- Automatic volume tuning produces **proposals requiring explicit accept** on Home (with low-confidence label); silent target mutation removed. Reject leaves targets untouched.
- Joint-pain check-in is **area-localized** (muscle chips); the joint-based volume rule only fires for the flagged area.
- ACWR copy is a heuristic load-change indicator (1.5× labeled as rule-of-thumb), never injury prediction.
- Bottom navigation is disabled until the scope disclaimer is accepted.
- Set inputs and remove buttons have accessible names (aria-label); native inputs use dark color-scheme.