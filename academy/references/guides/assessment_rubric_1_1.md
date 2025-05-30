# Assessment Rubric: Section 1.1 - Absolute Calibration (Photon and Electron Beams)

**Total Points:** 100

**Grading Distribution:**
*   Part 1: Fundamental Concepts (3 MCQ @ 4pts, 2 SA @ 4pts) = 20 points
*   Part 2: Procedures and Corrections (4 SA @ 5pts, 2 Calc @ 8pts) = 36 points
*   Part 3: Dose Calculation Formalism (2 Calc @ 8pts, 2 SA @ 6pts) = 28 points
*   Part 4: Practical Considerations (4 SA @ 4pts) = 16 points

---

## Part 1: Fundamental Concepts and Definitions (20 Points Total)

**1, 3, 4. Multiple Choice Questions (4 points each):**
*   Scoring: 4 points for each correct answer, 0 points for incorrect.
*   Answers:
    1.  c) $N_{D,w}^{Co-60}$, Absorbed Dose to Water in Cobalt-60
    3.  d) Percentage Depth Dose at 10 cm depth excluding electron contamination ($\%dd(10)_x$)
    4.  b) Depth of 50% dose ($R_{50}$)

**2, 5. Short Answers (4 points each):**
*   **General Criteria:**
    *   **4 Points (Excellent):** Accurate, concise, and directly addresses the question.
    *   **3 Points (Good):** Mostly accurate, minor omissions or lack of clarity.
    *   **2 Points (Fair):** Addresses question partially or with some inaccuracies.
    *   **1 Point (Poor):** Largely inaccurate or irrelevant.
    *   **0 Points (Unacceptable):** Missing or irrelevant.
*   **Specific Guidance:**
    *   **Q2 (TG-51 vs TG-21 Advantage):** Mention reduced uncertainty, direct absorbed dose calibration ($N_{D,w}$ vs $N_K/N_X$), simpler formalism for the user (fewer factors).
    *   **Q5 ($k_Q$ Purpose):** Explain it converts the $N_{D,w}^{Co-60}$ factor (obtained in Co-60) to be applicable at the user's specific photon beam quality ($Q$). Accounts for differences in chamber response between Co-60 and the clinical beam.

---

## Part 2: Procedures and Corrections (36 Points Total)

**6, 7, 10, 11. Short Answers (5 points each):**
*   **General Criteria:**
    *   **5 Points (Excellent):** Accurate, complete, clearly explained, uses appropriate terminology.
    *   **4 Points (Good):** Mostly accurate/complete, minor omissions/lack of clarity.
    *   **3 Points (Fair):** Addresses question but significant inaccuracies/omissions/lack of clarity.
    *   **1-2 Points (Poor):** Largely inaccurate/incomplete/irrelevant, but shows some attempt.
    *   **0 Points (Unacceptable):** Inaccurate, irrelevant, or missing.
*   **Specific Guidance:**
    *   **Q6 (Photon Ref Conditions):** Water phantom (≥30cm³), 10x10 cm² field at ref depth, 10 cm depth, 100 cm SSD.
    *   **Q7 (Electron Ref Depth $d_{ref}$):** $d_{ref} = 0.6 \times R_{50} - 0.1$ cm. Determined by measuring $R_{50}$ from a depth dose curve.
    *   **Q10 ($P_{pol}$ Procedure & Importance):** Measure with positive ($M^+$) and negative ($M^-$) polarity. $P_{pol} = (|M^+| + |M^-|) / (2 * |M_{routine}|)$. Importance: Corrects for net charge collection differences due to polarity, ensures accurate reading.
    *   **Q11 ($\%dd(10)_x$ Measurement ≥ 10MV):** Place 1mm lead foil ~50cm from phantom *during PDD scan only*. Why: To remove electron contamination from the beam, allowing accurate determination of the photon component's PDD at 10cm.

**8, 9. Calculation Problems (8 points each):**
*   **General Criteria:**
    *   **8 Points (Excellent):** Correct formula, substitutions, calculation, and answer (with units if applicable).
    *   **6-7 Points (Good):** Minor calculation error or unit issue, correct method.
    *   **3-5 Points (Fair):** Correct formula but significant errors in substitution or calculation.
    *   **1-2 Points (Poor):** Incorrect formula or major conceptual error.
    *   **0 Points (Unacceptable):** No work or irrelevant.
*   **Solutions:**
    *   **Q8 ($P_{TP}$):**
        *   Formula: $P_{TP} = \frac{273.2+T}{273.2+T_{ref}} \times \frac{P_{ref}}{P}$
        *   $P_{TP} = \frac{273.2+21.5}{273.2+22.0} \times \frac{101.33}{102.1}$
        *   $P_{TP} = \frac{294.7}{295.2} \times 0.99246$
        *   $P_{TP} = 0.99831 \times 0.99246 


       $P_{TP} \approx \mathbf{0.9908}$
    *   **Q9 ($P_{ion}$):**
        *   Formula (pulsed): $P_{ion} = \frac{1 - (V_H/V_L)^2}{(M_{raw}^{V_H}/M_{raw}^{V_L}) - (V_H/V_L)^2}$
        *   $V_H/V_L = 2$, $(V_H/V_L)^2 = 4$
        *   $M_{raw}^{V_H}/M_{raw}^{V_L} = 20.500 / 20.350 \approx 1.00737$
        *   $P_{ion} = \frac{1 - 4}{1.00737 - 4} = \frac{-3}{-2.99263} \approx \mathbf{1.0025}$

---

## Part 3: Dose Calculation Formalism (28 Points Total)

**13, 16. Calculation Problems (8 points each):**
*   **General Criteria:** (Same as Part 2 Calculation Problems)
*   **Solutions:**
    *   **Q13 (Photon Dose/MU):**
        *   Formula: $D_w^Q / MU = (M / MU_{delivered}) \times k_Q \times N_{D,w}^{Co-60}$
        *   $D_w^Q / MU = (18.950 \text{ nC} / 100 \text{ MU}) \times 0.988 \times 5.350 \text{ cGy/nC}$
        *   $D_w^Q / MU = 0.18950 \times 0.988 \times 5.350$
        *   $D_w^Q / MU \approx \mathbf{1.001}$ cGy/MU
    *   **Q16 (Electron Dose/MU - Parallel Plate):**
        *   Formula: $D_w^Q / MU = (M / MU_{delivered}) \times P_{gr}^Q \times k\'_{R_{50}} \times k_{ecal} \times N_{D,w}^{Co-60}$
        *   $P_{gr}^Q = 1.0$ for parallel-plate chambers.
        *   $D_w^Q / MU = (6.550 \text{ nC} / 100 \text{ MU}) \times 1.0 \times 1.015 \times 0.905 \times 15.800 \text{ cGy/nC}$
        *   $D_w^Q / MU = 0.06550 \times 1.0 \times 1.015 \times 0.905 \times 15.800$
        *   $D_w^Q / MU \approx \mathbf{0.950}$ cGy/MU

**12, 14, 15. Short Answers (6 points each for Q12, Q14; 4 points for Q15):**
*   **General Criteria:**
    *   **Excellent (6 or 4 pts):** Accurate, complete, clearly explained, uses appropriate terminology.
    *   **Good (4-5 or 3 pts):** Mostly accurate/complete, minor omissions/lack of clarity.
    *   **Fair (2-3 or 2 pts):** Addresses question but significant inaccuracies/omissions/lack of clarity.
    *   **Poor (1 pt):** Largely inaccurate/incomplete/irrelevant, but shows some attempt.
    *   **0 Points:** Inaccurate, irrelevant, or missing.
*   **Specific Guidance:**
    *   **Q12 (Photon Equation):** $D_w^Q = M \times k_Q \times N_{D,w}^{Co-60}$. Ensure M is defined as fully corrected reading.
    *   **Q14 (Electron Equation - Cylindrical):** $D_w^Q = M \times P_{gr}^Q \times k\'_{R_{50}} \times k_{ecal} \times N_{D,w}^{Co-60}$. Ensure M is defined as fully corrected reading.
    *   **Q15 ($P_{gr}^Q$ Purpose):** Corrects for dose gradient across the *finite volume* of a cylindrical chamber in the steep fall-off region of electron beams. Not needed for parallel-plate chambers as their sensitive volume is effectively a plane.

---

## Part 4: Practical Considerations and Guidance (16 Points Total - 4 Points Each)

**General Criteria per Question:** (Same as Part 1 Short Answers)

**Specific Guidance:**

*   **Q17 (TG-374 Leakage Tolerance):** Leakage current should be less than 0.1% of the measurement signal.
*   **Q18 (TG-385 PP Chamber Recommendation):** PP chambers are preferred for electrons (esp. low E) because they minimize perturbation effects (fluence and gradient) near the surface and in steep gradient regions, providing more accurate PDDs and $R_{50}$ values.
*   **Q19 (PP Cross-Calibration):** Place both cylindrical (calibrated) and PP chambers at $d_{ref}$ in a high-energy electron beam (where $P_{gr}^Q \approx 1$ for cylindrical). Determine dose using TG-51 with cylindrical chamber. Use this dose and the PP chamber's corrected reading ($M_{PP}$) to derive an effective calibration factor for the PP chamber in that beam: $N_{D,w}^{PP, Q_{ecal}} = D_w^Q / M_{PP}$. (Alternatively, determine $k_{ecal}$ for the PP chamber).
*   **Q20 (Consistency Checks):** List any two: Daily output checks using simple device (e.g., Daily QA3, MaxSD), monthly output checks with independent calibrated system, comparison with previous calibration data, constancy checks using built-in monitor chamber (if available), checking backup dosimeter.

---

*(Note: This rubric provides a framework. Specific point allocations and criteria can be adjusted based on instructional emphasis.)*
