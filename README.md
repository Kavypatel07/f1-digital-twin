# 🏎️ Apex Overdrive: Cinematic F1 Digital Twin 🌌

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Build: Success](https://img.shields.io/badge/Build-Success-brightgreen.svg)]()
[![Graphics: WebGL/SVG](https://img.shields.io/badge/Graphics-SVG_/_CSS3-blue.svg)]()

> **A high-fidelity, real-time F1 data visualization engine that simulates the grit and drama of the Singapore Marina Bay Street Circuit.**

This project blends photorealistic night-race aesthetics with holographic SVG telemetry, featuring synchronized overtakes, live tire degradation, and incident management.

---

## 🎬 Cinematic Site Preview

<img src="Apex F1- Perview v1.1.gif" width="500" alt="Description of the animation" />

---

## 📸 Snapshots of the Action


<img src="Apex F1- sample v1.1.png" width="500" alt="image" />

<img src="Apex F1- sample v1.2.png" width="500" alt="image" />

<img src="Apex F1- sample v1.3.png" width="500" alt="image" />

---

## ✨ Key Feature Highlights

*   **⚡ 60FPS LERP Motion**: Buttery smooth car movements using linear interpolation.
*   **📐 3D Perspective**: Cinematic road depth using CSS `perspective` and `rotateX`.
*   **🔗 Real-Time Digital Twin**: 1:1 synchronization between track cars and holographic dots.
*   **🚨 Automatic Incident Response**: Yellow flag triggers and dots freeze instantly on impact.
*   **📊 Dynamic HUD**: Live tire degradation and leaderboard re-ranking based on race events.

---

## 🛰️ The Vision: "Digital Twin" Synchronization

This project isn't just an animation; it's a **Digital Twin**. Every pixel on the "Live Road" is mathematically tied to the "Holographic Map."

### ⚙️ How it Works (The Tech Stack)
*   **🏎️ Core**: Vanilla HTML5, CSS3, & High-Performance JavaScript.
*   **🗺️ Map Logic**: SVG Coordinate Mapping with Path-Trail interpolation.
*   **📐 3D UI**: CSS Perspective (`1000px`) and `rotateX` transformations for a cinematic cockpit depth.
*   **📊 Data HUD**: Dynamic DOM rendering for the Live Leaderboard and Tire Strategy.

---

## 🛠️ Component Deep-Dive (Fun Learning Guide)

This project is built like a tiered engine, perfect for students learning **Dynamic Web Systems**.

### 1️⃣ The Keyframe Engine (`KF_MC`, `KF_RB`, etc.)
Instead of random movements, each car follows a precise "script."
*   **💡 Concept**: We store arrays of `[Time, Top, Left, Rotation]`.
*   **🧠 Logic**: Our `getState()` function uses **Linear Interpolation (LERP)** to find the exact position of a car between two keyframes. This creates buttery-smooth 60FPS motion.

### 2️⃣ The Holographic Map Sync (`dotPos`)
*   **❓ The Problem**: How do you know where a dot should be on a complex curly circuit?
*   **✨ The Solution**: We treat the total circuit length as `1.0` (100%).
*   **🔗 Sync Logic**: As a car moves on the "Live Road," its percentage on the circuit map is updated. The `dotPos()` function takes that percentage and maps it to the exact `[X, Y]` coordinates on the SVG path.

### 3️⃣ The HUD Brain (`renderLB`)
*   **🖥️ The Logic**: The Leaderboard isn't static. It listens to the `elapsed` animation time. 
*   **⚡ Sync Trigger**: At exactly `9.5 seconds`, the "State Machine" triggers an **Overtake Switch**. The UI instantly re-ranks the drivers, swaps the Tire Strategy order, and flashes the "P1 CHANGE" alert.

### 4️⃣ Incident Management (Yellow Flag) 🚩
*   **💥 Physics**: When the Ferrari impacts the wall (10.6s), we use a `frozenDotPos` to stop the holographic dot exactly at the pixel coordinate of the crash.
*   **🚨 Visuals**: We trigger rapid CSS opacity filters to create a "beeping" incident signal on the map.

---

## 🎨 Asset Management: How to find the components?
*   **Vector Cars**: The cars are implemented as **Optimized Inline SVGs** inside `index.html`. This ensures zero-latency loading and allows for dynamic CSS neon glows (`drop-shadow`).
*   **Marina Bay Backdrop**: `marina-bay-bg.png` provides the gritty, high-contrast atmospheric depth. It is connected via standard CSS `background-image` on the `#dashboard` container.
*   **Fonts**: The project pulls *Orbitron* and *Rajdhani* from Google Fonts to maintain the premium HUD appearance.

---

## 🎮 How to Start
Want to see it in action? It's simple:

1.  **Clone** the repository.
2.  **Open** a terminal in the folder.
3.  **Run** a local server (to handle image permissions):
    ```bash
    python -m http.server 8765
    ```
4.  **Visit** `http://localhost:8765` in your browser.

---

## 📚 Resources Used
*   **Fonts**: *Orbitron* (for that futuristic telemetry feel), *Rajdhani* (for readable data points).
*   **Design**: Inspired by real-world F1 broadcast graphics and "Cyberpunk" aesthetics.
*   **Mathematical Concepts**: LERP (Linear Interpolation), Modular Arithmetic (`% LOOP`), and SVG Path Logic.

---

*Made with ❤️ for F1 Fans and Code Explorers.*
