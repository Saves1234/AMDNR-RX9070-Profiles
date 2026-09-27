# Assassin's Creed Black Flag Resynced — experiment history

This folder preserves the tuning sequence that led to the current RX 9070 profile.

Test hardware: **AMD Radeon RX 9070 (non-XT)**.

The current recommended/tested profile remains:

`../OptiScaler.ini`

The files in this folder are **experiment snapshots**, not a list of presets that are all recommended.

## Early backend / performance tests

- `01_daniel_current.ini` — working Daniel backend snapshot.
- `02_lmxxf_baseline.ini` — lmxxf baseline, no TierSnap, Fast mode or interleave.
- `03_lmxxf_900tier.ini` — lmxxf with TierSnap / ~900-tier working size.
- `04_lmxxf_fast.ini` — lmxxf Fast mode / ~720-tier working size.

Startup/static-scene measurements saved during that stage:

- lmxxf baseline: about **41.5–42.2 FPS**
- 900 tier: about **52.7–53.3 FPS**
- Fast / 720 tier: about **68.6–69.2 FPS**

These are startup/static-scene measurements, not full gameplay benchmarks.

## Interleave and later tuning

- `05_lmxxf_fast_interleave2.ini`
- `06_lmxxf_fast_interleave3.ini`
- `07_fast720_i3_keep_20260927-170254.ini`
- `08_lmxxf_900tier_i2.ini`
- `09_current_before_fg_2026-09-27_1904.ini`

The file `BENCHMARK_2026-09-27_current_build.txt` preserves the measurements from the intermediate 900-tier / Interleave 2 stage, including FG on/off observations.

## Exact ~960 quality-tuning sequence

The later passes moved away from TierSnap/Fast and back to the exact ~1712x960 render-size input:

- `10_lmxxf_exact960_i2_0341.ini`
- `11_lmxxf_exact960_i2_skin07_0341.ini`
- `12_lmxxf_exact960_i2_nomask_0341.ini`
- `13_lmxxf_exact960_i2_edit08_0341.ini`
- `14_lmxxf_exact960_i2_edit075_0341.ini`

Profile **14** became the basis of the current main profile: lmxxf, exact ~960 input, Interleave 2, Fast OFF, TierSnap OFF and EditDetail 0.75.

The visual goal was not simply maximum sharpness. The final tuning tried to keep the stronger NR facial/detail reconstruction while reducing the dry or grainy-looking micro-detail that became noticeable on faces in shadow.

## Subjective image quality

The visual result is subjective. Some viewers may prefer stronger facial definition and local contrast; others may prefer the softer original presentation.

These snapshots are published so the tuning path can be reproduced and compared, not to claim one universal "best" look.
