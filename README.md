# Quantum Orbital Explorer ⚛️

An interactive, zero-dependency web application for visualizing hydrogen-like atomic orbitals, radial wave functions, probability distribution curves, and 3D angular shapes. 

Built entirely with **pure HTML5, CSS3, and Vanilla JavaScript (ES6+)** using the **Canvas 2D API**. Features zero build steps, zero external frameworks, and no heavy WebGL bundles—just raw mathematical computation and lightweight custom rendering engines.

🔗 **[Launch Interactive Web App](https://bayharborbytcher.github.io/quantum-orbital-explorer/)**

---

## 📸 Screenshots

<img width="1920" height="1080" alt="Screenshot (1364)" src="https://github.com/user-attachments/assets/09de134c-b62e-4dfa-beda-6d7a59827be1" />
<img width="1920" height="1080" alt="Screenshot (1366)" src="https://github.com/user-attachments/assets/9100d2ce-dd9c-4fc2-8b6b-1f496ba2c8de" />
<img width="1920" height="1080" alt="Screenshot (1367)" src="https://github.com/user-attachments/assets/32597ae4-d8c8-4408-a9c7-72e346d32a7c" />

---

## 💡 Motivation & Physics Context

In physical chemistry and quantum mechanics, understanding the behavior of an electron in a hydrogen-like atom often gets bogged down by static textbook diagrams. Key concepts like **radial nodes** (where wave function ψ = 0), the sign changes in the radial wave function R(r), and the shift in the most probable radius caused by the r² spherical shell factor are hard to grasp without interaction.

I built the **Quantum Orbital Explorer** to provide a real-time, mathematically rigorous playground where students, educators, and science enthusiasts can explore quantum numbers, overlay orbital states, check probability distributions numerically, and inspect 3D spherical harmonics in a clean, responsive workspace.

---

## ✨ Key Features

### 1. Dual Radial Function Plotting: R(r) & P(r)
* **Radial Wave Function R(r):** Real-time plotting of the radial part of ψ = R(r) · Yₗᵐ(θ, φ), highlighting zero-crossings (radial nodes) in red.
* **Radial Distribution Function P(r) = r²R²(r):** Visualizes the actual probability density per unit radius, showing how the expanding area of spherical shells (r²) forces the most probable radius away from the nucleus.
* **Smooth Scene Interpolation:** Switching between orbitals uses a custom-built frame-blending loop that smoothly morphs graphs and axes rather than abruptly snap-updating.

### 2. Multi-Orbital Overlay Comparisons
* Superimpose multiple orbitals simultaneously on both R(r) and P(r) plots to analyze shell penetration, decay rates, and comparative node locations in real-time.

### 3. Integrated Physics & Property Engine
* **Quantum State Cards:** Live readouts for n, l, and mₗ along with degenerate state counts.
* **Node Analysis:** Automatic analytical breakdown of radial nodes (n − l − 1), angular nodes (l), and total nodes (n − 1).
* **Integrated Probability Bands:** Numerically integrates P(r) using the trapezoidal rule to calculate the precise percentage share of electron density trapped between consecutive radial nodes.
* **Property Dashboard:** Displays energy levels (E♜), mean radius ⟨r⟩, most probable radius r_mp, orbital angular momentum, electron density at the nucleus, and numerical normalization verification (∫ r²R² dr = 1).

### 4. Interactive 3D Angular Shape Explorer (s, p, d, f)
* **Custom Software Z-Buffer Rasterizer:** Written completely from scratch in JavaScript (no Three.js or WebGL dependency) to render, shade, and depth-sort 3D spherical harmonics.
* **Isosurface Generation:** Solves polar plotting limitations where shapes like d_z² and f_z³ pinch into flat discs. Instead, ray-marched isosurfaces of |ψ| are used to render true 3D tori (doughnut rings) with hollow centers.
* **Controls:** Drag or use arrow keys to rotate, inspect positive/negative phase colors, double-click to reset, and toggle touch-friendly Free Rotate mode.

---

## 🛠️ Technical Stack & Architecture

* **Frontend:** HTML5, CSS3 (Custom CSS Grid, CSS Variables, glassmorphic UI, responsive drawer menu).
* **Graphics:** HTML5 Canvas 2D API (High-DPI Retina resolution auto-scaling).
* **Scripting:** Pure Vanilla ES6+ JavaScript.
* **Physics Framework:** Atomic units (a₀ = 1, Z = 1), exact hydrogenic wave functions up to the 4f subshell, and floating-point numeric integration loops.

---

## 🚀 Running Locally

Because this project requires no compiler, bundler, or web server setup, you can launch it in under 10 seconds:

1. Clone the repository:
   ```bash
   git clone [https://github.com/bayharborbytcher/quantum-orbital-explorer.git](https://github.com/bayharborbytcher/quantum-orbital-explorer.git)
