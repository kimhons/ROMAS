# Section 4.6: Worked Examples for Activities - TBI & TSEI

This document provides detailed solutions and explanations for the activities presented in `activities_4_6.md`.

## Worked Example for Activity 1: TBI Dose Calculation and IVD Analysis

*   **Given Data:**
    *   Prescription: 12 Gy in 6 fractions (200 cGy/fraction) to midline umbilicus.
    *   Technique: AP/PA extended SSD.
    *   Calibrated Dose Rate (Ref): 15.0 cGy/MU.
    *   Umbilicus Separation: 30 cm (Midline depth = 15 cm).
    *   TPR(15 cm): 0.750.
    *   Off-Axis Factor (OAF): 1.00.
    *   Compensator Transmission Factor (CompF): 0.95.
    *   Spoiler Factor (SpF): 1.03.

*   **Task 1: Calculate MU per field (AP/PA, equal weight).**
    *   Dose per field to midline = (Total Dose per fraction) / 2 = 200 cGy / 2 = 100 cGy.
    *   The dose delivered to the midline point per MU under treatment conditions is:
        *   Dose/MU = Ref_Dose_Rate * TPR * OAF * CompF * SpF
        *   Dose/MU = 15.0 cGy/MU * 0.750 * 1.00 * 0.95 * 1.03
        *   Dose/MU ≈ 11.00 cGy/MU
    *   MU per field = (Dose per field) / (Dose/MU)
    *   MU per field = 100 cGy / 11.00 cGy/MU
    *   **MU per field ≈ 9.09 MU** (Practical MU would likely be rounded, e.g., 9 MU or adjusted based on specific clinic rounding protocols).

*   **Task 2: Analyze anterior surface IVD.**
    *   Expected Dose (Ant Surface): 225 cGy.
    *   Measured Dose (Ant Surface): 208 cGy.
    *   Percentage Difference = [(Measured - Expected) / Expected] * 100%
    *   Percentage Difference = [(208 - 225) / 225] * 100%
    *   Percentage Difference = [-17 / 225] * 100%
    *   **Percentage Difference ≈ -7.6%**

*   **Task 3: Analyze lung block IVD.**
    *   Expected Dose (Mid-Lung): 70 cGy.
    *   Estimated Measured Dose (Mid-Lung): 85 cGy.
    *   Percentage Difference = [(Measured - Expected) / Expected] * 100%
    *   Percentage Difference = [(85 - 70) / 70] * 100%
    *   Percentage Difference = [15 / 70] * 100%
    *   **Percentage Difference ≈ +21.4%**

*   **Task 4: Actions and Discussion.**
    *   **Anterior Surface (-7.6%):** This is within a typical ±10% tolerance. Potential causes could include slight variations in patient setup (e.g., slightly larger separation than planned), minor compensator positioning shift, or inherent measurement uncertainty. Action: Monitor in subsequent fractions. If consistently low, consider minor MU adjustment or re-evaluate setup/compensation.
    *   **Lung Dose (+21.4%):** This is significantly higher than expected and exceeds typical tolerances (often ±10% or ±15% for critical organs). This requires immediate investigation.
        *   **Potential Causes:**
            *   Incorrect lung block placement (most likely). The block might have shifted, exposing more lung tissue.
            *   Incorrect block design or fabrication (wrong thickness/material).
            *   Error in IVD placement or dose estimation from surface measurement.
            *   Significant change in patient anatomy/position affecting scatter or transmission.
        *   **Actions:**
            1.  **STOP Treatment:** Do not proceed with the next fraction until resolved.
            2.  **Verify Block Position:** Review daily portal images meticulously. If shifted, correct placement before next treatment.
            3.  **Verify Block Design/Transmission:** Re-measure block transmission if placement seems correct.
            4.  **Review IVD:** Check IVD calibration, placement, and calculation used to estimate mid-lung dose.
            5.  **Re-simulate/Re-plan:** If block position/design is incorrect and cannot be easily rectified, re-simulation and re-planning might be necessary.
            6.  **Consultation:** Discuss findings with the radiation oncologist immediately.

## Worked Example for Activity 2: TSEI Uniformity Assessment and Boost Planning

*   **Given Data:**
    *   Prescription: 36 Gy total (1 Gy/fraction).
    *   IVD Results (Dose per Fraction):
        *   Scalp Vertex: 65 cGy
        *   Sole of Foot: 55 cGy
        *   Perineum: 60 cGy
        *   Inframammary Fold: 75 cGy
        *   Other points: 95-105 cGy

*   **Task 1: Identify underdosed areas (< 85% of 100 cGy).**
    *   85% of 100 cGy = 85 cGy.
    *   **Underdosed Areas:** Scalp Vertex (65 cGy), Sole of Foot (55 cGy), Perineum (60 cGy), Inframammary Fold (75 cGy).

*   **Task 2: Calculate required boost dose.**
    *   Total Prescribed Dose = 3600 cGy.
    *   **Scalp Vertex:**
        *   Estimated total dose from main fields = 65 cGy/fx * 36 fx = 2340 cGy.
        *   Required Boost Dose = 3600 cGy - 2340 cGy = **1260 cGy**.
    *   **Sole of Foot:**
        *   Estimated total dose = 55 cGy/fx * 36 fx = 1980 cGy.
        *   Required Boost Dose = 3600 cGy - 1980 cGy = **1620 cGy**.
    *   **Perineum:**
        *   Estimated total dose = 60 cGy/fx * 36 fx = 2160 cGy.
        *   Required Boost Dose = 3600 cGy - 2160 cGy = **1440 cGy**.
    *   **Inframammary Fold:**
        *   Estimated total dose = 75 cGy/fx * 36 fx = 2700 cGy.
        *   Required Boost Dose = 3600 cGy - 2700 cGy = **900 cGy**.
    *   *Note:* Boost doses are often prescribed in easily deliverable fractions (e.g., 200 cGy/fx) towards the end of the main treatment course.

*   **Task 3: Outline boost planning steps.**
    1.  **Simulation:** Patient simulated specifically for boost fields. Areas clearly marked. Appropriate electron energy selected based on depth required (often similar or slightly higher energy than main TSEI fields, e.g., 6-9 MeV). Bolus may be used to ensure surface dose.
    2.  **Field Definition:** Appropriate electron applicator/cone size chosen to cover the target area with margin. Field shape may be defined using standard inserts or custom cutouts.
    3.  **Setup:** Patient positioned reproducibly (often supine/prone). Setup verified (e.g., using light field, SSD check).
    4.  **MU Calculation:** Dose per MU determined for the specific energy, applicator, and SSD. MU calculated to deliver the required boost dose (often delivered over several fractions).
    5.  **QA:** Independent MU calculation check. Verification of field size, shape, energy, and setup before first boost fraction.

*   **Task 4: Physics reasons for underdosing.**
    *   **Scalp Vertex:** Beam incidence is highly oblique (near tangential) from the angled Stanford fields, leading to reduced surface dose and increased penetration before dmax is reached.
    *   **Soles of Feet:** Patient standing on the floor/platform; limited direct irradiation and scatter contribution from below.
    *   **Perineum:** Significant self-shielding by the thighs and torso, especially depending on patient stance.
    *   **Skin Folds (Inframammary, Axillae, Groin):** Self-shielding by overlapping tissue; beam enters at oblique angles.

## Worked Example for Activity 3: Designing a QA Checklist for TBI

*(This requires creating a structured checklist. Below is an example outline, not exhaustive.)*

**TBI QA Checklist (Extended SSD AP/PA Technique)**

**A. Pre-Treatment Machine QA (Frequency: Annually/Commissioning & Pre-Program Start)**
    *   [ ] Output Calibration @ Extended SSD (e.g., 400 cm) in Ref Phantom (Tolerance: ±2%)
    *   [ ] Field Size Indicator Accuracy @ Extended SSD (Tol: ±2 mm)
    *   [ ] Light/Radiation Field Coincidence @ Extended SSD (Tol: ±3 mm)
    *   [ ] Beam Profile Uniformity (Large Field @ Ext SSD) (Tol: ±3% or 5%)
    *   [ ] Beam Energy Constancy (PDD/TPR Check @ Ext SSD) (Tol: ±1% in depth)
    *   [ ] Gantry/Collimator Angle Accuracy (Tol: ±0.5 deg)
    *   [ ] ODI Accuracy @ Extended SSD (Tol: ±2 mm)
    *   [ ] Safety Interlocks (Door, Collision, Timer) Verification
    *   [ ] Spoiler Integrity and Positioning Verification

**B. Patient-Specific Planning QA (Frequency: Per Patient, Before First Tx)**
    *   [ ] Independent MU Calculation Check (Tol: ±3-5%)
    *   [ ] Compensator Design/Material/Thickness Verification
    *   [ ] Compensator Transmission Factor Check (Calculated vs Measured) (Tol: ±2%)
    *   [ ] Lung Block Design/Material/Thickness Verification
    *   [ ] Lung Block Transmission Factor Check (Tol: ±2%)
    *   [ ] IVD Dose Prediction Calculation Check
    *   [ ] Plan Review (Prescription, Constraints, Isocenter, Field Arrangement)

**C. Daily Treatment Delivery QA (Frequency: Each Treatment Day/Fraction)**
    *   [ ] Linac Output Constancy Check (Standard QA device) (Tol: ±3%)
    *   [ ] Patient Identification Verification (2 methods)
    *   [ ] Patient Positioning/Immobilization Verification
    *   [ ] SSD/Distance Verification (ODI/Manual Check)
    *   [ ] Field Size Verification
    *   [ ] Gantry/Collimator Angle Verification
    *   [ ] Compensator Placement Verification
    *   [ ] Spoiler Placement Verification
    *   [ ] Lung Block Placement Verification (Portal Image Review - Mandatory)
    *   [ ] IVD Placement Verification (Correct locations, secure attachment)
    *   [ ] MU Setting Verification (vs Plan)
    *   [ ] Beam On/Off Observation
    *   [ ] Treatment Console Record Verification
    *   [ ] IVD Reading/Recording (Post-Tx)
    *   [ ] Physics Review of IVD Results (Before next fraction if possible, mandatory if outside tolerance)

## Worked Example for Activity 4: Clinical Decision Making - TBI Toxicity

*   **Scenario:** TBI patient develops cough/shortness of breath after 4/6 fractions.
*   **Differential Diagnoses:**
    *   **Early Radiation Pneumonitis:** While typically occurring weeks/months later, severe early reactions are possible, especially with risk factors.
    *   **Infection:** Bacterial or viral pneumonia (patient is immunosuppressed).
    *   **Fluid Overload:** Can occur due to hydration/medications.
    *   **Chemotherapy Effect:** Some chemo agents used in conditioning can cause pulmonary symptoms.
    *   **Underlying Disease:** Progression or complication related to leukemia/lymphoma.
*   **Immediate Steps:**
    1.  **Clinical Assessment:** Detailed history, vital signs, lung auscultation.
    2.  **Imaging:** Chest X-ray (CXR) STAT. Consider CT chest if CXR inconclusive.
    3.  **Labs:** CBC, blood cultures, sputum culture (if productive cough), inflammatory markers (CRP).
    4.  **Oxygenation:** Check O2 saturation; provide supplemental O2 if needed.
    5.  **Consultation:** Inform radiation oncologist and transplant physician immediately.
*   **Effect on TBI:**
    *   **HOLD Treatment:** TBI should likely be held pending investigation.
    *   **Diagnosis Dependent:** If infection is confirmed and treated, TBI might resume cautiously. If early severe pneumonitis is suspected, continuing TBI is extremely high risk and may need to be aborted or significantly modified (unlikely).
*   **Role of Shielding/IVD:**
    *   **IVD Review:** Immediately review IVD results for lung dose under blocks from previous fractions. Doses significantly exceeding tolerance (>10-15% high) would increase suspicion for radiation-induced cause.
    *   **Shielding Review:** Review daily portal images to confirm block placement was accurate for previous fractions.

## Worked Example for Activity 5: Clinical Decision Making - TSEI Toxicity

*   **Scenario:** TSEI patient develops confluent moist desquamation in axillae/groin after 20/36 fractions.
*   **Management Strategy:**
    1.  **Assessment:** Examine affected areas, assess extent and severity, check for signs of infection (pus, odor, increased pain/redness).
    2.  **Skin Care:**
        *   Gentle cleansing with lukewarm water and mild soap (or saline rinses).
        *   Pat dry gently.
        *   Apply non-adherent dressings (e.g., Mepitel, Adaptic) directly to moist areas.
        *   Consider hydrogel dressings for soothing effect.
        *   Use absorbent secondary dressings if needed.
        *   Avoid friction/trauma to the area.
        *   Topical antibiotics (e.g., silver sulfadiazine, bacitracin) ONLY if infection is suspected/confirmed.
    3.  **Symptom Control:** Pain medication if needed.
*   **Treatment Interruption:**
    *   Generally, treatment can continue if moist desquamation is localized and managed appropriately.
    *   Consider a short break (e.g., 2-3 days) ONLY if reaction is extremely severe, widespread, painful, or shows signs of infection, to allow for initial healing.
    *   Prolonged breaks are discouraged as they reduce treatment efficacy.
*   **Patient Advice:**
    *   Wear loose-fitting, soft clothing (cotton).
    *   Avoid harsh soaps, lotions, perfumes, deodorants in treated areas.
    *   Keep areas clean and dry between dressing changes.
    *   Report any signs of infection immediately.
*   **Predisposing Factors:** Skin folds (friction, moisture), obesity, prior skin conditions, possibly higher dose inhomogeneity in those areas.

