# Cyberpunk 2077 — final NR comparison

Final screenshots for the RX 9070 Cyberpunk profile.

Test setup:

- 2560x1440
- RT Ultra, Path Tracing off
- AMDNR 0.3.5.1
- lmxxf 0.39
- pixel-exact 1706x960 neural input
- Style 1
- Full Network ON
- Interleave 1.4
- Edit Detail 1.06
- FSR Frame Generation enabled through OptiScaler

The screenshots were captured during the final frame-generation test. The player reported that control remained responsive and did not perceive additional input lag. This is a subjective gameplay observation, not a latency measurement.

No obvious large geometry distortions, broken shoulders or major frame-generation artifacts were noticed during normal movement in this test.

Screenshot pairs:

- 01 / 02 — red-haired NPC, NR OFF / ON
- 03 / 04 — sunglasses NPC, NR OFF / ON
- 05 / 06 — NCPD officer close-up, NR OFF / ON
- 07 / 08 — bartender, NR OFF / ON

NR state was cross-checked against the AMDNR toggle timestamps in OptiScaler.log for these captures.

The NCPD pair shows the effect most clearly: NR ON adds stronger skin micro-detail, facial definition, beard texture and material contrast while keeping the overall face geometry intact in this scene.
