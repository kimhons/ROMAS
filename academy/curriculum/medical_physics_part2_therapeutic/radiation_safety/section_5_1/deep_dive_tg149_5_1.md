# Deep Dive: AAPM Task Group 149 (TG-149) - Intravascular Brachytherapy Dosimetry

This document provides a detailed deep dive into the recommendations of the AAPM Therapy Physics Committee Task Group No. 149, focusing on dose calculation formalisms and consensus dosimetry parameters for Intravascular Brachytherapy (IVBT). It serves as an update to aspects of the earlier TG-60 report, reflecting data and practices developed since its publication.

## I. Introduction & Background

*   **Context:** Addresses restenosis (re-narrowing of blood vessels) after percutaneous interventions (like angioplasty and stenting).
*   **IVBT Role:** Uses ionizing radiation to inhibit neointimal hyperplasia (cell growth causing restenosis). Proven effective for *in-stent restenosis* (restenosis occurring within a previously placed stent).
*   **Complementary to Drug-Eluting Stents (DES):** At the time of publication, DES were approved for *de novo* lesions, while IVBT was approved for *in-stent restenosis*. IVBT showed efficacy even in DES restenosis cases.
*   **Team Approach:** Emphasizes collaboration between interventional cardiologist, radiation oncologist, and medical physicist.
*   **TG-149 Goal:** Update TG-60 by recommending standard dose calculation formalisms and providing consensus dosimetry parameters for commonly used IVBT systems (Cordis 192Ir, Novoste 90Sr/90Y, Guidant 32P).
*   **Importance of Data:** Consensus data are crucial for consistent dosimetry, retrospective analysis of clinical trials, and potential future epidemiological studies or applications.

## II. Approved IVBT Systems & Sources (at time of publication)

*   **A. Systems:**
    *   **1. Cordis Checkmate (192Ir):**
        *   Uses Best Medical Model 81-01 192Ir seeds in nylon ribbons.
        *   Manual afterloader (source advanced by physician).
        *   Non-centering catheter.
        *   Typical treatment time: 15-40 min.
        *   Prescription examples: SCRIPPS/GAMMA-I (IVUS-based, 8 Gy at max luminal distance, limit 30 Gy at min distance); WRIST/GAMMA-II (fixed distance, e.g., 14-15 Gy at 2-2.4 mm).
    *   **2. Novoste Beta-Cath (90Sr/90Y):**
        *   Uses trains of 90Sr/90Y seeds.
        *   Hydraulic, closed-loop system advances/retracts seeds.
        *   Non-centering catheter.
        *   Two source sizes: 5 F (1.65 mm dia) and 3.5 F (1.16 mm dia).
        *   Prescription: Fixed distance (2 mm), dose depends on vessel diameter (e.g., 18.4 Gy for 2.7-3.3 mm, 23.0 Gy for 3.3-4.0 mm, based on revised NIST data).
    *   **3. Guidant Galileo (32P):**
        *   Uses a flexible 32P wire source.
        *   Computer-controlled HDR-like afterloader.
        *   Centering catheters (perfusion type).
        *   Approved for source pullback (stepping) to treat longer lesions.
        *   Prescription: Fixed depth (1 mm) into vessel wall, 20 Gy dose. Vessel diameter from balloon size/fluoroscopy.
*   **B. Source Descriptions:**
    *   **1. 192Ir Seeds (Best Model 81-01):**
        *   Gamma emitter (avg. 370 keV), 74-day half-life.
        *   3 mm long seed, 0.5 mm outer diameter.
        *   0.1 mm dia Pt/Ir core, 0.2 mm thick stainless steel encapsulation (radial).
        *   Ends *not* encapsulated (allows beta/electron emission in gaps).
        *   Assembled in nylon ribbon with 1 mm gaps.
        *   FDA-approved trains: 6, 10, 14 seeds (23, 39, 55 mm).
    *   **2. 90Sr/90Y Seeds (Novoste):**
        *   90Sr (parent, 28.8 yr half-life, 546 keV max beta) -> 90Y (daughter, 64 hr half-life, 2.28 MeV max beta). Secular equilibrium; 90Y betas provide therapy.
        *   2.5 mm long seeds, no separation in train.
        *   **5 F:** 0.56 mm dia ceramic core, 0.04 mm SS wall, 0.05 mm SS ends. Gold markers on train ends.
        *   **3.5 F:** 0.32 mm dia sintered Al powder core, 0.03 mm SS wall/ends. Stainless steel coil jacket holds seeds, Pt/Ir markers on train ends.
    *   **3. 32P Wire (Guidant):**
        *   Pure beta emitter, 14.3 day half-life, 1.71 MeV max beta.
        *   Flexible polymer core containing 32P.
        *   Encapsulated in NiTi tubing.
        *   Lengths: 27 mm (older) and 20 mm (newer, with proximal marker, allows stepping).

## III. Dosimetry Methods & Formalisms

*   **Challenge:** High dose gradients require sub-millimeter resolution dosimetry.
*   **A. Monte Carlo (MC) Calculations:**
    *   Advantage: High spatial resolution.
    *   Common Codes Used: ITS/CYLTRAN, EGS4, EGSnrc, MCNP (4B, 4C, X), PENELOPE, GEANT4.
    *   Importance: Requires careful validation and setup to ensure accuracy.
*   **B. Experimental Measurements:**
    *   Detectors need high resolution (<0.5 mm).
    *   **Radiochromic Film:** Widely used. Good resolution (<0.1 mm), near water-equivalent (for relevant energies), good sensitivity. Requires careful handling (depth scaling, time/temp dependence, low-energy photon dependence).
    *   Other detectors: Small scintillators, ultrathin TLDs.
    *   Primary Standards: Extrapolation ionization chambers (used by NIST, PTB, VSL).
*   **C. Dose Calculation Formalisms:**
    *   **1. Spherical Coordinates (TG-43 Update 2004):**
        *   `Ḋ(r, θ) = S_K * Λ * [G_L(r, θ) / G_L(r0, θ0)] * g_L(r) * F(r, θ)`
        *   `S_K`: Air kerma strength (for gamma sources, e.g., 192Ir).
        *   `Λ`: Dose rate constant (cGy h⁻¹ U⁻¹ at r0=1 cm, θ0=90°).
        *   `G_L(r, θ)`: Geometry function. **Line source approximation recommended for IVBT.**
            *   `G_L(r, θ) = β / (L * r * sinθ)` if θ ≠ 0
            *   `G_L(r, θ) = 1 / (r² - L²/4)` if θ = 0
            *   Where L = active length, β = angle subtended by source ends.
        *   `g_L(r)`: Radial dose function (accounts for scatter/attenuation along transverse axis).
        *   `F(r, θ)`: 2D anisotropy function (accounts for angular absorption/scatter).
        *   **For Beta Seeds (e.g., 90Sr/90Y):** Replace `S_K * Λ` with `Ḋw(r0)`, the reference absorbed dose rate in water at r0=2 mm.
        *   **Superposition:** Recommended for calculating dose from seed trains (sum dose from individual seeds).
    *   **2. Cylindrical Coordinates (Modified TG-43 for Line Sources):**
        *   Developed because standard TG-43 shows limitations for *long* beta sources at *short* distances.
        *   `Ḋ(ρ, z) = Ḋw(ρ0) * [G(ρ, z) / G(ρ0, 0)] * g(ρ) * h(ρ, z)`
        *   `(ρ, z)`: Cylindrical coordinates (radial distance ρ, longitudinal distance z from center).
        *   `Ḋw(ρ0)`: Reference absorbed dose rate in water at ρ0=2 mm, z=0.
        *   `G(ρ, z)`: Geometry function in cylindrical coordinates.
        *   `g(ρ)`: 1D radial dose function (along z=0 axis).
        *   `h(ρ, z)`: 2D anisotropy function in cylindrical coordinates.
        *   **Recommended for Guidant 32P wire sources.**

## IV. Consensus Data Methodology & Recommendations

*   **Principle:** Consensus based on comparing available datasets (MC and experimental). Preference given to averages or most densely populated studies (often MC).
*   **A. Source Strength Specification:**
    *   **1. 192Ir:** **Air Kerma Strength (S_K)** remains the standard (Units: U = µGy m² h⁻¹).
    *   **2. 32P and 90Sr/90Y:** **Reference Absorbed Dose Rate to Water (Ḋw(r0))** at r0=2 mm on transverse bisector. Measured by primary labs using extrapolation chambers.
        *   *Caution:* Well chambers measure activity-related quantity. Inferring Ḋw(r0) requires assuming uniform activity distribution, which must be verified (e.g., by film). Non-uniform sources have different Activity-to-Ḋw(r0) relationship.
    *   **Calibration Transfer:** Well chambers are primary tool. Standardized inserts are crucial. Regular checks with long-lived reference sources (e.g., 137Cs, 90Sr/90Y) are necessary.
*   **B. Recommended Formalism:**
    *   **192Ir & 90Sr/90Y Seeds/Trains:** **TG-43 formalism (spherical)** using line source geometry function and linear superposition for trains.
    *   **32P Wires (Guidant):** **Modified TG-43 formalism (cylindrical)**.
*   **C. Recommended Dosimetry Parameters:**
    *   **1. 192Ir (Best Model 81-01 Seed):**
        *   `L` (Active Length): **3.0 mm**.
        *   `Λ` (Dose Rate Constant): **1.12 cGy h⁻¹ U⁻¹** (TG-43 value).
        *   `g_L(r)` (Radial Dose Function): Based on TG-43 polynomial fit (Table II/III), valid 0.5-90 mm. Excludes low-energy beta contribution (absorbed by ribbon).
        *   `F(r, θ)` (Anisotropy Function): Based on Patel et al. (2003) for r < 10 mm, TG-43 for r ≥ 10 mm (Table IV).
    *   **2. 90Sr/90Y (Novoste Seeds):**
        *   `L` (Active Length): **2.5 mm**.
        *   `Ḋw(2mm) / Activity`: **1.10 Gy min⁻¹ mCi⁻¹** (Consensus average, for both 5F & 3.5F seeds).
        *   `g_L(r)` (Radial Dose Function): Based on Wang & Li (2002) fit for 5F source (Table II/III), valid 0.5-9.9 mm.
        *   `F(r, θ)` (Anisotropy Function): Based on Wang & Li (2002) for 5F source (Table XI).
    *   **3. 32P (Guidant Wires):**
        *   Use **cylindrical formalism**.
        *   `Ḋw(2mm) / Activity`: Consensus values provided (Table XII).
        *   `g(ρ)` (Radial Dose Function): Fit parameters provided (Table II/III), valid 0.5-6.5 mm.
        *   `h(ρ, z)` (Anisotropy Function): Tabulated data provided (Tables XIIIa/b for 20/27 mm wires).
*   **D. Media Scaling:**
    *   Dosimetry data typically determined in water or water-equivalent plastic.
    *   Scaling needed for measurements in non-water media (like radiochromic film in solid phantoms).
    *   Use stopping power ratios (water-to-medium) for electrons, mass energy-absorption coefficient ratios for photons.
    *   TG-149 provides scaling factors for common phantom materials (Solid Water, Virtual Water, PMMA, Polystyrene) for the three radionuclides (Table XIV).

## V. Discussion and Conclusions

*   TG-149 provides consensus dosimetry parameters and formalism recommendations for the three main IVBT systems used clinically at the time.
*   Adoption of these recommendations promotes standardization in dose calculation and reporting.
*   Highlights the importance of accurate source strength specification (S_K for 192Ir, Ḋw(2mm) for betas) and the challenges in transferring beta source calibrations.
*   Recommends specific formalisms (spherical TG-43 for seeds/trains, cylindrical for 32P wires) based on source geometry and physics.
*   Provides comprehensive tables and fits for `Λ`, `g(r)`, `F(r,θ)`, `g(ρ)`, `h(ρ,z)`, and media scaling factors.

*Disclaimer: This deep dive summarizes key aspects of AAPM TG-149. Users should always refer to the original report for complete details, data tables, and context.*
