# AMDNR RX 9070 Profiles

Community tuning profiles for **AMDNR / OptiScaler** tested on an **AMD Radeon RX 9070**.

This repository does **not** redistribute AMDNR, OptiScaler, lmxxf runtime files, DLLs, PAK files, or any other upstream binaries. Install AMDNR from the original project first, then apply only the profile from this repository.

## Current tested profiles


### Cyberpunk 2077

Tested on RX 9070 at 2560x1440 with RT Ultra, Path Tracing off. Current profile uses AMDNR 0.3.5.1 + lmxxf 0.39, pixel-exact 1706x960 neural input, Style 1, Full Network, Interleave 1.4 and Edit Detail 1.06. FSR Frame Generation is routed through OptiScaler in Borderless Windowed mode.

Profile path:

`profiles/cyberpunk-2077/OptiScaler.ini`

Detailed notes:

`profiles/cyberpunk-2077/README.md`

### Assassin's Creed Black Flag Resynced

Tested setup:

- GPU: Radeon RX 9070
- Resolution: 2560x1440
- Game preset: Ultra + heavy RT
- Upscaling: FSR Quality
- AMDNR: 0.3.4.1
- Neural runtime: lmxxf
- NR working size: exact render size, approximately 1712x960
- TierSnap: OFF
- Fast mode: OFF
- Model interleave: 2
- Interleave preset: 10 / Edit accumulation
- lmxxf Edit Detail: 0.75

Profile path:

`profiles/assassins-creed-black-flag-resynced/OptiScaler.ini`

## Scope

This profile was tuned and validated specifically in **Assassin's Creed Black Flag Resynced** on an RX 9070. It is **not a universal RX 9070 preset for every game**.

For other games, use it only as a starting point. Different titles can need different NR resolution, interleave, edit/detail, colour and temporal settings.

## Why this profile exists

The goal was to keep the stronger facial reconstruction and image detail of Neural Rendering while avoiding the overly dry / grainy micro-detail that appeared on faces in shadow with more aggressive settings.

The tuning process showed:

- 900-tier was faster, but facial reconstruction in shadow became noticeably harsher.
- Exact ~960 input improved face quality without destroying performance.
- Lowering `AmdLmxxfEditDetail` to `0.75` reduced harsh micro-detail while retaining most of the NR clarity and facial definition.
- Disabling the native character mask did not improve the result.
- Lowering only SkinStructure had a smaller effect than EditDetail.

## Performance observed

Same general test area, scene-dependent:

- Full game render without NR: about 73-74 FPS
- Tuned lmxxf NR profile: about 44-48 FPS
- Tuned profile with frame generation enabled: roughly 70-80 FPS in the tested area

In our test setup, frame generation felt substantially more responsive than playing at the 44-48 FPS base rate. This is a subjective gameplay observation, not a guarantee of lower measured input latency. Latency and frame pacing depend on the game, frame-generation implementation, driver, CPU and other settings.

## Visual character of the effect

In some lighting conditions, Neural Rendering can increase local contrast, facial definition and fine texture enough that the result may initially resemble strong sharpening or an aggressive ReShade-style post-process. The effect is not simply a post-process filter, but the visual impression can sometimes be similar.

The result is also **subjective**. Some users may prefer the stronger facial definition and detail produced by NR, while others may prefer the softer and more natural-looking original image. This profile should be treated as a tested balance of image quality and performance, not as an objectively better look for everyone.
## Additional test material

This repository also keeps selected experiment history and one game-to-game comparison so the tuning process can be reproduced instead of only showing the final result.

- Black Flag experiment history: `profiles/assassins-creed-black-flag-resynced/experiments/`
- Kingdom Come: Deliverance II comparison: `comparisons/kingdom-come-deliverance-2/`

The KCD2 material was also tested on the **RX 9070 non-XT**. It includes OptiScaler snapshots, the standalone DLSS-NR-on-AMD 0.4.1 reference config and a confirmed NR OFF / NR ON screenshot pair.

Image-quality comments throughout the repository are subjective observations from the captured scenes, not universal rankings. Different viewers, displays and scenes can produce a different preference.

## Installation

1. Install the current AMDNR release from the original AMDNR repository.
2. Start the game once and verify AMDNR works.
3. Back up your existing `OptiScaler.ini`.
4. Copy this repository's `OptiScaler.ini` for the game into the game directory, replacing the existing config.
5. Restart the game.
6. Verify the Neural runtime is `lmxxf`.
7. Test the profile before changing additional settings.

Do not copy old runtime DLL/PAK files from this repository: none are provided here. Keep the runtime files that belong to your installed AMDNR version.

## Rollback

Restore your backed-up `OptiScaler.ini`, or use AMDNR's own default/profile reset.

## Notes

This is a hardware/game-specific tuning profile. It was tuned visually with repeated comparisons of faces under sun, partial shadow and deep shadow, while also checking frame rate and frame-time behavior.

The profile is intended as a starting point for RX 9070 users. RX 9070 XT, RX 7000 and APUs may behave differently.

## Upstream projects and credits

AMDNR / OptiScaler integration:
https://github.com/3zwr1/AMD-NR---OptiScaler

lmxxf DLSS5-on-AMD work:
https://github.com/lmxxf/dlss5-on-amd-9070xt-porting

Daniel Blanco DLSS-NR-on-AMD runtime:
https://github.com/danielblnc/DLSS-NR-on-AMD

All upstream code, binaries, runtimes, trademarks and project names remain the property of their respective authors and are governed by their upstream licenses.

This repository only contains tuning configuration and documentation created from testing. It is not an official AMDNR, OptiScaler, AMD, NVIDIA, Ubisoft or Assassin's Creed project.

