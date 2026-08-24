# Flow High Performance — Injury Prevention & Load Management (Study Notes)

Source: Najib's saved playlist (13 entries; #13 "Stretching" was a duplicate already covered in [../fhp-recovery/NOTES.md](../fhp-recovery/NOTES.md) — 12 new videos processed). Raw transcripts in [transcripts/](transcripts/). Companions: [../rp-series/NOTES.md](../rp-series/NOTES.md) · [../rp-specialization/NOTES.md](../rp-specialization/NOTES.md) · [../fhp-periodization/NOTES.md](../fhp-periodization/NOTES.md) · [../fhp-recovery/NOTES.md](../fhp-recovery/NOTES.md).

## 1. The master principle: spikes injure, load protects

- **Acute:Chronic Workload Ratio (ACWR)** [01][09]: this week's load ÷ your rolling 4-week weekly average. Spikes above the average = elevated injury risk; smooth gradual progressions keep it low. Units are flexible — for lifters, **sets per muscle per week** (or volume-load) works.
- Load itself is protective: high chronic workload shields you from competition/activity spikes; strength training cuts injury risk ~70%; proprioception training up to ~50%; stretching ≈ nothing [03].
- Practical ramp rules [09]: +1–2 sets/week maximum; after any layoff, ramp back over weeks; new exercises start at LOWER volume than what they replace, building over 1–2 weeks; before attempting true 1RMs, re-acclimate to heavy loads gradually if you've lived in 6–15 reps.

## 2. Training around pain — the priority ladder [10]

Pain ≠ damage (87.6% of pain-free adults have disc bulging on MRI). Hypertrophy is non-specific — almost always a pain-free path exists. Exhaust in this order:

1. **Zero cost**: swap the exercise · drop load below the pain threshold (e.g., stay under ~70% 1RM) · slow the tempo (any rep duration up to ~8s grows equally).
2. **Tiny cost**: shorten rests · tweak technique · BFR on limbs.
3. **Real cost**: limit ROM (full ROM is better — regain it later) · stop short of failure · cut volume (dose-response exists).

## 3. Blood Flow Restriction (BFR) [02]

- Cuffs/bands make light loads feel heavy physiologically (~50% capacity with cuff ≈ ~80% without).
- Main use = keeping muscle during joint flare-ups/rehab, not for healthy trainees. Protocol example: knee pain above 60% 1RM → stay ≤60%, near failure, add BFR → productive stimulus without irritating the joint.

## 4. Case-study playbook (what actually fixed injuries)

- **Tendon-type knee pain from lifting** [05]: remove bounce/stretch-shortening reps → pause squats & power variations; fix with eccentric-overload leg extensions (up heavy with 2 legs, lower slow on ONE leg 3–5 s) — relief within week one. Knee sleeves = symptom masker with dependency.
- **Compressive low-back pain** [06]: cap barbell work ~70%, pivot to horizontal loading (leg press, hip thrusts, back extensions, planks, ab wheel), partial pulls floor-to-knee, +5–10% every 4–5 weeks. Failed experiments worth knowing: self-massage, "functional core drills," breathing rituals.
- **Injury as a forced specialization block** [04]: keep training everything pain-free (often becomes a hypertrophy phase for non-injured areas), return to aggravating lifts gradually (~+0.5–1 km/wk style ramps). Never push through sharp pain and never take total rest then jump to "100%".

## 5. Hamstring resilience (bonus for anyone who runs/plays) [07] [08]

- Nordic curls cut hamstring strains up to ~51% — or machine curl single-leg eccentrics as an alternative.
- Sprint training also builds longer fascicles and speed, but Nordics carry the direct injury-rate evidence. Do both if you sprint; Nordics regardless.

## 6. Range of motion — final word [12] (see also recovery notes #11)

- Full ROM ≥ partials overall — but position matters more than completeness: **lengthened-position partials BEAT full ROM**, shortened partials are worst (calf studies within-subject).
- Strength follows specificity (partial squats improve partial 1RM; deep squats improve full 1RM + size).
- Train pain-free ranges first; treat stretch-position emphasis as the default growth driver everywhere (matches RP's lengthened-partial enthusiasm).

## 7. Goals cheat-sheet [11]

| Goal | Core prescription |
|---|---|
| Hypertrophy | target muscle limits set · 5–20 reps · ≤3 RIR · >10 sets/muscle/wk |
| Fat loss | deficit · lose ≤~1% BW/week · protein ≥1.5 g/kg · ~10k steps/day |
| Strength | specificity of the lift · plateau → grow prime movers · transition slowly |
| Health | lift 2–3×/wk 45–60 min · cardio 2–3×/wk (1–2 hard) |

---

# How this feeds GymLog (analysis-only — no app changes)

| Concept | Future GymLog feature |
|---|---|
| ACWR spike detection | Weekly sets/muscle vs 4-week average shown as ratio; red flag when spiking (computable TODAY from history data model) |
| Pain thresholds per exercise | Per-exercise notes field: "pain above X load / ROM Y" so future sessions respect it |
| Injury-mode block | One-tap switch to "injury mode": app suppresses aggravating exercises, suggests Cat-1 swaps from library, keeps other muscles progressing |
| Ramp-back after layoff | Layoff detection (gap in history) → auto-scaled restart volumes for 1–2 weeks |
| Lengthened-ROM coaching | Exercise how-to text already exists in library; add "stretch emphasis" cue tags |

This series completes the safety layer. The full v2 science stack now covers WHAT (mechanics/specialization), HOW MUCH/HOW FAST (periodization), RECOVERY (recovery series), and STAYING UNBROKEN (this series).
