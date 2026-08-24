# FHP Creating a Hypertrophy Training Program — The 8-Step Builder (Study Notes)

Source: Najib's playlist #14 (8 parts, ALL new). This is FHP's complete program-construction walkthrough — **the algorithmic spec for GymLog v2's program builder**, step by step, with their worked example running through every part. Raw transcripts in [transcripts/](transcripts/).

## Step 1 — Mesocycle skeleton (Part 1)

- Block of 3–6 weeks = overloading weeks + deload.
- Overloading = volume between a minimum adaptive threshold and your max recoverable threshold (proximity to failure assumed).
- **Deload = 50–65% of normal overloading volume** — still enough to maintain, low enough to shed fatigue.
- Ratio: **1 deload per 2–5 overloading weeks**. Advanced lifters sit at the frequent end (bigger stimulus → bigger fatigue); novices at the far end.
- Their worked example: 4-week meso, deload placed at WEEK ONE, three overloading weeks after. (FHP consistently front-loads the easy week.)

## Step 2 — Frequency & split (Part 2)

Two separate dials, neither affects growth much at equated volume:
- **Workout frequency** (days/week total) — lifestyle decision, not optimization.
- **Muscle-group frequency** — spreading a muscle's weekly sets over more sessions raises set QUALITY (less intra-session fatigue); unclear if that improves outcomes.
- Guidelines: hit each muscle **>1×/week** when possible; never high-volume same-muscle on consecutive days.
- Worked example: 4-day upper/lower, every muscle 2×/week non-consecutive.

## Step 3 — Exercise selection (Part 3)

Six filters, in priority order:

1. **Biomechanics** — does the lift load the target muscle AT ALL?
2. **Stimulus-to-fatigue ratio** — stimulus per unit of systemic cost.
3. **Range of motion** — bigger ROM generally wins.
4. **Compound vs isolation** — compounds are efficient but only ONE muscle limits them; isolation always makes the target the limiter. Bi-articular muscles (biceps during rows/pulls) escape compound tension → need direct work. Rule: majority of volume from compounds, isolation fills coverage gaps.
5. **Tension curve** — prefer constant-tension (cable fly > dumbbell fly) or hard-at-stretch profiles (T-bar/landmine rows match the descending pull curve).
6. **Individual anatomy + preference** — pain-free beats theoretically-optimal; enjoyment raises effort.

Session-design rule from their build: **never stack multiple heavy compounds in one session** (shared stabilizer fatigue + impractical rest periods). Day emphases alternate (day 1 press-biased, day 3 pull-biased).

Their example program (steal for defaults):
- D1 (chest/triceps/front-delt bias): incline BB press, seated cable row, DB OHP, cable fly, pushdown, EZ curl
- D2 (quad bias): back squat, back extension, leg extension, standing calf raise
- D3 (back/rear-delt/biceps bias): barbell row, incline BB press, lat pulldown, reverse fly, EZ curl, pushdown
- D4 (glute/ham bias): stiff-leg deadlift, leg press, leg curl, standing calf raise

## Step 4 — Volume (Part 4)

- Metric = **sets per muscle per week** (rep-range equivalence makes sets the honest currency).
- Dose-response confirmed, ceiling unknown — but you'll hit a practical limiter FIRST, in this order: **joint tolerance → systemic fatigue → time**.
- So: perform the most volume you can handle *without joint pain, without breaching systemic capacity, within your real schedule* — then allocate by PRIORITY (weak points get more).
- Their balanced example: chest 12 / back 12 / quads 9 / hams 9 / shoulders 8 direct / biceps 8 direct / triceps 8 direct / calves 6 direct.
- Deload weeks run at **~60–65%** of these numbers.

## Step 5 — Proximity to failure (Part 5)

- Global default: **0–3 RIR everywhere**; avoid habitual true failure (disproportionate fatigue vs marginal growth).
- Per category (their exact prescriptions):
  - Heavy lower-body compounds (squat, SLDL): **2–3 RIR**
  - Other compounds: **1–2 RIR**
  - Isolations: **0–1 RIR**
- By rep zone: 6–12-rep sets → 1–3 RIR; 12–20+-rep sets → 0–2 RIR.
- **RIR stays CONSTANT across the whole mesocycle** — progression is NOT pre-programmed (see Step 7). This is FHP's signature difference from RP's ramp-to-failure.

## Step 6 — Rep ranges & load (Part 6)

- Reps and load are ONE variable (inverse relationship) — prescribe NEITHER strictly.
- Band: **6–20 reps** equally valid near failure. Compounds suit 6–12 (cardio/stabilizers cap high-rep squats); isolations suit 12–20 (heavy single-joint loading is injurious).
- High-rep work goes LATE in sessions (its metabolic fatigue would tax following exercises).
- Leave reps/load cells EMPTY for the lifter to record and self-adjust mid-session — their worked example shows dropping load between sets to stay in the target zone while honoring RIR.
- Philosophy: rigid numbers can't match an individual's actual rate of progress.

## Step 7 — Progressive overload (Part 7)

- **Not written into the program at all.** Fixed sets + fixed RIR → performance moves on its own timeline.
- Novice: rep improvements visible within one meso. Advanced: may take 2–3 mesos before a trend appears.
- Judge performance ONLY in the 6–20 band, strict technique, across MONTHS — never compare single sessions.
- Overload = the natural result of growth expressing itself, not a schedule to force.

## Step 8 — Long-term periodization (Part 8)

Periodization for hypertrophy = **reactive management after each meso**, driven by four inputs:

| Input | Signals |
|---|---|
| Performance trend | improving in 6–20 band = working; stagnant/declining across MULTIPLE mesos = adjust |
| Systemic fatigue | lethargy, poor sleep, illness risk, effortful sessions |
| Joint pain | acute (one-off) vs chronic aches (volume/load too high for that joint) |
| Monotony | boredom threatening adherence |

Adjustment levers, in order:
1. **Change nothing** — if trending well, repeat the program!
2. **Volume ±**: increase for a stalled-but-healthy muscle (e.g., chest 12→14) or for more growth when recovering fine; decrease when systemically fried or a joint complains.
3. **Exercise swap**: compounds kept ≥3 mesos, isolations 1–2 mesos acceptable; swap triggers = plateau, monotony, pain — swap to a close variant (incline BB → flat DB press).

## The complete builder algorithm (GymLog v2 spec)

```
1. Meso length: 4 wks default (wk1 = deload @60–65%, wks 2–4 identical overload)
2. Split: upper/lower ×2 default; each muscle ≥2×/wk non-consecutive
3. Exercises: 6-filter selection; ≤1 heavy compound/session; day emphases alternate
4. Volume: sets/muscle/wk picker with practical-limit warnings (joints/systemic/time)
5. RIR: auto-assigned by category (squat/SLDL 2-3, compounds 1-2, isolation 0-1)
6. Reps/load: left blank; user logs; app suggests load adjustments to stay in zone
7. Progression: none forced — app charts rep trends per exercise
8. End-of-meso review screen: performance/fatigue/joints/monotony → recommend hold/volume±/swap
```

This 8-step flow + the template architecture (fhp-templates notes) + RP landmarks together define the entire v2 training engine.
