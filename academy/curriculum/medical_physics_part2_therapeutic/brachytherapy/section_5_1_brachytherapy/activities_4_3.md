# Activities: Section 4.3 - Brachytherapy Planning

This document provides activities designed to reinforce understanding and practical skills in brachytherapy planning.

## Activity 1: HDR GYN Plan Evaluation

*   **Objective:** Evaluate a sample HDR GYN brachytherapy plan against GEC-ESTRO recommendations.
*   **Materials:** Sample anonymized HDR GYN plan data (CT images, contours for HR-CTV, Bladder, Rectum, Sigmoid, final dose distribution, DVHs).
*   **Tasks:**
    1.  **Review Contours:** Assess the appropriateness of HR-CTV, Bladder, Rectum, and Sigmoid contours based on provided images.
    2.  **Assess Target Coverage:**
        *   Find the $D_{90}$ (dose covering 90%) for the HR-CTV from the DVH.
        *   Calculate the total EQD2 for the HR-CTV $D_{90}$, assuming prior EBRT of 45 Gy in 25 fractions and an $\alpha/\beta$ ratio of 10 Gy for the HR-CTV. Use the formula: $EQD2_{Total} = EQD2_{EBRT} + EQD2_{Brachy}$.
        *   Compare the total EQD2 $D_{90}$ to the GEC-ESTRO goal (e.g., 85-90 Gy₁₀).
    3.  **Assess OAR Sparing:**
        *   Find the $D_{2cc}$ (maximum dose to 2cc) for the Bladder, Rectum, and Sigmoid Colon from their respective DVHs.
        *   Calculate the total EQD2 for each OAR $D_{2cc}$, assuming prior EBRT of 45 Gy in 25 fractions and an $\alpha/\beta$ ratio of 3 Gy for these late-responding tissues.
        *   Compare the total EQD2 $D_{2cc}$ values to the GEC-ESTRO hard constraints (e.g., Bladder < 90 Gy₃, Rectum < 75 Gy₃, Sigmoid < 75 Gy₃).
    4.  **Evaluate Homogeneity:** Visually inspect the isodose distribution. Are there significant hot spots or cold spots within the HR-CTV? (Note: Homogeneity indices are less emphasized in GYN compared to target coverage and OAR sparing).
    5.  **Write Summary:** Summarize your findings. Does the plan meet the primary goals? Are there any areas of concern? What adjustments might be considered if goals are not met?

## Activity 2: LDR Prostate Seed Implant QA Check

*   **Objective:** Simulate performing key QA checks for an LDR prostate seed implant procedure.
*   **Scenario:** You are the physicist responsible for an upcoming I-125 prostate seed implant.
*   **Tasks:** Create a checklist outlining the essential physics QA steps you would perform, including timing (pre-implant, day of implant, post-implant). Include checks for:
    1.  **Source QA:** (e.g., Receipt verification, $S_K$ assay vs. certificate, leak testing, number of seeds).
    2.  **Equipment QA:** (e.g., TRUS calibration/functionality, stepper/template checks, needle checks).
    3.  **Pre-Plan QA:** (e.g., Independent check of volume study contours, seed arrangement, planned dosimetry metrics).
    4.  **Day of Implant QA:** (e.g., Patient identification, site verification, seed handling/accountability, final plan verification).
    5.  **Post-Implant Dosimetry QA:** (e.g., CT scan protocol, seed localization accuracy check, contouring verification, independent check of calculated $D_{90}$, $V_{100}$, OAR doses).

## Activity 3: TG-43 Parameter Investigation

*   **Objective:** Understand how different TG-43 parameters influence the dose distribution.
*   **Materials:** Access to a brachytherapy TPS or spreadsheet software capable of basic TG-43 calculations (using provided sample data for $\Lambda$, $g_L(r)$, $F(r, \theta)$ for a hypothetical source).
*   **Tasks:** For a single point source with a given $S_K$:
    1.  **Effect of $\Lambda$:** Calculate the dose rate at the reference point (1 cm, 90°) using two different (hypothetical) values of $\Lambda$. How does $\Lambda$ scale the dose rate?
    2.  **Effect of $g_L(r)$:** Calculate the dose rate at r = 2 cm, 5 cm, and 10 cm along the transverse axis (θ=90°). Compare this to a pure $1/r^2$ fall-off from the dose rate at 1 cm. How does $g_L(r)$ modify the dose fall-off?
    3.  **Effect of $F(r, \theta)$:** Calculate the dose rate at r = 3 cm for angles θ = 0°, 45°, and 90°. How does the anisotropy function affect the dose rate away from the transverse plane?
    4.  **Summarize:** Briefly explain the physical meaning and impact of each parameter ($\\Lambda$, $g_L(r)$, $F(r, \theta)$) on the final dose calculation.

## Activity 4: HDR Dwell Time Optimization Concepts

*   **Objective:** Understand the basic principles behind HDR dwell time optimization.
*   **Scenario:** Consider a single straight catheter placed through a target volume, with several potential dwell positions along its length. Dose constraints are defined for the target surface and a nearby OAR.
*   **Tasks (Conceptual):**
    1.  **Uniform Dwell Times:** If all dwell positions have the same dwell time, where would the dose be highest? Where would it be lowest relative to the catheter?
    2.  **Optimizing for Target Coverage:** How would you adjust dwell times to make the dose more uniform along the length of the target near the catheter? (Hint: Consider the ends vs. the middle).
    3.  **Optimizing for OAR Sparing:** If an OAR is close to one end of the catheter, how would you adjust dwell times near that end to reduce the OAR dose, potentially at the expense of some target dose in that immediate vicinity?
    4.  **Inverse Planning:** Briefly describe how an inverse planning algorithm like IPSA automates this process based on user-defined dose objectives and constraints.


