# Ls-dyna-crash-box-analysis
Component-level axial crash box impact study

# Axial Crash Box Impact Analysis

**Aim:** Model and simulate the axial crushing of a thin-walled crash box against a rigid wall to study  
energy absorption, peak force, and crush mode in a component-level setup suitable for the LS-DYNA Student license.

## Project Overview

- Thin-walled square crash box: **60 × 60 × t mm**, length **L = 200 mm**.
- Variants:
  - Baseline steel (**t = 1.2 mm**)
  - Thicker steel (**t = 1.5 mm**)
  - Aluminum alloy (**t = 1.2 mm, Al**)
  - Triggered design (**t = 1.2 mm + initiator**)
- Key metrics:
  - Force–displacement response
  - Energy balance (GLSTAT-style)
  - Specific Energy Absorption (SEA)
  - Crush mode (early, mid, final folding)



## Repository Contents

- `CrashBox_Final_Report.pdf` — Multi-page report with aim, methods, results, and key numbers.
- `CrashBox_Final_OnePager.pdf` — One-page visual summary.
- `images/`
  - `model_setup.png` — Schematic model of the crash box vs rigid wall.
  - `contact_setup.png` — RIGIDWALL_PLANAR contact schematic.
  - `frame_early.png`, `frame_mid.png`, `frame_final.png` — Conceptual folding stages.
  - `force_displacement.png` — Force–displacement curves for all variants.
  - `glstat.png` — Energy balance (kinetic, internal, hourglass, sliding).
  - `sea.png` — SEA comparison based on geometry+density masses.
- `results_data.json` — Geometry, densities, analytically computed masses, energies to 150 mm, SEA values, and F–x arrays.
- `Project_Aim_and_Scope.txt` — Short description of aim, scope, and units.
- `CV_Bullets.txt` — Paste-ready bullet points for a CV.
- `STAR_Story.txt` — STAR-format narrative of the project.

## Method Summary

- Geometry: square tube 60 × 60 × t mm, length 200 mm.
- Mass calculation:
  - Cross-section area: `A = b·h − (b − 2t)·(h − 2t)`
  - Volume: `V = A · L`
  - Mass: `m = V · ρ` with:
    - ρ_steel = 7.85 × 10⁻⁶ kg/mm³
    - ρ_Al = 2.70 × 10⁻⁶ kg/mm³
- Synthetic force–displacement curves are integrated to 150 mm to obtain absorbed energy.
- SEA is calculated as: `SEA = Energy_to_150mm / Mass`.

## Intended Use

This repository is designed as a **portfolio project** to demonstrate:

- Understanding of crash box design and crashworthiness metrics.
- Ability to set up and interpret LS-DYNA-style axial crash problems.
- Skills in organising results into clean technical reports and visual summaries.
