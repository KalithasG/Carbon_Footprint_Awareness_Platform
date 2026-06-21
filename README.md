# Carbon Footprint Awareness Platform

An immersive, responsive, and scientifically grounded educational suite designed to clarify and demystify global greenhouse gas metrics. Grounded in the findings of the **IPCC Working Group III**, the **Greenhouse Gas Protocol**, and macroeconomic trade disclosures, this platform replaces individual micro-anxiety with a macro-reconstructive awareness of systemic climate pathways.

---

## 📖 Table of Contents
1. [Core Philosophy](#-core-philosophy)
2. [Interactive Modules & Features](#-interactive-modules--features)
3. [Technical Architecture](#-technical-architecture)
4. [Directory & Asset Structure](#-directory--asset-structure)
5. [Installation & Local Run](#-installation--local-run)
6. [Hosting & Deployment Guide](#-hosting--deployment-guide)

---

## 💡 Core Philosophy

Unlike traditional carbon engines that focus strictly on individual calculators, the **Carbon Footprint Awareness Platform** utilizes a **Zero-Calculator Architecture**. 

* **Macro Over Micro:** Rather than calculating personal micro-footprints (which can induce individual action paralysis), the platform directs cognitive focus toward large-scale industrial supply-chains, sovereign wealth consumption structures, and systemic decarbonization pathways.
* **Aesthetic Intent:** Tailored in accordance with Google Material 3 Visual Standards, leveraging a clean, dark-accented slate color theme, generous negative space, sophisticated typography pairing (*Space Grotesk* for display elements and *JetBrains Mono* for technical indicators), and high-contrast, accessible visual grids.

---

## 🎨 Interactive Modules & Features

The platform is designed to be highly immersive, guiding the reader through high-fidelity visual and computational frameworks:

### 1. 🎥 Widescreen Ambient Video Slot (Cinematic Canvas)
Positioned at the absolute peak of the page, this cinematic widescreen (with an elegant `21:9` widescreen aspect ratio) acts like a high-fidelity looping GIF.
* **Ambient Behavior:** Plays muted, loops automatically, and plays inline on hardware configurations without rendering stutters.
* **Graceful Fallbacks:** Incorporates an automated native loader that detects when video assets are fully cached and active. If assets are not present in `/public/videos`, a gorgeous pulsing SVG overlay remains as an interactive placeholder outlining placement directions.

### 2. 🌀 Intersection Observer Animations
To enhance the editorial feel, all section cards, interactive canvas tables, and custom-drawn SVGs utilize a custom implementation of the web **Intersection Observer API**.
* **Scroll-staggered Entrances:** Elements seamlessly fade and translate upward as the user scrolls, creating a tactile spatial pacing.

### 3. 🔍 Interactive Myth Buster Grid
Interactive structural cards mapping common carbon fallacies against raw peer-reviewed realities.
* **Key Interactions:** Keyboard navigable elements that animate flip transitions flawlessly on click or space/enter key triggers, validating strict accessibility standards.

### 4. 🧮 GWP Equivalence Visualization
An interactive cascade mapping non-CO₂ greenhouse gases (such as methane $\text{CH}_4$, nitrous oxide $\text{N}_2\text{O}$, and fluorinated compounds) into global-warming potential equivalents over 20-year and 100-year horizons.

### 5. 🏗️ The 3-Scope Accounting Map
A systemic layout dissecting emissions boundaries:
* **Scope 1:** Direct combustion & chemical processes.
* **Scope 2:** Purchased energy, thermal units, and stream grids.
* **Scope 3:** Full up-stream and down-stream value chains, spanning from purchased services to product end-of-life cycles.

### 6. 📊 Sovereign & Sector Data Explorer
Draws dynamic SVG charts in real time using client-side vanilla JavaScript.
* **Zero Libraries Overhead:** High-performance, fully inline SVGs that rebuild programmatically on view resize events. Includes interactive state filters enabling toggles between:
  * Global Greenhouse Gas Sectors Share (%)
  * Sovereign Income Cohort Footprints (Tons per capita per year)
  * Dual Scaled Overlay: Sector Share vs. Income Cohorts

### 7. 🔄 Value-Chain Circular Economy Loop
An active SVG state diagram demonstrating the critical flows of feedback loops, circular extraction vectors, and municipal-to-industrial recovery paths.

### 8. 📝 Comprehension Check-Out Quiz
A client-side interactive validation quiz allowing users to test their understanding. Includes active instant validation indicators, score tallies, and structured educational critiques based on their selected answers.

---

## 🛠️ Technical Architecture

This application is built as a single-page distribution mounted on a modern TypeScript stack with extreme lightweight performance constraints:

* **Engine:** [React 18+](https://react.dev/) + [Vite](https://vitejs.dev/) bundler configuration.
* **Language:** TypeScript (`strict: true`) ensuring compile-time safety and clear documentation.
* **Styling Method:** Tailored CSS utility directives mapping responsive viewports flawlessly (`sm:`, `md:`, `lg:`).
* **Charts & Animations:** Custom native vector rendering (Inline SVG + CSS transitions) coupled with an native raw JavaScript Intersection Observer lifecycle controller (`.animate-on-scroll`).

---

## 📁 Directory & Asset Structure

```bash
├── public/                 # Static assets directory copied directly to build root
│   └── videos/             # Folder designated for looping panoramic cinematic assets
│       ├── README.md       # Asset usage documentation
│       ├── carbon_loop.mp4 # Ideal location to place your .mp4 looping background
│       └── carbon_loop.webm# WebM version for maximized multi-browser compatibility
├── src/
│   ├── App.tsx             # Main Application routing and component architecture
│   ├── main.tsx            # React application mounting and rendering entry point
│   └── index.css           # Global custom theme variables and utility core
├── index.html              # Custom indexed entry framework housing structural components
├── package.json            # Project dependencies, compile configs, and task runners
└── metadata.json           # Application configurations and sandbox environment bounds
```

---

## 🚀 Installation & Local Run

To boot up the application locally in development mode:

1. **Clone or Download** the folder contents into your workspace.
2. **Install all dependencies** via npm:
   ```bash
   npm install
   ```
3. **Execute the local development server**:
   ```bash
   npm run dev
   ```
4. Open the displayed local service address (usually `http://localhost:3000` or `http://localhost:5173`) in your browser.

---

## ☁️ Hosting & Deploying to Firebase

Because this platform operates on a static full-client distribution architecture, it is perfectly suited for ultra-fast, zero-cost CDN delivery using **Firebase Hosting**.

### Steps to Deploy manually:

1. **Install Firebase CLI Tools globally**:
   ```bash
   npm install -g firebase-tools
   ```
2. **Authenticate your command line**:
   ```bash
   firebase login
   ```
3. **Initialize Firebase** at the project root:
   ```bash
   firebase init hosting
   ```
   * Set your public directory to `dist` (Vite's default compiled outputs destination).
   * Configure as a single-page app (Rewrite all URLs to `/index.html`): `Yes`.
4. **Compile the production-ready distribution**:
   ```bash
   npm run build
   ```
5. **Publish to Google CDN servers**:
   ```bash
   firebase deploy --only hosting
   ```

Upon completion, Firebase will produce a global SSL-encrypted public URL hosting your modern **Carbon Footprint Awareness Platform**.
