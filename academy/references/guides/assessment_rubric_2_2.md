# Assessment Rubric: Section 2.2 - Proton Accelerators and Beam Characteristics

**Total Points:** 100 (Example distribution, can be adjusted)

**Grading Distribution:**
*   Part 1: Multiple Choice Questions (10 questions x 3 points each) = 30 points
*   Part 2: Short Answer Questions (8 questions x 5 points each) = 40 points
*   Part 3: Scenario-Based Question (1 question x 30 points) = 30 points

---

## Part 1: Multiple Choice Questions (30 Points Total)

*   **Scoring:** 3 points for each correct answer, 0 points for each incorrect answer.
*   **Answers:** (Refer to the answer key associated with `assessment_2_2.md` - Note: An answer key needs to be formally created if not already implicitly present in the assessment file itself. Assuming standard answers based on content.)
    1.  b) Cyclotron (Typically continuous beam, though energy variation needs degraders)
    2.  c) The amplitude of the accelerating RF voltage
    3.  c) Synchrotron
    4.  c) Bragg Peak
    5.  a) Initial energy
    6.  c) Deliver a uniform dose across the target volume depth
    7.  c) 1.1
    8.  c) HU depends on factors differently than proton stopping power does.
    9.  b) Beam range and output constancy
    10. b) Directly measuring proton stopping power within the patient

---

## Part 2: Short Answer Questions (40 Points Total - 5 Points Each)

**General Criteria per Question:**
*   **5 Points (Excellent):** Answer is accurate, complete, clearly explained, and demonstrates a strong understanding of the concepts.
*   **4 Points (Good):** Answer is mostly accurate and complete, with minor omissions or lack of clarity.
*   **3 Points (Fair):** Answer addresses the question but contains significant inaccuracies, omissions, or lacks clarity.
*   **1-2 Points (Poor):** Answer is largely inaccurate, incomplete, or irrelevant, but shows some attempt to address the question.
*   **0 Points (Unacceptable):** Answer is completely inaccurate, irrelevant, or missing.

**Specific Guidance:**

1.  **Cyclotron vs. Synchrotron Acceleration:** Look for mention of constant magnetic field/varying radius (cyclotron) vs. varying magnetic field/fixed radius (synchrotron), and corresponding RF frequency differences (constant vs. varying).
2.  **Range Uncertainty:** Explanation should include the source (primarily CT HU-to-SPR conversion), the consequence (need for margins), and the impact (potential underdose of target or overdose of OARs).
3.  **Beam Transport System:** Mention guiding/focusing the beam from accelerator to treatment room using magnets (dipoles, quadrupoles) in a vacuum line.
4.  **Stoichiometric Calibration:** Describe scanning phantom with known tissue inserts, relating HU to calculated SPR based on elemental composition. Advantage: More accurate than single curve, especially across different tissue types.
5.  **TPS Commissioning (TG-185):** List any three relevant items from: Beam data acquisition (PBP, spot profiles, range), beam modeling (matching calculations to measurements), model verification (independent checks), MU verification, CT calibration (HU-SPR curve).
6.  **Lateral Beam Spreading:** Identify Multiple Coulomb Scattering (MCS) as the primary cause.
7.  **WEPL:** Define as the path length in water that would cause the same energy loss as the actual path through the patient. Relevance: Directly measured in PR, used for range verification or pCT reconstruction.
8.  **Beam Time Structure:** Explain impact on scanning (spot delivery timing, interplay with motion), detector saturation (esp. for pulsed beams), and overall treatment time (duty cycle).

---

## Part 3: Scenario-Based Question (30 Points Total)

**Scenario:** Annual QA range measurement for 180 MeV beam is 2 mm shorter than baseline. Tolerance is ±1.5 mm.

**a) Does measurement pass tolerance? (5 points)**
*   **5 Points:** Correctly states 

No, the measurement does not pass tolerance. The difference (-2 mm) exceeds the allowed tolerance (±1.5 mm).
*   **0-4 Points:** Incorrect conclusion or calculation.

**b) Potential causes for discrepancy? (10 points)**
*   **8-10 Points:** Lists multiple plausible and relevant causes (e.g., actual decrease in beam energy from accelerator/source, drift in beam transport magnets, issue with energy selection system/degrader, change in beam path medium before phantom, incorrect measurement setup/alignment, detector malfunction/calibration drift).
*   **4-7 Points:** Lists some relevant causes, but may miss key possibilities or include less likely ones.
*   **1-3 Points:** Lists only one relevant cause or mostly irrelevant causes.
*   **0 Points:** No relevant causes listed.

**c) Steps physicist should take? (15 points)**
*   **12-15 Points:** Outlines a comprehensive and logical sequence of actions: 
    1.  Confirm the measurement setup and repeat the measurement.
    2.  If discrepancy persists, immediately restrict clinical use of the affected beam energy.
    3.  Investigate potential causes (review machine logs, check related QA parameters like output/symmetry, inspect beamline components if possible).
    4.  Notify the radiation oncology team and the service engineer.
    5.  Work with service/perform adjustments as needed (e.g., beam tuning, energy calibration).
    6.  Thoroughly re-verify beam range (and potentially other related parameters like output) after correction.
    7.  Document all findings, actions, and final verification before releasing the beam for clinical use.
*   **7-11 Points:** Outlines most key steps but may miss some or present them in a less logical order.
*   **3-6 Points:** Outlines some appropriate steps but misses critical actions like restricting beam use or final verification.
*   **1-2 Points:** Suggests minimal or inappropriate actions.
*   **0 Points:** No relevant actions listed.

---

*(Note: This rubric provides a framework. Specific point allocations and criteria can be adjusted based on instructional emphasis.)*
