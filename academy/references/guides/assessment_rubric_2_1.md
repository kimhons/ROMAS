# Assessment Rubric: Section 2.1 - Photon/Electron Medical Accelerators

**Total Points:** 100 (Example distribution, can be adjusted)

**Grading Distribution:**
*   Part 1: Linac Components and Beam Production (1 MCQ @ 4pts, 4 SA @ 5pts) = 24 points
*   Part 2: Troubleshooting Scenarios (4 SA @ 6pts) = 24 points
*   Part 3: QA and Commissioning (TG reports) (1 MCQ @ 4pts, 4 SA @ 5pts) = 24 points
*   Part 4: Respiratory Motion & Shielding (TG & NCRP) (5 SA @ 4pts) = 20 points
*   Part 5: Calculation Problem (NCRP 151) (1 Calculation @ 8pts) = 8 points

---

## Part 1: Linac Components and Beam Production (24 Points Total)

**1. MCQ (4 points):**
*   Answer: b) Electron Gun
*   Scoring: 4 points for correct, 0 for incorrect.

**2-5. Short Answers (5 points each):**
*   **General Criteria:**
    *   **5 Points (Excellent):** Accurate, complete, clear explanation, uses appropriate terminology.
    *   **4 Points (Good):** Mostly accurate/complete, minor omissions/lack of clarity.
    *   **3 Points (Fair):** Addresses question but significant inaccuracies/omissions/lack of clarity.
    *   **1-2 Points (Poor):** Largely inaccurate/incomplete/irrelevant, but shows some attempt.
    *   **0 Points (Unacceptable):** Inaccurate, irrelevant, or missing.
*   **Specific Guidance:**
    *   **Q2 (Traveling vs. Standing Wave):** Mention power flow (through vs. reflected), efficiency (standing generally higher), length (standing generally shorter), typical use (standing common in modern linacs).
    *   **Q3 (Flattening Filter):** Explain it shapes the forward-peaked beam into a flat profile. Absence (FFF) results in a conical/peaked profile, higher dose rate on central axis.
    *   **Q4 (Scattering Foils):** Explain they spread the narrow pencil electron beam to create a clinically useful field size.
    *   **Q5 (Monitor Chambers):** Describe their role in measuring delivered dose (MUs), terminating beam, and monitoring beam flatness/symmetry.

---

## Part 2: Troubleshooting Scenarios (24 Points Total - 6 Points Each)

**General Criteria per Question:**
*   **6 Points (Excellent):** Identifies multiple plausible causes, outlines logical and relevant troubleshooting steps, demonstrates understanding of system interdependencies.
*   **4-5 Points (Good):** Identifies some key causes and steps, but may miss some or lack detail.
*   **2-3 Points (Fair):** Identifies some relevant points but approach is incomplete or lacks clarity.
*   **1 Point (Poor):** Minimal relevant information.
*   **0 Points (Unacceptable):** Irrelevant or missing.

**Specific Guidance:**

*   **Q6 (VAC 1 Interlock):** Causes: Loss of vacuum in waveguide/gun, faulty vacuum pump (ion pump), leak. Steps: Check pump status/readings, check for obvious damage, notify service (vacuum issues usually require service).
*   **Q7 (MLC Picket Fence Failure):** Causes: Leaf motor issue, position sensor error, control board fault, leaf obstruction/friction. Investigation: Review error logs, run MLC calibration/tests, visual inspection, potentially test individual leaves, notify service.
*   **Q8 (Photon Output Drop, Electrons OK):** Focus: Components unique to photon path after bending magnet - Target integrity/position, flattening filter alignment/damage, photon monitor chamber section. Steps: Check target/filter visually if possible, perform specific photon QA checks (flatness/symmetry, energy), notify service.
*   **Q9 (Dim Lasers):** Causes: Laser aging/failure, dirty optics, power supply issue, misalignment. Steps: Clean external optics, check power supply if accessible, check alignment, replace laser if necessary (often service task).

---

## Part 3: QA and Commissioning (TG Reports) (24 Points Total)

**10. MCQ (4 points):**
*   Answer: c) ±3%
*   Scoring: 4 points for correct, 0 for incorrect.

**11-14. Short Answers (5 points each):**
*   **General Criteria:** (Same as Part 1 Short Answers)
*   **Specific Guidance:**
    *   **Q11 (TG-198 vs TG-142):** TG-198 recommends QMP review daily QA *before the first patient treatment* if performed by non-QMP, stricter than TG-142's minimum weekly review.
    *   **Q12 (TG-106 Detector Orientation):** Scan perpendicular to chamber axis to minimize volume averaging effects across steep dose gradients.
    *   **Q13 (TG-106 EPOM Shift):** More significant for electrons due to steeper gradients. Shift is typically upstream (towards source).
    *   **Q14 (TG-53 Complex Checks):** List any two: Field matching (abutting fields), MLC effects (tongue-and-groove, small fields), heterogeneity corrections (lung, bone), off-axis calculations, non-coplanar beams, IMRT/VMAT plan verification.

---

## Part 4: Respiratory Motion & Shielding (TG & NCRP) (20 Points Total - 4 Points Each)

**General Criteria per Question:**
*   **4 Points (Excellent):** Accurate, concise, and directly addresses the question.
*   **3 Points (Good):** Mostly accurate, minor omissions or lack of clarity.
*   **2 Points (Fair):** Addresses question partially or with some inaccuracies.
*   **1 Point (Poor):** Largely inaccurate or irrelevant.
*   **0 Points (Unacceptable):** Missing or irrelevant.

**Specific Guidance:**

*   **Q15 (TG-76 Motion Management):** List any two: Gating (beam on only during specific phase), Tracking (beam follows tumor), Forced Breath-hold (patient holds breath), Abdominal Compression (reduces motion), ITV (treats envelope of motion).
*   **Q16 (4D CT Purpose):** To capture tumor motion throughout the respiratory cycle, allowing for creation of ITV or phase-specific plans.
*   **Q17 (NCRP 151 Parameters):** W: Weekly dose delivered at isocenter. U: Fraction of workload directed towards barrier. T: Fraction of time area is occupied.
*   **Q18 (Secondary Barrier Sources):** Leakage radiation (through head shielding) and Patient Scatter.
*   **Q19 (Neutron Concern & Shielding):** Produced via photonuclear reactions (>10 MV). Shielding: Hydrogenous materials (e.g., concrete, polyethylene) often combined with high-Z material (e.g., lead) for capture gammas.

---

## Part 5: Calculation Problem (NCRP 151) (8 Points Total)

**20. Calculation (8 points):**
*   **Criteria:**
    *   **8 Points:** Correct formula, substitutions, calculation, and answer.
    *   **6-7 Points:** Minor calculation error or unit issue.
    *   **3-5 Points:** Correct formula but significant errors in substitution or calculation.
    *   **1-2 Points:** Incorrect formula or major conceptual error.
    *   **0 Points:** No work or irrelevant.
*   **Solution:**
    *   Formula for leakage barrier transmission (B_L): B_L = (P * d_sec²) / (0.001 * W * T) (Note: 0.001 represents 0.1% leakage)
    *   P = 0.02 mSv/wk = 0.00002 Sv/wk
    *   d_sec = 5.0 m
    *   W = 600 Gy/wk = 600 Sv/wk (assuming QF=1 for photons)
    *   T = 1/5 = 0.2
    *   B_L = (0.00002 * (5.0)²) / (0.001 * 600 * 0.2)
    *   B_L = (0.00002 * 25) / (0.12)
    *   B_L = 0.0005 / 0.12
    *   B_L ≈ **0.00417** or **4.17 x 10⁻³**

---

*(Note: This rubric provides a framework. Specific point allocations and criteria can be adjusted based on instructional emphasis.)*
