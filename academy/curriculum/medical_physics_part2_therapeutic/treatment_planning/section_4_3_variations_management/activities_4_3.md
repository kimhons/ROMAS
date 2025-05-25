# Section 4.3: Management of Inter- and Intra-fraction Variations - Activities

## Activity 1: 4DCT Analysis and ITV Creation

**Objective:** To understand the process of analyzing 4DCT data to quantify respiratory motion and create an Internal Target Volume (ITV).

**Scenario:** You are provided with a 4DCT dataset (10 phases) for a patient with a lung tumor.

**Tasks:**
1.  **Load & Review:** Load the 10 phases of the 4DCT scan into your treatment planning system (TPS).
2.  **Contour GTV:** Contour the Gross Tumor Volume (GTV) on a reference phase (e.g., the 50% exhale phase).
3.  **Propagate/Adjust Contours:** Propagate the GTV contour to all other phases of the 4DCT. Carefully review and adjust the contours on each phase to accurately represent the tumor volume throughout the respiratory cycle.
4.  **Quantify Motion:** Using the contoured GTVs across all phases, determine the maximum displacement of the tumor centroid or extent in the superior-inferior (SI), anterior-posterior (AP), and left-right (LR) directions.
5.  **Create ITV:** Generate an ITV that encompasses all the GTV contours from the 10 phases. Most TPS have tools to automatically create a composite volume from contours across multiple image sets.
6.  **Measure Volumes:** Record the volume of the GTV on the reference phase and the volume of the resulting ITV.
7.  **Discussion:** Discuss the implications of the motion amplitude and the ITV volume on potential treatment planning strategies (e.g., ITV-based PTV vs. gating/tracking). What are the potential drawbacks of a large ITV?

## Activity 2: IGRT Image Registration Comparison

**Objective:** To practice and compare different image registration methods for patient setup verification.

**Scenario:** You are provided with a planning CT scan and a pre-treatment kV CBCT scan for a prostate cancer patient with implanted fiducial markers.

**Tasks:**
1.  **Load Images:** Load the planning CT and the CBCT into your TPS or IGRT review software.
2.  **Bony Anatomy Registration:** Perform an automatic image registration based on bony anatomy (e.g., pelvic bones). Record the translational (X, Y, Z) and rotational (Pitch, Roll, Yaw) shifts suggested by the system.
3.  **Fiducial Marker Registration:** Perform an automatic image registration based on matching the implanted gold fiducial markers visible on both the planning CT (or DRRs) and the CBCT. Record the translational and rotational shifts suggested.
4.  **Soft Tissue Registration (Optional/Visual):** If possible, attempt a registration based on aligning the prostate soft tissue contours (or visually assess the alignment of the prostate after bony and fiducial matches). Note any discrepancies.
5.  **Compare Shifts:** Compare the shifts obtained from bony registration versus fiducial registration. Are they identical? If not, why might they differ?
6.  **Decision:** Which registration result would you clinically prioritize for correcting the patient's setup for prostate IMRT? Justify your answer, considering the target and nearby OARs.
7.  **Discussion:** Discuss the pros and cons of bony vs. fiducial vs. soft-tissue registration for prostate IGRT based on TG-132 recommendations.

## Activity 3: Evaluating the Need for Adaptive Replanning

**Objective:** To simulate the process of evaluating anatomical changes during treatment and deciding whether adaptive replanning is necessary.

**Scenario:** A head and neck cancer patient is undergoing IMRT. You have the initial planning CT and a CBCT acquired at week 4 of treatment. Significant weight loss has occurred.

**Tasks:**
1.  **Load & Register:** Load the planning CT and the week 4 CBCT into the TPS. Register the CBCT to the planning CT, likely using bony anatomy.
2.  **Review Anatomy:** Carefully compare the anatomy on the CBCT to the planning CT. Pay attention to:
    *   External contour changes.
    *   Target volume (GTV/CTV) size and position.
    *   Position and shape of OARs (e.g., parotid glands, spinal cord).
3.  **Dose Deformation/Recalculation (Conceptual or Actual):**
    *   *Conceptual:* Based on the observed anatomical changes, predict how the delivered dose distribution might differ from the planned distribution. Will the target still be adequately covered? Are OARs receiving significantly higher doses?
    *   *Actual (if TPS allows):* If your TPS has tools for dose deformation or recalculation on the daily image, attempt to estimate the dose delivered based on the week 4 CBCT anatomy. Compare this estimated dose to the planned dose (e.g., using DVHs for target and OARs).
4.  **Decision:** Based on your evaluation, would you recommend adaptive replanning for this patient? Justify your decision based on the potential dosimetric impact of the observed changes.
5.  **Discussion:** What factors influence the decision to replan (e.g., magnitude of change, location of change relative to target/OARs, remaining fractions, clinical goals)? Discuss the logistical steps involved in offline adaptive replanning.

