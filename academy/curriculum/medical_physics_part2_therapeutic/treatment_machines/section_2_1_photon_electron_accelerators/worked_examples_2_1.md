**Worked Example 1: Calculating Number of TVLs for a Primary Barrier**

*   **Problem:** A primary barrier requires a transmission factor (B_pri) of 5.0 x 10^-7 to meet the dose limit P for an uncontrolled area. Using the NCRP 151 methodology, calculate the required number of Tenth-Value Layers (n).

*   **Solution:**
    The number of TVLs (n) is related to the transmission factor (B) by the formula:
    n = -log10(B)

    In this case, B_pri = 5.0 x 10^-7.
    n = -log10(5.0 x 10^-7)
    n = -(log10(5.0) + log10(10^-7))
    n = -(0.699 + (-7))
    n = -(-6.301)
    n = 6.301

*   **Answer:** Approximately 6.3 TVLs are required for the primary barrier.

**Worked Example 2: Calculating Primary Barrier Thickness from TVLs**

*   **Problem:** From Worked Example 1, n = 6.301 TVLs are required. If the shielding material is concrete and the beam energy is 10 MV, determine the required barrier thickness (t). Assume for 10 MV concrete: TVL1 = 0.42 m, TVLe = 0.38 m.

*   **Solution:**
    The thickness (t) is calculated using:
    t = TVL1 + (n - 1) * TVLe

    Here, n = 6.301, TVL1 = 0.42 m, TVLe = 0.38 m.
    t = 0.42 m + (6.301 - 1) * 0.38 m
    t = 0.42 m + (5.301) * 0.38 m
    t = 0.42 m + 2.014 m
    t = 2.434 meters

*   **Answer:** The required concrete thickness for the primary barrier is approximately 2.43 meters.

**Worked Example 3: Daily QA Output Constancy Action Levels (TG-142/TG-198)**

*   **Problem:** A daily QA check for a 6 MV photon beam yields a reading that is +4.2% higher than the baseline value. The tolerance specified in TG-142 is ±3%. According to typical action levels described in TG-198, what steps should be taken?

*   **Solution:**
    1.  **Identify Deviation:** The reading (+4.2%) exceeds the ±3% tolerance.
    2.  **Consult Action Levels (TG-198 Guidance):**
        *   If >±3% but <±5%: Repeat measurement. If still >±3%, notify QMP immediately. Treatment may continue if QMP approves after investigation.
        *   If >±5%: Repeat measurement. If still >±5%, notify QMP immediately. Do not treat.
    3.  **Apply to Scenario:** The deviation (+4.2%) falls into the first category (>±3% but <±5%).
    4.  **Action:**
        *   Repeat the measurement immediately.
        *   If the repeat measurement is within ±3%, document and proceed.
        *   If the repeat measurement is still outside ±3% (e.g., +4.0%), notify the Qualified Medical Physicist (QMP) immediately. The QMP must investigate the cause (e.g., setup error, device issue, actual output change). Treatment should only proceed if the QMP approves after the investigation and deems it safe.

*   **Answer:** Repeat the measurement. If it remains outside the ±3% tolerance, notify the QMP immediately for investigation before proceeding with treatment.

**Worked Example 4: Effective Point of Measurement (EPOM) Shift Correction**

*   **Problem:** A PDD measurement is performed for a 6 MV photon beam using a cylindrical Farmer-type ion chamber with an inner radius of 3.0 mm. The raw measurement data shows the depth of maximum dose (dmax) occurring at 1.7 cm. Calculate the corrected dmax after accounting for the EPOM shift.

*   **Solution:**
    1.  **Determine EPOM Shift:** For photon beams, the upstream shift for a cylindrical chamber is typically given by 0.6 * r, where r is the inner radius of the chamber cavity.
        Shift = 0.6 * 3.0 mm = 1.8 mm = 0.18 cm.
    2.  **Apply Correction:** The effective point of measurement is upstream of the chamber center. Therefore, to get the true depth, we subtract the shift from the measured depth.
        Corrected dmax = Measured dmax - Shift
        Corrected dmax = 1.7 cm - 0.18 cm = 1.52 cm.

*   **Answer:** The corrected depth of maximum dose (dmax) is approximately 1.52 cm.

**Worked Example 5: Gating Duty Cycle Calculation**

*   **Problem:** A respiratory gating system is set up with a window covering 30% of the breathing cycle (e.g., gating during end-exhale). If a treatment plan requires 200 Monitor Units (MU) to be delivered without gating, estimate the total MUs that will need to be delivered *during* the gated treatment to achieve the same effective dose, assuming the dose rate is constant when the beam is on.

*   **Solution:**
    1.  **Identify Duty Cycle:** The duty cycle is the fraction of time the beam is on, which is 30% or 0.30 in this case.
    2.  **Calculate Gating Factor:** The gating factor is the reciprocal of the duty cycle, representing how much longer the treatment will take or how many more MUs need to be delivered *while the beam is on* compared to a non-gated delivery.
        Gating Factor = 1 / Duty Cycle = 1 / 0.30 ≈ 3.33
    3.  **Estimate Total Gated MUs:** Multiply the non-gated MUs by the gating factor.
        Total Gated MUs = Non-gated MUs * Gating Factor
        Total Gated MUs = 200 MU * 3.33 ≈ 667 MU

*   **Answer:** Approximately 667 MUs would need to be delivered during the gated treatment intervals to achieve the equivalent of 200 non-gated MUs. (Note: This assumes ideal gating and constant dose rate. Real-world scenarios might involve slight variations.)
