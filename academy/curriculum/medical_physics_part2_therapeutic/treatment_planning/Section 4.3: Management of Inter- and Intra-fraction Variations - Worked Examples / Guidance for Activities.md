# Section 4.3: Management of Inter- and Intra-fraction Variations - Worked Examples / Guidance for Activities

## Guidance for Activity 1: 4DCT Analysis and ITV Creation

**Objective:** Understand 4DCT analysis for respiratory motion and ITV generation.

**Expected Outcomes & Guidance:**

1.  **Loading & Review:** Successfully load all 10 phases into the TPS. Familiarize yourself with navigating between phases.
2.  **Contouring GTV:** Accurately contour the GTV on the reference phase (e.g., 50% exhale). Pay attention to window/level settings for optimal tumor visualization.
3.  **Propagate/Adjust:** Use TPS tools (e.g., contour propagation, deformation) to transfer the contour to other phases. **Crucially, manually review and adjust the contour on *each* phase.** Respiratory motion often involves deformation, not just rigid shifts, so simple propagation may be inaccurate. Ensure the contour accurately reflects the GTV boundary in each phase's anatomy.
4.  **Quantify Motion:** Most TPS have analysis tools to track contour centroids or extents across phases. Record the maximum range of motion (max position - min position) in SI, AP, and LR directions. *Example Result:* SI = 1.5 cm, AP = 0.4 cm, LR = 0.2 cm.
5.  **Create ITV:** Use the TPS function to generate a composite volume enclosing all 10 GTV contours. Visually inspect the ITV to ensure it fully encompasses the tumor extent across all phases.
6.  **Measure Volumes:** Record the GTV volume (e.g., 8.5 cc) and the ITV volume (e.g., 15.0 cc). The ITV volume will always be larger than any single-phase GTV volume.
7.  **Discussion Points:**
    *   **Implications:** A large motion amplitude (like 1.5 cm SI) leads to a significantly larger ITV compared to the GTV. Planning based on this ITV (ITV + Setup Margin = PTV) means irradiating a larger volume of normal lung tissue.
    *   **Alternatives:** For large motion, techniques like gating (treating only during phases with minimal motion), breath-hold (immobilizing the tumor), or tracking might be considered to reduce the treated volume and spare normal tissue, especially for SBRT where high doses are used.
    *   **Drawbacks of Large ITV:** Increased dose to surrounding normal tissues (lung, chest wall, etc.), potentially increasing toxicity risk (e.g., pneumonitis). May limit the achievable dose conformality.

## Guidance for Activity 2: IGRT Image Registration Comparison

**Objective:** Compare bony vs. fiducial registration for prostate IGRT.

**Expected Outcomes & Guidance:**

1.  **Loading:** Successfully load planning CT and CBCT.
2.  **Bony Registration:** Execute automatic registration based on pelvic bones (e.g., femurs, pelvic brim, sacrum). Record the shifts (e.g., X=0.2cm, Y=-0.3cm, Z=0.1cm, Pitch=0.5°, Roll=0.1°, Yaw=-0.2°).
3.  **Fiducial Registration:** Execute automatic registration based on the implanted markers. Ensure the TPS correctly identifies the markers on both datasets. Record the shifts (e.g., X=0.4cm, Y=-0.8cm, Z=0.3cm, Pitch=0.7°, Roll=0.2°, Yaw=-0.1°).
4.  **Soft Tissue:** Visually compare the prostate contour alignment after applying each set of shifts. Note if one registration method appears to align the target better.
5.  **Compare Shifts:** The shifts will likely **differ**. Bony registration aligns the pelvic skeleton, while fiducial registration aligns the markers *within* the prostate. Since the prostate can move relative to the pelvic bones (due to bladder/rectal filling), the shifts required to align the target (fiducials) may differ from those needed to align the bones.
6.  **Decision:** **Prioritize fiducial registration.** For prostate IMRT, the goal is to accurately target the prostate itself. Fiducial markers implanted within the prostate provide the most direct and reliable surrogate for the target's position, accounting for its movement relative to the bones. Bony registration primarily corrects overall patient setup but not internal organ motion.
7.  **Discussion Points (TG-132):**
    *   **Pros/Cons:**
        *   *Bony:* Easy to automate, good for initial setup, less invasive. However, does not account for internal organ motion relative to bone.
        *   *Fiducial:* Directly tracks target position (or a close surrogate), accounts for organ motion relative to bone, generally considered more accurate for targets like the prostate. Requires invasive marker implantation, markers can migrate, registration can fail if markers are obscured or misidentified.
        *   *Soft Tissue:* Directly aligns the target organ contour. Can be challenging due to lower contrast on CBCT, requires accurate initial contours, susceptible to contouring variations and DIR algorithm inaccuracies.
    *   **TG-132:** Emphasizes understanding the limitations of each method, the importance of QA for registration algorithms, and choosing the registration strategy most appropriate for the clinical target and goals.

## Guidance for Activity 3: Evaluating the Need for Adaptive Replanning

**Objective:** Assess anatomical changes and decide on adaptive replanning.

**Expected Outcomes & Guidance:**

1.  **Loading & Registration:** Load images and perform registration (likely bony anatomy for H&N).
2.  **Review Anatomy:** Systematically compare the CBCT to the planning CT.
    *   *Example Observations:* External contour smaller due to weight loss, GTV appears smaller, parotid glands have shifted medially and superiorly, air gaps visible between mask and skin.
3.  **Dose Evaluation:**
    *   *Conceptual Prediction:* Weight loss/shrinkage might pull OARs (parotids) into higher dose regions. Tumor shrinkage might lead to parts of the original PTV receiving high dose unnecessarily, or potentially parts of the shrunken GTV being underdosed if it moved significantly.
    *   *Actual Dose Estimation:* If performed, the recalculated DVH might show: decreased GTV coverage (e.g., V95% < 95%), increased parotid mean dose (e.g., > 26 Gy), increased maximum dose to spinal cord or brainstem if significant shifts occurred.
4.  **Decision:** **Likely recommend adaptive replanning.** Significant weight loss, tumor shrinkage, and OAR shifts (especially parotids moving into high dose) strongly suggest the original plan is no longer optimal or safe. The potential for increased OAR toxicity and/or compromised target coverage justifies the effort of replanning.
5.  **Discussion Points:**
    *   **Influencing Factors:** Magnitude of weight loss, degree of tumor shrinkage, extent of OAR displacement relative to dose gradients, remaining number of fractions (more fractions remaining = greater benefit from adaptation), patient's clinical status, institutional resources/workflow for ART.
    *   **Logistics (Offline ART):** Scheduling new CT sim, physician re-contouring time, physics re-planning and QA time, ensuring smooth transition between plans. Requires efficient communication and workflow.

