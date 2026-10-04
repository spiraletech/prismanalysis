# PRISM Analysis

PRISM Analysis is a native Windows x64 audio-analysis lab built in C++.

It captures system audio locally through Windows audio interfaces and renders a live 0–20 kHz analysis field with stereo, heatmap, low-end, and semantic-geometry views.

## Current build

**PRISM_LAB_ORBMODES.exe**

SHA-256:

`fe35932df6a3eea6b7e2930926e57c3e7f252a1fb491d13749df9966708b1de5`

## Core features

- 0–20 kHz live spectrum
- FL-style amplitude heatmap logic
- Mouse-hover dBFS readout
- True Phase Scope / stereo goniometer
- Mid/Side and stereo-correlation analysis
- Bass/Sub Bouncer
- Semantic Orb with three audio-driven modes:
  - LOTUS
  - CYMATIC
  - MANDALA
- Melody rail
- Local system-audio analysis; no cloud service required

## Controls

| Key | Action |
| --- | --- |
| O | Cycle LOTUS → CYMATIC → MANDALA |
| T | Cycle Spectrum / Heatmap / Dual |
| I | Cycle SUM / LEFT / RIGHT / MID / SIDE |
| D | Cycle display floor -60 / -90 / -120 dB |
| Y | Cycle visual tilt 0 / 3 / 4.5 / 6 dB/oct |
| L | Toggle Melody Rail |
| H | Toggle HUD |
| F | Freeze / unfreeze |
| R | Reset analyzer state |
| S | Capture |
| F11 | Fullscreen |
| Esc | Exit |

## Orb logic

The semantic orb is driven by measured audio features rather than static animation.

**Lotus** responds to sustain, bass pressure, harmonic energy, stereo width, and transient flutter.

**Mandala** maps dominant frequency to radial symmetry, harmonic energy to nested rings, chroma memory to spoke structure, and spectral roughness to controlled deformation.

**Cymatic** preserves the nodal / interference-oriented hydro-cymatic view.

## Build

The repository includes the native C++ source/build ingredients used for the current executable. The Windows build uses MSVC with a static runtime and links against standard Windows system libraries.

## Platform

- Windows x64
- Native C++
- WASAPI loopback audio capture
- GDI software rendering
