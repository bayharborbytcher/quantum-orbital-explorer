# Quantum Orbital Explorer ⚛️

An interactive, zero-dependency web application for visualizing hydrogen-like atomic orbitals, radial wave functions, probability distribution curves, and 3D angular shapes. 

Built entirely with **pure HTML5, CSS3, and Vanilla JavaScript (ES6+)** using the **Canvas 2D API**. Features zero build steps, zero external frameworks, and no heavy WebGL bundles—just raw mathematical computation and lightweight custom rendering engines[cite: 1, 3].

🔗 **[Launch Interactive Web App](https://bayharborbytcher.github.io/quantum-orbital-explorer/)** *(Update this link after enabling GitHub Pages)*

---

## 📸 Screenshots
<img width="1920" height="1080" alt="Screenshot (1364)" src="https://github.com/user-attachments/assets/09de134c-b62e-4dfa-beda-6d7a59827be1" />
<img width="1920" height="1080" alt="Screenshot (1366)" src="https://github.com/user-attachments/assets/9100d2ce-dd9c-4fc2-8b6b-1f496ba2c8de" />
<img width="1920" height="1080" alt="Screenshot (1367)" src="https://github.com/user-attachments/assets/32597ae4-d8c8-4408-a9c7-72e346d32a7c" />


---

## 💡 Motivation & Physics Context

In physical chemistry and quantum mechanics, understanding the behavior of an electron in a hydrogen-like atom often gets bogged down by static textbook diagrams. Key concepts like **radial nodes** ($\psi = 0$), the sign changes in the radial wave function $R(r)$, and the shift in the most probable radius caused by the $r^2$ spherical shell factor ($P(r) = r^2 R^2$) are hard to grasp without interaction[cite: 1, 3].

I built the **Quantum Orbital Explorer** to provide a real-time, mathematically rigorous playground where students, educators, and science enthusiasts can explore quantum numbers, overlay orbital states, check probability distributions numerically, and inspect 3D spherical harmonics in a clean, responsive workspace[cite: 1, 3].

---

## ✨ Key Features

### 1. Dual Radial Function Plotting ($R(r)$ & $P(r)$)
* **Radial Wave Function $R(r)$:** Real-time plotting of the radial part of $\psi = R(r) \cdot Y_l^m(\theta, \phi)$, highlighting zero-crossings (radial nodes) in red[cite: 1, 3].
* **Radial Distribution Function $P(r) = r^2 R^2(r)$:** Visualizes the actual probability density per unit radius, showing how the expanding area of spherical shells ($r^2$) forces the most probable radius ($r_{mp}$) away from the nucleus[cite: 1, 3].
* **Smooth Scene Interpolation:** Switching between orbitals uses a custom-built frame-blending loop that smoothly morphs graphs and axes rather than abruptly snap-updating.

### 2. Multi-Orbital Overlay Comparisons
* Superimpose multiple orbitals simultaneously on both $R(r)$ and $P(r)$ plots to analyze shell penetration, decay rates, and comparative node locations in real-time[cite: 1, 3].

### 3. Integrated Physics & Property Engine
* **Quantum State Cards:** Live readouts for $n$, $l$, and $m_l$ along with degenerate state counts[cite: 3].
* **Node Analysis:** Automatic analytical breakdown of radial nodes ($n - l - 1$), angular nodes ($l$), and total nodes ($n - 1$)[cite: 1, 3].
* **Integrated Probability Bands:** Numerically integrates $P(r)$ using the trapezoidal rule to calculate the precise percentage share of electron density trapped between consecutive radial nodes[cite: 3].
* **Property Dashboard:** Displays energy levels ($E_n = -\frac{13.606}{n^2}\text{ eV}$), mean radius $\langle r \rangle$, most probable radius $r_{mp}$, orbital angular momentum $\sqrt{l(l+1)}\hbar$, electron density at the nucleus $\vert{}\psi(0)\vert{}^2$, and numerical normalization verification ($\int_0^\infty r^2 R^2 dr = 1$)[cite: 3].

### 4. Interactive 3D Angular Shape Explorer ($s, p, d, f$)
* **Custom Software Z-Buffer Rasterizer:** Written completely from scratch in JavaScript (no Three.js or WebGL dependency) to render, shade, and depth-sort 3D spherical harmonics ($Y_l^m$)[cite: 3].
* **Isosurface Generation:** Solves polar plotting limitations where shapes like $d_{z^2}$ and $f_{z^3}$ pinch into flat discs. Instead, ray-marched isosurfaces of $\vert{}\psi\vert{}$ are used to render true 3D tori (doughnut rings) with hollow centers[cite: 3].
* **Controls:** Drag or use arrow keys to rotate, inspect positive/negative phase colors, double-click to reset, and toggle touch-friendly Free Rotate mode[cite: 3].

---

## 🛠️ Technical Stack & Architecture

* **Frontend:** HTML5, CSS3 (Custom CSS Grid, CSS Variables, glassmorphic UI, responsive drawer menu)[cite: 3].
* **Graphics:** HTML5 Canvas 2D API (High-DPI Retina resolution auto-scaling)[cite: 1, 3].
* **Scripting:** Pure Vanilla ES6+ JavaScript[cite: 1, 3].
* **Physics Framework:** Atomic units ($a_0 = 1, Z = 1$), exact hydrogenic wave functions up to the $4f$ subshell, and floating-point numeric integration loops[cite: 3].

---

## 🚀 Running Locally

Because this project requires no compiler, bundler, or web server setup, you can launch it in under 10 seconds:

1. Clone the repository:
   ```bash
   git clone [https://github.com/bayharborbytcher/quantum-orbital-explorer.git](https://github.com/bayharborbytcher/quantum-orbital-explorer.git)
