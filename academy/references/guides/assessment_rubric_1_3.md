# Assessment Rubric: Section 1.3 - Survey Detector Design and Application

**Total Points:** 100 (Example distribution, can be adjusted)

**Grading Distribution:**
*   Part 1: Multiple Choice Questions (5 questions x 4 points each) = 20 points
*   Part 2: Short Answer Questions (5 questions x 8 points each) = 40 points
*   Part 3: Calculation Problems (4 questions x 10 points each) = 40 points

---

## Part 1: Multiple Choice Questions (20 Points Total)

*   **Scoring:** 4 points for each correct answer, 0 points for each incorrect answer.
*   **Answers:** (Refer to `assessment_1_3.md`)
    1.  b) Ionization Region
    2.  c) Ionization chamber survey meter
    3.  d) Dead time losses
    4.  c) Annually and after significant repair
    5.  c) Short-term stability and function

---

## Part 2: Short Answer Questions (40 Points Total - 8 Points Each)

**General Criteria per Question:**
*   **7-8 Points (Excellent):** Answer is accurate, complete, clearly explained, uses appropriate terminology, and demonstrates a strong understanding of the concepts.
*   **5-6 Points (Good):** Answer is mostly accurate and complete, with minor omissions or lack of clarity.
*   **3-4 Points (Fair):** Answer addresses the question but contains significant inaccuracies, omissions, or lacks clarity.
*   **1-2 Points (Poor):** Answer is largely inaccurate, incomplete, or irrelevant, but shows some attempt to address the question.
*   **0 Points (Unacceptable):** Answer is completely inaccurate, irrelevant, or missing.

**Specific Guidance:**

6.  **Sensitivity vs. Accuracy:** Define sensitivity (ability to detect low levels) and accuracy (agreement with true value). Example for sensitivity: Contamination survey (need to detect any presence). Example for accuracy: Dose rate measurement for shielding verification (need reliable value).
7.  **GM Pulse Formation:** Mention initial ionization, gas multiplication (avalanche), spread along the anode wire, and quenching mechanism (gas or electronic).
8.  **Cs-137 Calibration:** Explain its common use (long half-life, convenient gamma energy). Precautions for different energies: Discuss energy dependence, need for correction factors if significant, potential for inaccurate readings (over/under response) if ECF is not applied.
9.  **Operational Checks:** List any three from: Battery check, physical inspection (damage, settings), zero check (if applicable), response to check source (constancy), background check.
10. **Contamination Survey Technique:** Describe slow scan speed (~1-2 inches/sec), close distance (~1 cm), systematic pattern (overlapping passes), and importance of measuring background first.

---

## Part 3: Calculation Problems (40 Points Total - 10 Points Each)

**General Criteria per Question:**
*   **9-10 Points (Excellent):** Correct formula used, correct values substituted, correct calculation performed, correct units stated, answer clearly presented.
*   **7-8 Points (Good):** Minor calculation error or unit error, but correct method and understanding demonstrated.
*   **4-6 Points (Fair):** Correct formula identified but significant calculation errors, incorrect substitutions, or misunderstanding of concepts.
*   **1-3 Points (Poor):** Incorrect formula used or major conceptual errors, but some attempt made.
*   **0 Points (Unacceptable):** No work shown, completely incorrect, or irrelevant.

**Specific Guidance & Answers:**

11. **GM Dead Time Correction:**
    *   Formula: n_true = n_measured / (1 - n_measured * τ)
    *   n_measured = 10000 cpm / 60 s/min = 166.67 cps
    *   τ = 200 µs = 200 x 10⁻⁶ s = 2 x 10⁻⁴ s
    *   n_true = 166.67 / (1 - 166.67 * 2e-4) = 166.67 / (1 - 0.0333) = 166.67 / 0.9667 ≈ 172.4 cps
    *   n_true (cpm) ≈ 172.4 * 60 ≈ **10344 cpm**

12. **Source Check Tolerance:**
    *   Tolerance range: 2.8 mR/hr ± (15% of 2.8 mR/hr)
    *   15% of 2.8 = 0.15 * 2.8 = 0.42 mR/hr
    *   Lower limit = 2.8 - 0.42 = 2.38 mR/hr
    *   Upper limit = 2.8 + 0.42 = 3.22 mR/hr
    *   Measured value = 2.5 mR/hr
    *   Conclusion: **Yes, the meter passes** (2.5 is within [2.38, 3.22]).

13. **Inverse Square Law:**
    *   Formula: I₂ = I₁ * (d₁ / d₂)²
    *   I₁ = 50 mR/hr, d₁ = 1 m, d₂ = 0.5 m
    *   I₂ = 50 * (1 / 0.5)² = 50 * (2)² = 50 * 4 = **200 mR/hr**

14. **Surface Activity Concentration:**
    *   Activity (dpm) = Net Counts (cpm) / Efficiency = 3000 cpm / 0.25 = 12000 dpm
    *   Activity Conc (dpm/cm²) = Activity (dpm) / Area (cm²) = 12000 dpm / 20 cm² = 600 dpm/cm²
    *   Activity Conc (Bq/cm²) = Activity Conc (dpm/cm²) / 60 dpm/Bq = 600 / 60 = **10 Bq/cm²**

---

*(Note: This rubric provides a framework. Specific point allocations and criteria can be adjusted based on instructional emphasis.)*
