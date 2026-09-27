AMDNR RX 9070 / Black Flag test profiles

01_daniel_current.ini   - snapshot of the working danielblnc setup.
02_lmxxf_baseline.ini   - lmxxf, no tier snap, no Fast mode, no interleave.
03_lmxxf_900tier.ini    - lmxxf + TierSnap=true. 1712x960 input -> ~1600x897 / 900 tier.
04_lmxxf_fast.ini       - lmxxf + TierSnap=true + Fast mode. 1712x960 input -> ~1280x718 / 720 tier.

Automated same-startup-scene measurements, FSR Quality, NR 100%, FG/interleave off:
02 baseline: hip mean ~16.6 ms; cadence ~41.5-42.2 fps.
03 900 tier: hip mean ~12.37 ms; cadence ~52.7-53.3 fps.
04 Fast/720: hip mean ~9.2 ms; cadence ~68.6-69.2 fps.

Notes:
- These are startup/static-scene measurements, not a full gameplay benchmark.
- 03 preserves more network detail and is the current active profile for visual testing.
- 04 is the performance profile; its fresh edit magnitude was lower, so fine detail may be softer.
- Interleave remains OFF so the backend/tier cost is isolated.
- Working Daniel logs are preserved alongside profile 01.
