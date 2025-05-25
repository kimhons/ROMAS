# Assessment Rubric: Section 1.2 - Dosimeter Design, Characteristics, Application, and QA

**Total Points:** 100

**Grading Distribution:**
*   Part 1: Detector Types and Characteristics (2 MCQ @ 4pts, 3 SA @ 6pts) = 26 points
*   Part 2: Detector Applications (4 SA @ 5pts, 1 SA @ 4pts) = 24 points
*   Part 3: Quality Assurance (TG-142, TG-69) (2 MCQ @ 4pts, 3 SA @ 6pts) = 26 points
*   Part 4: Specific Considerations (TG-106, TG-235, TG-218/219) (4 SA @ 5pts, 1 SA @ 4pts) = 24 points

---

## Part 1: Detector Types and Characteristics (26 Points Total)

**1, 2. Multiple Choice Questions (4 points each):**
*   Scoring: 4 points for each correct answer, 0 points for incorrect.
*   Answers:
    1.  c) Thimble Ionization Chamber (e.g., Farmer type)
    2.  c) Over-response due to increased low-energy scattered photons

**3, 4, 5. Short Answers (6 points each):**
*   **General Criteria:**
    *   **6 Points (Excellent):** Accurate, complete, clearly explained, uses appropriate terminology.
    *   **4-5 Points (Good):** Mostly accurate/complete, minor omissions/lack of clarity.
    *   **2-3 Points (Fair):** Addresses question but significant inaccuracies/omissions/lack of clarity.
    *   **1 Point (Poor):** Largely inaccurate/incomplete/irrelevant, but shows some attempt.
    *   **0 Points (Unacceptable):** Inaccurate, irrelevant, or missing.
*   **Specific Guidance:**
    *   **Q3 (MOSFET):** Principle: Radiation creates electron-hole pairs in SiO₂, trapping charge and shifting threshold voltage. Voltage shift is proportional to dose. Application: In vivo dosimetry (surface dose, intracavitary), QA.
    *   **Q4 (Dose Rate Dependence):** Define as the variation in detector sensitivity (reading per unit dose) as the dose rate changes. Mention potential causes (e.g., ion recombination in ion chambers, saturation effects).
    *   **Q5 (Volume Averaging):** Explain it occurs when detector size is significant relative to dose gradient. The reading represents average dose over the volume, potentially underestimating peaks and broadening penumbra. More significant with larger detectors in high gradient regions.

---

## Part 2: Detector Applications (24 Points Total)

**6, 7, 8, 9. Short Answers (5 points each):**
*   **General Criteria:**
    *   **5 Points (Excellent):** Accurate, complete, clearly explained.
    *   **4 Points (Good):** Mostly accurate/complete, minor omissions/lack of clarity.
    *   **3 Points (Fair):** Addresses question but significant inaccuracies/omissions.
    *   **1-2 Points (Poor):** Largely inaccurate/incomplete/irrelevant.
    *   **0 Points (Unacceptable):** Missing or irrelevant.
*   **Specific Guidance:**
    *   **Q6 (TG-61 kV Detector):** Free-air chamber (primary standard) or cross-calibrated plane-parallel/thimble chamber designed for low energies. Why: Minimal perturbation, accurate measurement of air kerma at low energies where electron equilibrium is not established in medium.
    *   **Q7 (Film Advantages/Disadvantages):** Advantages: High spatial resolution, 2D information, tissue equivalence (radiochromic). Disadvantage: Dose range limitations, sensitivity to handling/environment, requires careful calibration/scanning protocol, not real-time.
    *   **Q8 (OSLDs):** Principle: Radiation traps electrons in crystal lattice (e.g., Al₂O₃:C). Light stimulation releases trapped electrons, causing luminescence proportional to dose. Difference from TLD: Light stimulation instead of heat, allows for re-reading (non-destructive readout).
    *   **Q9 (In Vivo Dosimetry):** Purpose: To measure dose delivered to patient during treatment for verification or monitoring. Detector examples: Diodes, MOSFETs, OSLDs, TLDs.

**10. Short Answer (4 points):**
*   **General Criteria:**
    *   **4 Points (Excellent):** Accurate, concise, and directly addresses the question.
    *   **3 Points (Good):** Mostly accurate, minor omissions or lack of clarity.
    *   **2 Points (Fair):** Addresses question partially or with some inaccuracies.
    *   **1 Point (Poor):** Largely inaccurate or irrelevant.
    *   **0 Points (Unacceptable):** Missing or irrelevant.
*   **Specific Guidance:**
    *   **Q10 (EPID Principle):** Incident high-energy photons interact with metal plate/phosphor screen, producing light photons. Light photons are detected by photodiodes in the amorphous silicon array, generating charge proportional to incident fluence.

---

## Part 3: Quality Assurance (TG-142, TG-69) (26 Points Total)

**11, 15. Multiple Choice Questions (4 points each):**
*   Scoring: 4 points for each correct answer, 0 points for incorrect.
*   Answers:
    11. d) Annually (or per ADCL calibration cycle) - Note: Constancy implies comparison to baseline, often checked more frequently (e.g., monthly/quarterly) but full recalibration is annual/per ADCL.
    15. ±1 mm

**12, 13, 14. Short Answers (6 points each):**
*   **General Criteria:** (Same as Part 1 Short Answers)
*   **Specific Guidance:**
    *   **Q12 (Leakage Test):** Apply bias voltage, measure charge collected over time (e.g., 1-5 min) *without* radiation. Acceptable level (TG-374): < 0.1% of expected measurement signal.
    *   **Q13 (TG-142 Imaging QA):** List any two: Geometric distortion, spatial resolution, contrast/contrast-to-noise ratio (CNR), uniformity, scaling accuracy, radiation dose.
    *   **Q14 (TG-69 HDR QA Check):** Check for integrity/damage/obstructions in guide tubes and secure connection to applicator. Why: Ensure smooth source transit and accurate positioning, prevent source getting stuck.

---

## Part 4: Specific Considerations (TG-106, TG-235, TG-218/219) (24 Points Total)

**16, 17, 19, 20. Short Answers (5 points each):**
*   **General Criteria:** (Same as Part 2 Short Answers)
*   **Specific Guidance:**
    *   **Q16 (TG-106 Detector Selection):** Large detectors cause significant volume averaging in high gradient regions like penumbra, leading to inaccurate profile measurement (broadened penumbra).
    *   **Q17 (TG-235 Small Field Challenges):** List any two: Lack of lateral charged particle equilibrium (LCPE), source occlusion, detector volume averaging, difficulty in precise positioning.
    *   **Q19 (TG-218/219 Multiple Detectors):** Different detectors have different strengths/weaknesses. Arrays provide efficient 2D comparison but may lack resolution or have angular dependence. Film offers high resolution but has handling/calibration challenges. Point measurements (chamber) provide accuracy at specific points. Combining methods gives a more complete picture.
    *   **Q20 (Gamma Analysis):** Compares measured dose distribution to calculated dose distribution. Criteria: 3% dose difference (DD) and 3mm distance-to-agreement (DTA). It evaluates if points in the measured distribution have a corresponding point in the calculated distribution within both the DD and DTA criteria.

**18. Short Answer (4 points):**
*   **General Criteria:** (Same as Part 2 Q10 Short Answer)
*   **Specific Guidance:**
    *   **Q18 (TG-235 Small Field Detectors):** Recommended: Micro-ionization chambers, small diodes (corrected), diamond detectors, scintillators, radiochromic film. Unsuitable: Standard Farmer-type chambers, large diodes (uncorrected), standard parallel-plate chambers (due to volume/perturbation).

---

*(Note: This rubric provides a framework. Specific point allocations and criteria can be adjusted based on instructional emphasis.)*
