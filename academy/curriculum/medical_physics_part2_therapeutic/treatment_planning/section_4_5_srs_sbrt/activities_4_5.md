# Section 4.5: Activities & Worked Examples - SRS/SBRT

*(Note: These activities and examples are designed to reinforce the concepts presented in Section 4.5, encouraging practical application of physics and clinical principles.)*

## Activity 1: Evaluating Immobilization and IGRT Strategy

*   **Scenario:** A clinic is implementing frameless linac-based SRS for brain metastases using a thermoplastic mask system and CBCT for IGRT.
*   **Task:**
    1.  Outline the key QA procedures necessary to commission and maintain the geometric accuracy of the CBCT system specifically for SRS, referencing relevant TG reports (e.g., TG-142, TG-179 principles).
    2.  Describe a method to quantify the residual setup uncertainty associated with the thermoplastic mask system in your clinic.
    3.  Based on the quantified uncertainty and CBCT system accuracy, propose an appropriate PTV margin for GTV-to-PTV expansion for single-fraction SRS, justifying your choice.
    4.  Discuss the potential limitations of using CBCT alone for IGRT in cranial SRS compared to systems with kV orthogonal imaging or frame-based localization.

## Worked Example 1: Calculating PTV Margin Based on Uncertainties

*   **Problem:** A clinic characterizes its frameless SRS system. CBCT geometric accuracy (including registration) is determined to be 0.5 mm (standard deviation, SD). Residual setup uncertainty with the mask system after CBCT correction is measured to be 0.7 mm (SD). Assuming Gaussian distributions and aiming for 95% coverage (requiring ~1.645 * SD for systematic and 0.84 * SD for random, or using simpler margin recipes like Van Herk: 2.5Σ + 0.7σ).
*   **Simplified Margin Calculation (Illustrative - using a common recipe):**
    *   Assume uncertainties are primarily random for simplicity in this example (a more rigorous approach would separate systematic Σ and random σ components).
    *   Total uncertainty (σ_total) can be estimated by adding variances in quadrature: σ_total² = σ_IGRT² + σ_setup²
    *   σ_total² = (0.5 mm)² + (0.7 mm)² = 0.25 mm² + 0.49 mm² = 0.74 mm²
    *   σ_total = √0.74 mm² ≈ 0.86 mm
    *   Using a simplified margin recipe (e.g., Margin ≈ 2.5 * σ_total for 90% population coverage, though specific recipes vary):
    *   Margin ≈ 2.5 * 0.86 mm ≈ 2.15 mm
*   **Proposed Margin:** Based on this simplified calculation, a PTV margin of 2.0 to 2.5 mm might be considered. A more formal calculation using established margin recipes (like Van Herk) considering systematic and random components separately would be required in clinical practice.
*   **Discussion:** This margin accounts for the measured uncertainties in image guidance and patient setup reproducibility. If uncertainties were larger, a larger margin would be needed, potentially increasing dose to normal brain tissue. This highlights the importance of minimizing uncertainties through rigorous QA and effective immobilization.

## Activity 2: Spine SBRT Plan Evaluation

*   **Scenario:** You are presented with an SBRT plan for a T9 vertebral metastasis prescribed 27 Gy in 3 fractions.
*   **Provided Data (Hypothetical):**
    *   PTV (covers T9 vertebral body): D95% = 27.5 Gy (102%), Dmax = 32 Gy (118%)
    *   Spinal Cord PRV (Cord + 2mm): Dmax = 20.1 Gy, V18Gy = 0.05 cc
    *   Esophagus: Dmax = 25 Gy
*   **Task:**
    1.  Evaluate the PTV coverage. Is it acceptable?
    2.  Evaluate the dose to the Spinal Cord PRV based on common constraints (e.g., RTOG 0631 constraints suggest Cord PRV Dmax < 18 Gy and V18Gy < 0.1 cc for 27 Gy/3fx). Is the plan acceptable regarding cord dose?
    3.  Evaluate the dose to the Esophagus (common constraints might be Dmax < 27-30 Gy in 3 fx). Is this acceptable?
    4.  If the cord dose is unacceptable, suggest specific planning strategies the dosimetrist could employ to reduce it while maintaining adequate PTV coverage.

## Worked Example 2: Evaluating Spine SBRT Cord Dose

*   **Problem:** Using the data from Activity 2, evaluate the spinal cord dose.
*   **Evaluation:**
    *   **Constraint Check (Example based on RTOG 0631):**
        *   Cord PRV Dmax Constraint: < 18 Gy
        *   Plan Cord PRV Dmax: 20.1 Gy
        *   **Result:** Constraint VIOLATED.
        *   Cord PRV V18Gy Constraint: < 0.1 cc
        *   Plan Cord PRV V18Gy: 0.05 cc
        *   **Result:** Constraint MET.
*   **Conclusion:** The plan is unacceptable due to the maximum point dose to the Spinal Cord PRV exceeding the critical tolerance limit, despite the volume constraint being met. This carries an unacceptable risk of radiation myelopathy.
*   **Recommendations:** The plan must be revised. Strategies include:
    *   Tightening MLC margins around the Cord PRV.
    *   Adding avoidance sectors or optimizing beam angles.
    *   Potentially accepting slightly less PTV coverage immediately adjacent to the cord if necessary (requires physician approval).
    *   Re-evaluating the PTV margin near the cord.
*   **Street Wisdom:** Spinal cord dose limits in SBRT are absolute. There is no room for compromise. Even small volumes exceeding point dose tolerances can be dangerous. Always verify constraints against established protocols.

## Activity 3: Small Field Output Factor Measurement

*   **Scenario:** Commissioning a linac for SRS requires measuring output factors for small fields (e.g., 1x1 cm, 2x2 cm) relative to a reference field (10x10 cm).
*   **Task:**
    1.  Choose two different detector types suitable for small field measurements (e.g., a shielded stereotactic diode and radiochromic film).
    2.  Describe the setup for measuring the output factor for a 1x1 cm field using *each* detector, including phantom type, SSD/SCD, and alignment procedures.
    3.  Discuss the potential sources of error and necessary corrections for *each* detector type when measuring small field output factors (consider volume averaging, energy dependence, perturbations, etc.).
    4.  Explain why the raw measured output factor might differ between the two detectors and how these differences are typically reconciled using correction factors (k-factors based on TRS-483/TG-155 principles).

## Worked Example 3: Applying Small Field Correction Factor (Illustrative)

*   **Problem:** A shielded diode measures a raw reading ratio (1x1 cm field / 10x10 cm field) of 0.750. Monte Carlo simulations (or published data for this specific diode and beam quality) provide a correction factor (k_Qclin,Qref^fclin,fref) of 1.030 for this 1x1 cm field relative to the 10x10 cm reference field.
*   **Calculation:**
    *   Corrected Output Factor = Measured Ratio * Correction Factor (k)
    *   Corrected Output Factor = 0.750 * 1.030 = 0.7725
*   **Interpretation:** The raw diode reading underestimated the true output factor due to detector-specific effects in the small field relative to the reference field. Applying the appropriate correction factor provides a more accurate value for use in the TPS beam model.
*   **Discussion:** This highlights the necessity of using detector-specific correction factors, derived from reliable sources (like Monte Carlo or consensus data like TRS-483), when performing small field dosimetry. Using uncorrected measurements can lead to significant errors in dose calculation for SRS/SBRT.

## Activity 4: 4D-CT Analysis and Motion Management Choice

*   **Scenario:** A patient with a peripheral lung lesion undergoes 4D-CT.
*   **Provided Data (Hypothetical):**
    *   Maximum SI motion observed: 2.5 cm
    *   Maximum AP/LR motion: 0.6 cm
    *   Respiratory trace shows irregular breathing pattern with variable amplitude.
    *   Correlation between external surrogate and internal tumor motion appears unstable on initial assessment.
*   **Task:**
    1.  Evaluate the suitability of different motion management strategies (ITV, Gating, Tracking, Breath-Hold, Compression) for this patient, discussing the pros and cons of each based on the observed motion characteristics.
    2.  If an ITV approach were chosen, estimate the approximate PTV size in the SI dimension assuming a 5 mm isotropic margin is added to the ITV.
    3.  If gating were considered, what further investigations or actions would be needed given the irregular breathing and unstable surrogate correlation?
    4.  Discuss the potential impact of the interplay effect if a VMAT plan is used with gating for this patient.

