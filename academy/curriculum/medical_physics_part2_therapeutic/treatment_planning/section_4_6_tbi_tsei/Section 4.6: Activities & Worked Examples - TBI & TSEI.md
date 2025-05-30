# Section 4.6: Activities & Worked Examples - TBI & TSEI

This document outlines activities designed to reinforce the understanding of physics and clinical concepts related to Total Body Irradiation (TBI) and Total Skin Electron Irradiation (TSEI). Corresponding worked examples or detailed solutions are provided in the `worked_examples_4_6.md` document.

## Activity 1: TBI Dose Calculation and IVD Analysis

*   **Scenario:** A clinic uses an AP/PA extended SSD technique for TBI (12 Gy in 6 fractions prescribed to midline umbilicus). The calibrated dose rate at the treatment distance (midline umbilicus depth, dmax) under reference conditions (large phantom, spoiler) is 15.0 cGy/MU.
*   **Patient Data:**
    *   AP/PA separation at umbilicus: 30 cm
    *   Tissue Phantom Ratio (TPR) at 15 cm depth (for midline): 0.750
    *   Off-axis factor at umbilicus position: 1.00
    *   Compensator transmission factor (average): 0.95
    *   Spoiler factor: 1.03
    *   Prescribed dose per fraction: 200 cGy to midline umbilicus.
*   **Tasks:**
    1.  Calculate the total Monitor Units (MU) required per field (AP and PA, assuming equal weighting initially) to deliver the prescribed dose per fraction to the midline umbilicus. Show your calculation steps.
    2.  During the first fraction, IVD diodes are placed. The expected dose to a diode on the anterior surface at the umbilicus level is 225 cGy. The measured dose is 208 cGy. Calculate the percentage difference.
    3.  The expected dose under the lung block (mid-lung depth equivalent) is 70 cGy per fraction. The IVD measurement on the surface over the lung (under the block) corresponds to an estimated mid-lung dose of 85 cGy. Calculate the percentage difference.
    4.  Based on the IVD results in tasks 2 & 3, what actions, if any, should be considered by the physics team before the next fraction? Discuss the potential causes for these discrepancies.

## Activity 2: TSEI Uniformity Assessment and Boost Planning

*   **Scenario:** A patient is undergoing TSEI using the 6-field Stanford technique (36 Gy total dose, 1 Gy/fraction). Initial IVD (TLD) measurements are taken during the first fraction.
*   **IVD Results (Selected Points, Dose per Fraction):**
    *   Forehead: 102 cGy
    *   Anterior Chest: 98 cGy
    *   Anterior Abdomen: 105 cGy
    *   Anterior Shin: 95 cGy
    *   Scalp Vertex: 65 cGy
    *   Posterior Neck: 101 cGy
    *   Upper Back: 99 cGy
    *   Sole of Foot: 55 cGy
    *   Perineum (estimated): 60 cGy
    *   Inframammary Fold: 75 cGy
*   **Tasks:**
    1.  Identify the areas that are significantly underdosed based on a typical tolerance level (e.g., < 85% of prescribed dose/fraction).
    2.  Calculate the total additional dose required for each significantly underdosed area to bring the total dose closer to the prescription of 36 Gy by the end of treatment.
    3.  Outline the steps involved in planning and delivering electron boost fields to these underdosed areas (e.g., simulation, energy selection, field size, setup, MU calculation, QA).
    4.  Discuss the physics reasons why these specific areas (scalp, soles, perineum, folds) are prone to underdosing in the Stanford TSEI technique.

## Activity 3: Designing a QA Checklist for TBI

*   **Scenario:** Your clinic is implementing a new TBI program using an extended SSD AP/PA technique.
*   **Task:** Develop a comprehensive QA checklist covering pre-treatment machine QA, patient-specific planning QA, and daily treatment delivery QA for TBI. Base your checklist on the recommendations in AAPM Report 17 and general physics principles. Include specific items to check, tolerances (where applicable), and frequency.
    *   *Hint:* Consider categories like Machine Output & Profiles, Dosimetry Systems, Planning System, Compensators/Blocks, Patient Setup, IVD, Documentation.

## Activity 4: Clinical Decision Making - TBI Toxicity

*   **Scenario:** A 40-year-old patient undergoing fractionated TBI (12 Gy/6 fx) develops a persistent non-productive cough and mild shortness of breath during the third day of treatment (after 4 fractions).
*   **Task:** Outline the potential differential diagnoses. What immediate steps should be taken by the clinical team? How might this affect the continuation of TBI? Discuss the role of lung shielding and IVD in assessing the situation.

## Activity 5: Clinical Decision Making - TSEI Toxicity

*   **Scenario:** A 70-year-old patient undergoing TSEI (36 Gy) develops confluent moist desquamation in the axillae and groin areas after 20 fractions.
*   **Task:** Describe the appropriate management strategy for this acute skin toxicity. Should TSEI treatment be interrupted? What advice should be given to the patient regarding skin care? Discuss factors that might predispose patients to more severe skin reactions.

