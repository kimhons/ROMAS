# Deep Dive: AAPM Task Group 186 (TG-186) - Model-Based Dose Calculation Algorithms (MBDCA) in Brachytherapy

This document provides a detailed deep dive into the recommendations of the AAPM Task Group 186, focusing on the transition from the TG-43 formalism to model-based dose calculation algorithms (MBDCAs) for brachytherapy treatment planning. It addresses the rationale, challenges, and practical implementation guidance for these advanced algorithms.

## I. Introduction

*   **Problem:** The standard TG-43 formalism for brachytherapy dose calculation assumes a homogeneous water medium, ignoring tissue/applicator heterogeneities, interseed attenuation, and patient size effects. This can lead to significant inaccuracies (over/underestimations >5%, sometimes > factor of 10), especially for low-energy sources or near high-Z materials (applicators, bone).
*   **Solution:** Model-Based Dose Calculation Algorithms (MBDCAs) account for radiation transport in heterogeneous media, offering more physically accurate dose distributions.
*   **TG-186 Goal:** Provide guidance for early MBDCA adopters to ensure practice uniformity, addressing key challenges:
    *   Dose specification medium (Sec III).
    *   Voxel-by-voxel cross-section assignment from CT (Sec IV).
    *   MBDCA commissioning procedures (Sec V).
*   **Endorsement:** Report endorsed by AAPM, ESTRO, ABS, ABG.
*   **Target Audience:** Experienced brachytherapy physicists and physicians.

## II. Review of Heterogeneity Effects (Limitations of TG-43)

*   **Magnitude:** Errors depend on photon energy, materials, and distance.
*   **Low Energy (LE) Sources (<50 keV; e.g., 125I, 103Pd, 131Cs, EBS):**
    *   Photoelectric effect dominates; highly sensitive to material composition (Z).
    *   TG-43 (Dw,w-TG43) vs. MBDCA (Dm,m): Differences up to 25% in breast (EBS), 10-20% in prostate (seeds), 9% in eye plaques. Primarily due to tissue composition differences (bone, soft tissue vs. water).
    *   Interseed attenuation adds ~4% difference in prostate implants.
    *   TG-43 generally *overestimates* target dose (e.g., D90 by ~7% in prostate) and OAR dose compared to Dm,m.
    *   Lung brachytherapy: TG-43 *underestimates* dose in larger volumes with more lung tissue.
*   **Intermediate Energy (50-200 keV; e.g., 169Yb):**
    *   Scatter effects maximal in soft tissues.
    *   Breast brachytherapy (169Yb): TG-43 > Dm,m by 5% at PTV surface, 15-25% at skin, 30% in lung. Contrast in balloon increases discrepancy.
*   **High Energy (HE) Sources (>200 keV; e.g., 192Ir, 137Cs):**
    *   Less sensitive to composition than LE, but scatter and shielding are important.
    *   Esophageal (192Ir): No difference in target, but TG-43 overestimates spinal cord dose (13%), underestimates sternum dose (15%).
    *   Breast (192Ir): TG-43 ≈ Dm,m in PTV, but TG-43 > Dm,m by 5% at skin, 10% in lung.
    *   Endorectal (192Ir) w/ shield: TG-43 ≈ Dm,m (<2%) in soft tissue, but large differences in bone (18-23% in cortical, 3-7% in spongiosa/femoral).
*   **CBCT Relevance:** CBCT energies overlap with brachytherapy. Studies show bone dose 2-4x higher than soft tissue dose, highlighting sensitivity to composition and geometry, especially near bone surfaces.

## III. Review of Model-Based Dose Calculation Algorithms (MBDCAs)

*   **Goal:** Account for 3D geometry and material heterogeneities.
*   **Primary vs. Scatter:** Primary dose can be calculated accurately via 1D ray-tracing (assuming CPE). Scatter dose requires 3D methods.
*   **A. Semi-Empirical Approaches:**
    *   Faster than full MBDCAs, aim for improved accuracy over TG-43.
    *   Examples: 1D scaling for shields, Primary/Scatter separation methods, MC pre-calculated applicator-specific kernels (hybrid TG-43).
    *   Address specific issues (e.g., shielding) but not full 3D heterogeneity.
*   **B. Model-Based Algorithms (Full 3D Transport):**
    *   **1. Collapsed-Cone (CC) Superposition/Convolution:**
        *   Kernel-based method, optimized for speed via angular discretization.
        *   Uses primary ray-trace + scatter kernels (first, multiple).
        *   Handles heterogeneities via density scaling (O'Connor theorem) or material-specific scaling.
        *   Compatible with Primary/Scatter Separation (PSS) source formalism.
        *   Example Implementation: Oncentra Brachy (Elekta).
    *   **2. Deterministic Solvers (Grid-Based Boltzmann Solvers - GBBS):**
        *   Solve Linear Boltzmann Transport Equation (LBTE) by discretizing space, angle, energy.
        *   Examples: DANTSYS (discrete ordinates), Attila (DFEM), Acuros BV (optimized GBBS).
        *   Example Implementation: Acuros BV in BrachyVision (Varian).
    *   **3. Monte Carlo (MC) Simulations:**
        *   Gold standard for accuracy; solves LBTE via random sampling.
        *   Requires significant computation time, but becoming faster.
        *   Codes used/developed for brachytherapy: PTRAN, BrachyDose (EGSnrc), Geant4, MCNP, Penelope.
        *   Often used to generate benchmark data or for complex cases.

## IV. Dose Specification Medium Selection

*   **Key Issue:** MBDCAs calculate dose *in* a medium. Which medium should dose be reported *to*?
*   **Notation:** `Dx,y-Z`
    *   `x`: Dose specification medium (w=water, m=local medium)
    *   `y`: Transport medium (w=water, w/appl/air=water+applicators/air, m=heterogeneous medium)
    *   `Z`: Algorithm (TG43, MBDC)
*   **Common Options:**
    *   `Dw,w-TG43`: Standard TG-43 (dose to water in water).
    *   `Dm,m-MBDC` (`Dm,m`): Dose to local medium in heterogeneous medium.
    *   `Dw,m-MBDC` (`Dw,m`): Dose to water in heterogeneous medium.
*   **Relationship between Dm,m and Dw,m:**
    *   Related by stopping power ratios (electrons) or mass energy-absorption coefficient ratios (photons), depending on cavity size relative to electron range (Bragg-Gray, Spencer-Attix theory).
    *   **Large Cavity:** `Dw,m ≈ Dm,m * (μ_en/ρ)_w^m` (ratio of mass energy-absorption coeffs).
    *   **Small Cavity:** `Dw,m ≈ Dm,m * (L̄/ρ)_w^m` (ratio of restricted mass stopping powers).
    *   Differences are largest for LE sources in high-Z materials (e.g., bone).
*   **Recommendations (TG-186):**
    *   **Retain TG-43:** `Dw,w-TG43` remains the basis for prescription and primary reporting.
    *   **Parallel Reporting:** When MBDCA is used, report `Dm,m` alongside `Dw,w-TG43`.
    *   **Transport Medium:** Radiation transport should always be performed in the heterogeneous medium (`y=m`).
    *   **Reporting Medium:** Report dose *to the local medium* (`Dm,m`) as a minimum requirement for MBDCA.
    *   Reporting `Dw,m` is also informative but requires careful consideration of cavity theory validity, especially for LE sources.
*   **Areas of Research:** Better understanding of `Dw,m` calculation/interpretation, biological effect modeling.

## V. CT Imaging and Patient Modeling for MBDCA

*   **Challenge:** MBDCAs need accurate voxel-by-voxel material composition and density, but standard CT only provides Hounsfield Units (HU), related primarily to electron density (ρe) and effective atomic number (Zeff).
*   **A. Literature Review:**
    *   **Material Characterization:** HU depends on both ρe and Zeff. Single-energy CT cannot uniquely determine composition. Stoichiometric calibration relates HU to ρe and Zeff, but requires phantom scanning and is scanner/kVp dependent.
    *   **CT Segmentation:** Assigning materials based on HU ranges (thresholding) or more advanced methods (region growing, pattern recognition).
    *   **CBCT:** More scatter, less stable HU values than diagnostic CT. Requires specific calibration.
    *   **Dual Energy CT (DECT) / Spectral CT:** Can potentially separate ρe and Zeff contributions, improving material identification. Promising but not widely available/standardized for TPS.
    *   **CT Artifacts:** Beam hardening, scatter, metal artifacts (streaks, voids) significantly impact HU values and need correction/mitigation.
    *   **Other Modalities:** MRI useful for soft tissue delineation, PET for functional info, US for real-time guidance. Can supplement CT but don't directly provide MBDCA input.
*   **B. Recommendations (TG-186):**
    *   **1. Consensus Material Definitions:** To ensure uniformity, use a standardized set of materials with defined compositions and densities, assigned based on anatomical location and HU ranges.
        *   **Prostate:** Defined composition (ICRU/ICRP).
        *   **Breast:** Defined composition (distinguish adipose vs. fibroglandular if possible, otherwise use average).
        *   **Calcifications:** Treat as bone.
        *   **Other Tissues:** Use standard compositions (e.g., muscle, lung, bone) from ICRU/ICRP.
        *   **Applicators/Devices:** Use manufacturer-specified materials and densities. Model accurately.
    *   **2. Material Assignment Method:** Use CT HU-based segmentation with overrides based on anatomical knowledge.
        *   Create a site-specific HU-to-material lookup table based on phantom calibration or literature values.
        *   Manually contour and assign materials for critical structures (applicators, shields, target, OARs, air cavities, bone) where HU values may be ambiguous or artifact-prone.
        *   Use MRI/US to guide contouring where beneficial.
    *   **3. CT Artifact Removal:** Implement available correction methods. Manually correct obvious artifacts (e.g., assign water density to streaks in soft tissue).
*   **C. Areas of Research:** Improved tissue composition determination (DECT, spectral CT), advanced segmentation methods, robust artifact correction.

## VI. MBDCA Commissioning

*   **Challenge:** Cannot benchmark against measurements for every patient/applicator/source combination like TG-43.
*   **A. Literature Review:** Limited specific guidance for brachytherapy MBDCA commissioning.
*   **B. Recommendations (TG-186):** Two-level process.
    *   **Level 1: Reproduce TG-43:** Verify MBDCA can replicate TG-43 parameters (Λ, g(r), F(r,θ)) in a homogeneous water geometry. Use standard TG-43 source data.
        *   Confirms basic algorithm function and source model implementation.
    *   **Level 2: Test Advanced Capabilities:** Verify accuracy in heterogeneous conditions using benchmark cases.
        *   Use virtual phantom geometries with known materials (water, bone, lung, air, applicators) and source placements.
        *   Compare MBDCA results (`Dm,m` and/or `Dw,m`) against published MC data or independent calculations for these benchmarks.
        *   Test sensitivity to material assignment, CT calibration, grid size.
    *   **Workflow:**
        *   Import DICOM test cases (CT, RTSTRUCT, RTPLAN, RTDOSE).
        *   Perform Level 1 tests (TG-43 replication).
        *   Perform Level 2 tests (heterogeneity benchmarks).
        *   Verify CT calibration curve implementation.
        *   Select and consistently use dose scoring medium (recommend `Dm,m`).
*   **C. Areas of Research:** Standardized benchmark test cases, robust comparison metrics (e.g., gamma index adaptation for brachytherapy), phantom development for experimental validation.

## VII. Other Issues and Limitations

*   **A. Uncertainties:** MBDCAs introduce new uncertainties compared to TG-43:
    *   Algorithm approximations (discretization, cross-section data).
    *   CT calibration and HU-to-material conversion.
    *   Material composition inaccuracies.
    *   Artifacts.
    *   Overall uncertainty likely similar to or slightly larger than advanced EBRT algorithms (e.g., ~5% in target, higher near interfaces).
*   **B. Limitations:**
    *   Computational time (especially MC).
    *   Dependence on accurate CT imaging and material assignment.
    *   Lack of robust biological effect modeling correlated with `Dm,m` or `Dw,m`.
    *   Need for specific commissioning and QA.
*   **C. Considerations for Changing Prescriptions:**
    *   **DO NOT change clinical prescriptions based solely on MBDCA results initially.**
    *   Report MBDCA doses (`Dm,m`) alongside standard TG-43 doses.
    *   Accumulate clinical experience correlating MBDCA doses with outcomes.
    *   Future prescription changes should be based on clinical evidence, potentially through cooperative group trials comparing TG-43 vs. MBDCA-based planning.
    *   The magnitude of difference between TG-43 and MBDCA depends heavily on site, energy, and presence of heterogeneities.

## VIII. Conclusions & Final Recommendations

*   MBDCAs offer significant accuracy improvements over TG-43 by accounting for heterogeneities.
*   **Clinical Implementation:** Adopt MBDCAs cautiously.
    *   **Continue using `Dw,w-TG43` for prescription and primary dose reporting.**
    *   **Perform MBDCA calculations in parallel.**
    *   **Transport radiation in the heterogeneous medium (`y=m`).**
    *   **Report `Dm,m` (dose to local medium) alongside `Dw,w-TG43`.**
    *   Use standardized material assignments (Sec V.B).
    *   Perform rigorous two-level commissioning (Sec VI.B).
*   Transitioning prescriptions requires clinical data correlating MBDCA doses with outcomes.
*   Further research needed in material characterization, segmentation, artifact correction, biological modeling, and benchmark development.

*Disclaimer: This deep dive summarizes key aspects of AAPM TG-186. Users should always refer to the original report for complete details, data tables, and context.*
