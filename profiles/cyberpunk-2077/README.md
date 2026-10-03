# Cyberpunk 2077 — RX 9070 AMDNR profile

Tested on Radeon RX 9070 at 2560x1440 with RT Ultra, Path Tracing off.

## Stack

- AMDNR: 0.3.5.1
- Neural runtime: lmxxf 0.39
- Upscaling path: FFX / FSR through OptiScaler
- Neural input: 1706x960, pixel-exact
- Runtime style: 1 (classic lmxxf look)
- Full Network: ON, all 71 blocks
- Fast Mode: OFF
- Model Interleave: 1.4
- Interleave preset: 10 / Edit accumulation
- lmxxf Edit Detail: 1.06
- Neural passes: 1
- Network Output / raw mode: OFF

## Frame generation

Frame generation is handled by OptiScaler rather than NVIDIA DLSS-G:

- FrameGen Enabled: true
- FG Input: upscaler
- FG Output: FSR FG
- Display mode: Borderless Windowed

On this RX 9070 setup, NVIDIA DLSS-G is rejected by Streamline as unsupported hardware, while FSR Frame Generation creates and activates successfully through OptiScaler.

Observed in the tested scene:

- Base framerate with NR enabled: roughly 45-50 FPS
- Displayed framerate with FSR FG: roughly 90-100 FPS
- NR off can rise substantially higher depending on scene

These numbers are scene-dependent and are not a benchmark guarantee.

## Why this version

A heavier every-frame model test produced little visible gain for the extra cost. A two-pass test cut performance to roughly 20 FPS without enough visual improvement to justify it.

The selected profile keeps the sharper pixel-exact 1706x960 character, Style 1 and Full Network, while using Interleave 1.4 to preserve practical framerate.

Earlier tests with 1919x1080 + Style 0 looked softer in this game, despite the higher neural feed resolution.

## Files

Use:

`OptiScaler.ini`

Back up your current config before replacing it.

Fresh comparison screenshots will be added separately after the final capture pass.

## Final comparison screenshots

Final NR OFF / ON pairs are available here:

`../../comparisons/cyberpunk-2077/screenshots/`

Comparison notes:

`../../comparisons/cyberpunk-2077/README.md`

During the final FSR Frame Generation test, the player reported responsive controls with no perceptible extra input lag and no obvious large geometry distortions during movement. These are subjective gameplay observations rather than instrumented latency or artifact measurements.
