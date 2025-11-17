<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:ff0080,50:7928ca,100:00d4ff&height=200&section=header&text=Pixel%20Pusher%20Plus&fontColor=ffffff&fontSize=50&animation=twinkling&fontAlignY=35&desc=Audio-Reactive%20VJ%20Engine%20%7C%20Real-Time%20GPU%20Shader%20Visualization&descSize=18&descAlignY=55" alt="Pixel Pusher Plus Header" />
</p>

<div align="center">

[![Rust](https://img.shields.io/badge/Rust-1.70+-000000?style=for-the-badge&logo=rust&logoColor=white)](https://www.rust-lang.org/)
[![wgpu](https://img.shields.io/badge/wgpu-22.1-4285F4?style=for-the-badge&logo=webgl&logoColor=white)](https://wgpu.rs/)
[![License](https://img.shields.io/badge/License-GPL--3.0-green?style=for-the-badge)](LICENSE)
[![Version](https://img.shields.io/badge/Version-0.2.0-blue?style=for-the-badge)](https://github.com/Snapwave333/pixel-pusher-plus/releases)

[![Build Status](https://img.shields.io/github/actions/workflow/status/Snapwave333/pixel-pusher-plus/rust.yml?style=flat-square&label=CI)](https://github.com/Snapwave333/pixel-pusher-plus/actions)
[![Last Commit](https://img.shields.io/github/last-commit/Snapwave333/pixel-pusher-plus?style=flat-square)](https://github.com/Snapwave333/pixel-pusher-plus/commits)
[![Issues](https://img.shields.io/github/issues/Snapwave333/pixel-pusher-plus?style=flat-square)](https://github.com/Snapwave333/pixel-pusher-plus/issues)
[![Stars](https://img.shields.io/github/stars/Snapwave333/pixel-pusher-plus?style=flat-square)](https://github.com/Snapwave333/pixel-pusher-plus/stargazers)

**Enterprise-grade, fullscreen audio-reactive VJ engine with AI-powered uniqueness tracking, 19 GPU shader patterns, and intelligent mood-based visual orchestration.**

[Features](#-features) • [Demo](#-live-demo) • [Quick Start](#-quick-start) • [Architecture](#-architecture) • [Patterns](#-shader-patterns) • [Contributing](#-contributing)

</div>

---

<p align="center">
  <img src="OneDrive/Desktop/apps/glsl/branding/demo_live.gif" alt="Live Demo" width="800"/>
</p>

## 🎯 Overview

Pixel Pusher Plus is a **next-generation audio-reactive visual engine** built with Rust and wgpu (WebGPU). It analyzes audio input in real-time, detects musical mood/genre, and generates stunning GPU-accelerated shader visualizations that respond dynamically to the music.

### Why Pixel Pusher Plus?

- 🧠 **AI-Powered Uniqueness** — Never see the same animation twice with intelligent variation tracking
- 🎵 **Deep Audio Analysis** — BPM detection, frequency band analysis, mood classification
- ⚡ **GPU-Accelerated** — Real-time WGSL shaders running on modern GPUs via wgpu
- 🎭 **Intelligent Orchestration** — Multi-act performances with narrative story arcs
- 🔄 **Smooth Transitions** — Cubic easing morphs between patterns with blacklist management
- 🎨 **19 Unique Patterns** — From plasma waves to fractals, truchet tiles to voronoi cells

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 🎤 Audio Intelligence
- Real-time BPM detection
- Frequency band analysis (bass/mid/treble)
- Automatic mood classification:
  - 🌊 **Ambient** — Slow, atmospheric
  - ⚡ **Energetic** — Fast, high-energy
  - 🎵 **Melodic** — Balanced, harmonic
  - 🥁 **Rhythmic** — Beat-synchronized
  - 🌀 **Chaotic** — Wild, unpredictable

</td>
<td width="50%">

### 🎨 Visual Engine
- 19 GPU shader patterns
- 16 color palettes
- Multiple color modes (Rainbow, Neon, Cyberpunk, etc.)
- Smooth parameter morphing
- Beat-synchronized effects
- Unique animation generation per transition

</td>
</tr>
<tr>
<td width="50%">

### 🧠 AI Orchestration
- **MacroStateEngine** — Intelligent decision making
- **ParamModifiers** — Unique randomization per show
- **Uniqueness Tracking** — HashSet prevents repetition
- **Pattern Blacklisting** — 30-second cooldown prevents overuse
- **Transition Triggers** — Beat, energy, mood, or random

</td>
<td width="50%">

### 🚀 Performance
- Cross-platform (Windows, macOS, Linux)
- Native GPU acceleration via wgpu
- Async audio processing with Tokio
- Zero-copy rendering pipeline
- Configurable FPS and resolution

</td>
</tr>
</table>

---

## 🎬 Live Demo

<p align="center">
  <img src="OneDrive/Desktop/apps/glsl/branding/screenshot_live_fullscreen.png" alt="Screenshot" width="800"/>
</p>

<details>
<summary><b>📸 More Screenshots</b></summary>

| Pattern | Description |
|---------|-------------|
| **Plasma** | Classic flowing plasma effect |
| **Waves** | Gentle ocean-like undulations |
| **Vortex** | Spiraling center vortex |
| **Voronoi** | Cell-based organic patterns |
| **Truchet** | Procedural tile patterns |
| **Fractal** | Complex mathematical patterns |
| **Glitch** | Digital distortion effects |
| **Grid** | Flowing neon grid lines |

</details>

---

## 🚀 Quick Start

### Prerequisites

- **Rust** 1.70+ with Cargo
- **GPU** with Vulkan, Metal, or DX12 support
- **Audio input** (optional, for reactive mode)

### Installation

```bash
# Clone the repository
git clone https://github.com/Snapwave333/pixel-pusher-plus.git
cd pixel-pusher-plus/OneDrive/Desktop/glsl

# Build release version
cargo build --release

# Run with audio support
cargo run --release --features audio
```

### Quick Run

```bash
# Default mode (no audio)
cargo run --release

# With audio reactivity
cargo run --release --features audio

# Specific pattern
cargo run --release -- --pattern plasma

# Custom settings
cargo run --release -- --fps 60 --width 1920 --height 1080
```

### Feature Flags

| Flag | Description |
|------|-------------|
| `audio` | Enable real-time audio analysis (cpal + rustfft) |
| `nvml` | NVIDIA GPU metrics monitoring |
| `amd` | AMD GPU support |
| `intel` | Intel GPU support |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    PIXEL PUSHER PLUS                        │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────────┐    ┌──────────────┐    ┌─────────────────┐   │
│  │  Audio  │───▶│   Analysis   │───▶│   MacroState    │   │
│  │  Input  │    │  (BPM/Mood)  │    │     Engine      │   │
│  └─────────┘    └──────────────┘    └────────┬────────┘   │
│                                               │             │
│                                               ▼             │
│  ┌─────────┐    ┌──────────────┐    ┌─────────────────┐   │
│  │   GPU   │◀───│    wgpu      │◀───│   Uniqueness    │   │
│  │ Display │    │   Shaders    │    │    Tracker      │   │
│  └─────────┘    └──────────────┘    └─────────────────┘   │
│                                                             │
│  19 Patterns │ 16 Palettes │ 5 Moods │ 1000+ Combinations │
└─────────────────────────────────────────────────────────────┘
```

### Core Components

| Component | File | Purpose |
|-----------|------|---------|
| **MacroStateEngine** | `src/vj/macro_state_engine.rs` | Brain of the autonomous VJ — decides transitions |
| **ParamModifiers** | `src/vj/macro_state_engine.rs` | Unique random parameters per animation |
| **ShaderParams** | `src/params/shader_params.rs` | 31+ controllable visual parameters |
| **PatternMorpher** | `src/vj/pattern_morpher.rs` | Smooth transitions between patterns |
| **BPMDetector** | `src/vj/bpm_detector.rs` | Real-time beat detection |
| **VisualOrchestrator** | `src/vj/visual_orchestrator.rs` | Multi-act show management |

---

## 🎨 Shader Patterns

<div align="center">

| Pattern | Type | Best For |
|---------|------|----------|
| 🌊 **Plasma** | Energetic | High-energy drops |
| 🌊 **Waves** | Ambient | Chill, atmospheric |
| 💧 **Ripples** | Ambient | Gentle transitions |
| 🌀 **Vortex** | Ambient | Building tension |
| 📡 **Noise** | Ambient | Textural backgrounds |
| 📐 **Geometric** | Melodic | Structured beats |
| 🔬 **Voronoi** | Chaotic | Complex soundscapes |
| 🧩 **Truchet** | Chaotic | Intricate patterns |
| ⬡ **Hexagonal** | Melodic | Clean arrangements |
| 〰️ **Interference** | Melodic | Layered sounds |
| 🌿 **Fractal** | Chaotic | Math-heavy tracks |
| 📺 **Glitch** | Energetic | Digital/Electronic |
| 🌀 **Spiral** | Energetic | Uplifting builds |
| ⭕ **Rings** | Rhythmic | Steady beats |
| ▦ **Grid** | Rhythmic | Strong rhythm |
| 💎 **Diamonds** | Rhythmic | Clear percussion |
| 🔮 **Sphere** | Melodic | 3D depth |
| ✡️ **Octgrams** | Rhythmic | Complex patterns |
| 🌊 **WarpedFbm** | Chaotic | Noise-based chaos |

</div>

---

## 🧰 Tech Stack

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/rust/rust-plain.svg" width="50" title="Rust"/>
  &nbsp;&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/webgl/webgl-original.svg" width="50" title="wgpu/WebGPU"/>
  &nbsp;&nbsp;
  <img src="https://raw.githubusercontent.com/nicbarker/clay/main/docs/Clay_Logo.svg" width="50" title="WGSL Shaders"/>
  &nbsp;&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg" width="50" title="Linux"/>
  &nbsp;&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/windows8/windows8-original.svg" width="50" title="Windows"/>
  &nbsp;&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/apple/apple-original.svg" width="50" title="macOS"/>
</p>

<div align="center">

| Technology | Purpose |
|------------|---------|
| **Rust** | Core language — memory safety, performance |
| **wgpu** | Cross-platform GPU abstraction (Vulkan/Metal/DX12) |
| **WGSL** | WebGPU Shading Language for GPU compute |
| **Tokio** | Async runtime for audio processing |
| **cpal** | Cross-platform audio input |
| **rustfft** | Fast Fourier Transform for frequency analysis |
| **crossterm** | Terminal rendering and input |
| **serde** | Configuration serialization |

</div>

---

## 📁 Project Structure

```
pixel-pusher-plus/
├── OneDrive/Desktop/glsl/          # Main VJ engine
│   ├── src/
│   │   ├── main.rs                 # Entry point
│   │   ├── lib.rs                  # Library root
│   │   ├── params/                 # Configuration & parameters
│   │   │   ├── shader_params.rs    # 31+ visual parameters
│   │   │   └── types.rs            # Pattern/Palette/ColorMode enums
│   │   ├── vj/                     # Visual Jockey intelligence
│   │   │   ├── macro_state_engine.rs   # AI decision brain
│   │   │   ├── visual_orchestrator.rs  # Show management
│   │   │   ├── pattern_morpher.rs      # Smooth transitions
│   │   │   ├── bpm_detector.rs         # Beat detection
│   │   │   └── autonomous_startup.rs   # Initialization
│   │   ├── shader_common/          # WGSL shader code
│   │   │   ├── main.wgsl           # Pattern dispatcher
│   │   │   └── effects.wgsl        # Visual effects
│   │   ├── shader_patterns/        # Individual patterns
│   │   │   ├── plasma.wgsl
│   │   │   ├── waves.wgsl
│   │   │   ├── grid.wgsl           # Fixed grid lines
│   │   │   └── ... (19 patterns)
│   │   ├── render/                 # GPU rendering pipeline
│   │   └── app/                    # Application logic
│   ├── Cargo.toml                  # Dependencies
│   └── branding/                   # Visual assets
└── README.md                       # You are here!
```

---

## 🎛️ Configuration

### Shader Parameters

The engine exposes 31+ parameters for fine-tuning visuals:

```rust
ShaderParams {
    // Core animation
    frequency: 10.0,      // Pattern frequency
    amplitude: 1.0,       // Effect strength
    speed: 0.5,           // Animation speed
    scale: 1.0,           // Pattern scale

    // Color grading
    brightness: 1.2,
    contrast: 1.0,
    hue: 0.0,
    saturation: 1.0,
    gamma: 1.0,

    // Effects
    noise_strength: 0.15,
    distort_amplitude: 0.5,
    vignette: 0.3,

    // Camera
    camera_zoom: 1.0,
    camera_rotation: 0.0,
    camera_pan_x: 0.0,
    camera_pan_y: 0.0,

    // Audio reactivity
    bass_influence: 1.0,
    mid_influence: 1.0,
    treble_influence: 1.0,

    // ...and more
}
```

### AI Uniqueness System

Each transition generates unique parameter modifiers:

```rust
ParamModifiers {
    frequency_mult: 0.5..2.5,   // Random multiplier
    speed_mult: 0.3..2.0,
    amplitude_mult: 0.5..2.0,
    hue_shift: 0.0..1.0,        // Color variation
    rotation_offset: 0..TAU,    // Camera rotation
    // ... tracked in HashSet to prevent repetition
}
```

---

## 🛠️ Development

### Building from Source

```bash
# Clone
git clone https://github.com/Snapwave333/pixel-pusher-plus.git
cd pixel-pusher-plus/OneDrive/Desktop/glsl

# Debug build
cargo build

# Release build (optimized)
cargo build --release

# Run tests
cargo test

# Check compilation
cargo check

# Format code
cargo fmt

# Lint
cargo clippy
```

### Adding a New Pattern

1. Create shader file: `src/shader_patterns/mypattern.wgsl`
2. Add pattern function:
```wgsl
fn mypattern_pattern(uv: vec2<f32>, time: f32) -> vec2<f32> {
    // Your shader logic here
    return vec2<f32>(value, secondary);
}
```
3. Register in `src/shader_common/main.wgsl` dispatcher
4. Add enum variant in `src/params/types.rs`
5. Map mood preferences in `MacroStateEngine`

---

## 🤝 Contributing

Contributions are welcome! Here's how to get started:

1. **Fork** the repository
2. **Clone** your fork
3. **Create** a feature branch: `git checkout -b feature/amazing-pattern`
4. **Make** your changes
5. **Test** thoroughly: `cargo test`
6. **Commit**: `git commit -m "feat: add amazing pattern"`
7. **Push**: `git push origin feature/amazing-pattern`
8. **Open** a Pull Request

### Contribution Ideas

- 🎨 New shader patterns
- 🎵 Audio analysis improvements
- 📊 Performance optimizations
- 📚 Documentation improvements
- 🐛 Bug fixes
- ✨ New color modes/palettes

---

## 📜 License

This project is licensed under the **GNU General Public License v3.0** — see the [LICENSE](LICENSE) file for details.

```
This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.
```

---

## 🙏 Acknowledgments

- **wgpu** team for the excellent WebGPU abstraction
- **Rust** community for the amazing ecosystem
- **WGSL** specification authors
- Shader inspiration from various sources including Shadertoy community

---

## 📊 Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=Snapwave333&repo=pixel-pusher-plus&theme=radical" alt="Repo Stats"/>
</p>

---

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:00d4ff,50:7928ca,100:ff0080&height=120&section=footer&animation=twinkling" alt="Footer" />
</p>

<div align="center">

**Made with ❤️ and Rust**

[⬆️ Back to Top](#)

</div>
