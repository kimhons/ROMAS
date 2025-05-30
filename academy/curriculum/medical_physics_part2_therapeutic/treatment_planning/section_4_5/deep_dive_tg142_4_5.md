# Section 4.5: Deep Dive into AAPM TG-142 - Linac QA on Steroids (Especially for SRS/SBRT)

*(Note: This deep dive focuses on the aspects of AAPM Task Group 142 most relevant to SRS/SBRT, building upon TG-40 and using expanded bullet points with practical insights.)*

## 1. Why TG-142? The Evolution Beyond TG-40

*   **TG-40 Limitations:** Published in 1994, TG-40 provided foundational linac QA guidance but didn't cover newer technologies or techniques.
    *   Missing: MLCs, asymmetric jaws, dynamic/virtual wedges, EPIDs, CBCT, IGRT, respiratory gating.
    *   Didn't differentiate QA needs based on treatment complexity (e.g., conventional vs. IMRT vs. SRS/SBRT).
*   **TG-142 Purpose:**
    *   Update TG-40 recommendations.
    *   Add QA procedures for the newer technologies.
    *   Provide specific recommendations and *tighter tolerances* for machines used for advanced techniques like IMRT and especially SRS/SBRT.
    *   Introduce QA for integrated imaging systems (kV, MV, CBCT).
    *   **Street Wisdom:** TG-142 acknowledges that if you're doing high-precision stuff like SRS/SBRT, your machine QA needs to be more rigorous than for basic treatments. You can't just use the old TG-40 checklist anymore.

## 2. Key Philosophy: Tailoring QA to Clinical Use

*   **Tiered Tolerances:** TG-142 introduces different tolerance levels based on the machine's clinical use:
    *   **Non-IMRT:** Basic 3D conformal treatments.
    *   **IMRT:** Intensity-modulated treatments (step-and-shoot, sliding window, VMAT).
    *   **SRS/SBRT:** Stereotactic treatments requiring the highest precision.
*   **Rationale:** Higher precision treatments demand tighter control over machine parameters.
    *   Small geometric errors (isocenter, MLC position, jaw position) have a much larger dosimetric impact in SRS/SBRT due to steep dose gradients and small target volumes.
    *   **Street Wisdom:** If your linac is only used for simple palliative cases, maybe the standard tolerances are okay. But if you're blasting tiny targets near critical structures with SRS/SBRT, that same machine needs much stricter checks.

## 3. Mechanical QA: Isocenter, Isocenter, Isocenter!

*   **Isocenter Accuracy:** The heart of stereotactic precision. TG-142 emphasizes rigorous checks.
    *   **Definition:** The point in space where the axes of rotation for the gantry, collimator, and couch intersect.
    *   **Tests (Annual):**
        *   **Gantry Rotation Isocenter:** Check stability of the radiation isocenter as the gantry rotates. Tolerance: ≤ 1 mm diameter sphere (SRS/SBRT) vs. ≤ 2 mm (Non-IMRT).
        *   **Collimator Rotation Isocenter:** Check stability as collimator rotates. Tolerance: ≤ 1 mm diameter (SRS/SBRT) vs. ≤ 2 mm (Non-IMRT).
        *   **Couch Rotation Isocenter:** Check stability as couch rotates. Tolerance: ≤ 1 mm diameter (SRS/SBRT) vs. ≤ 2 mm (Non-IMRT).
        *   **Coincidence of Radiation and Mechanical Isocenter:** Ensure the radiation beam axis aligns with the defined mechanical isocenter. Tolerance: ≤ 1 mm (SRS/SBRT) vs. ≤ 2 mm (Non-IMRT).
    *   **Street Wisdom:** For SRS/SBRT, everything has to point to the same tiny spot, no matter how you rotate the gantry, collimator, or couch. The 1 mm tolerance is tight and requires careful measurement techniques (e.g., "star shot" analysis, specialized phantoms).
*   **Other Key Mechanical Checks (with SRS/SBRT Tolerances):**
    *   **Laser Localization (Daily):** ≤ 1 mm (vs. 2 mm Non-IMRT). Critical for initial patient setup.
    *   **Distance Indicator (ODI) (Daily):** ≤ 2 mm (same as Non-IMRT, but consistency is key).
    *   **Collimator Size Indicator (Daily):** ≤ 1 mm per jaw (vs. 2 mm Non-IMRT). Important for accurate field definition.
    *   **Light/Radiation Field Coincidence (Monthly):** ≤ 1 mm or 1% per side (vs. 2 mm or 1% Non-IMRT). Ensures light field used for setup matches the treatment beam.
    *   **Gantry/Collimator Angle Indicators (Monthly):** ≤ 1.0° (digital readouts).
    *   **Jaw Position Indicators (Monthly):** ≤ 1 mm per jaw (symmetric & asymmetric) (vs. 2 mm Non-IMRT).
    *   **Cross-hair Centering (Walkout) (Monthly):** ≤ 1 mm radius from center (vs. 2 mm Non-IMRT). Ensures cross-hairs accurately indicate beam center across gantry/collimator rotation.
    *   **Treatment Couch Position Indicators (Monthly):** ≤ 1 mm / 0.5° (vs. 2 mm / 1° Non-IMRT). Crucial for accurate patient positioning and corrections based on IGRT.
    *   **Street Wisdom:** Notice the pattern: tolerances for SRS/SBRT are often half of what's acceptable for conventional RT. Millimeters matter!

## 4. Dosimetry QA: Consistency is King

*   **Output Constancy (Photons):**
    *   **Daily:** 3% (same across all tiers, mainly a safety/consistency check).
    *   **Monthly:** 2% (same across all tiers, but *how* you measure for SRS/SBRT might differ - need consistency in small field setup if applicable).
    *   **Annual:** 1% (absolute calibration traceable to standards).
    *   **SRS/SBRT Specific:** Check output constancy at the high dose rates often used for stereotactic treatments.
*   **Beam Profile Constancy (Monthly/Annual):** Ensures the beam shape (flatness, symmetry) hasn't changed.
    *   **Monthly:** 1% (vs. 2% Non-IMRT) for flatness/symmetry checks using simplified methods (e.g., scanning ion chamber array, EPID).
    *   **Annual:** Full water tank scans. Flatness ±1%, Symmetry ±1% (vs. ±3% / ±2% in TG-40 era). Tighter symmetry is important for dose calculation accuracy.
*   **Energy Constancy (Monthly/Annual):** Ensures beam penetration hasn't changed.
    *   Checked via PDD or TMR measurements. Tolerance: 1% variation in PDD/TMR value at a specific depth.
*   **Small Field Dosimetry Considerations:** While TG-142 doesn't detail *how* to do small field output factors (that's more TRS-483/TG-155), it implies that the QA program must ensure the constancy of whatever small fields are used clinically.
*   **Street Wisdom:** Daily output checks are basic safety. Monthly/Annual checks ensure the beam characteristics haven't drifted, which is critical because those baseline values are baked into the TPS. For SRS/SBRT, even small drifts in profile or energy can impact the dose distribution significantly.

## 5. Multileaf Collimator (MLC) QA: Shaping the Beam Precisely

*   **Critical for SRS/SBRT:** MLCs define the sharp field edges and complex shapes needed.
*   **Key Tests (Specific MLC Table V in TG-142):**
    *   **Leaf Position Accuracy (Monthly/Annual):** How accurately each leaf goes to its programmed position.
        *   Tolerance (IMRT/SRS): ≤ 1 mm (average error across leaves), ≤ 2 mm (max error for single leaf). Checked using film, EPID, or specialized phantoms.
    *   **Leaf Speed (Annual):** Important for dynamic IMRT/VMAT. Check against manufacturer specs.
    *   **Transmission (Annual):** Dose passing through the leaves and between leaves (interleaf leakage). Characterized at commissioning, checked for constancy.
    *   **Calibration/Synchronization (Monthly/Annual):** Ensure MLC positions correspond correctly to the TPS and linac control system.
    *   **Picket Fence Test (Weekly/Monthly for IMRT/SRS):** Qualitative or quantitative test using EPID or film to check leaf alignment and calibration consistency across abutting fields.
*   **Street Wisdom:** MLCs are complex mechanical devices. Leaves can get stuck, calibration can drift. For the tiny fields and sharp gradients in SRS/SBRT, even a 1 mm leaf position error can be significant. Regular, careful MLC QA is non-negotiable.

## 6. Imaging QA: Seeing is Believing (and Treating)

*   **New in TG-142:** Explicit QA for onboard imaging systems (EPID, kV OBI, CBCT).
*   **Goal:** Ensure geometric accuracy (imaging system aligned with treatment isocenter) and acceptable image quality.
*   **Key Tests (Specific Imaging Table VI in TG-142):**
    *   **Geometric Accuracy / Isocenter Coincidence (Monthly/Annual):** Verify that the center of the imaging volume (kV, MV, CBCT) coincides with the treatment radiation isocenter.
        *   Tolerance (SRS/SBRT): ≤ 1 mm (vs. ≤ 2 mm Non-IMRT).
        *   Checked using specialized phantoms with markers visible in both imaging and radiation fields (e.g., Winston-Lutz test variations, cube phantoms).
    *   **Image Quality (Monthly):** Assess spatial resolution, contrast, uniformity, and noise using appropriate phantoms (e.g., CatPhan for CBCT, Leeds phantom for planar kV/MV).
    *   **Scaling/Distortion (Annual):** Verify geometric accuracy across the image field.
    *   **Registration/Correction Accuracy (Monthly/Annual):** Test the software's ability to accurately register images and apply calculated shifts to the couch.
*   **Street Wisdom:** Your IGRT system is what allows you to set up the patient accurately. If the imaging isocenter doesn't match the treatment isocenter, you'll be systematically missing the target, even if the images look good. The 1 mm tolerance for SRS/SBRT is critical here.

## 7. Action Levels: What to Do When Things Go Wrong

*   **TG-142 Suggests Action Levels:**
    *   **Inspection:** Parameter is outside tolerance but doesn't pose immediate risk. Monitor more frequently, investigate cause.
    *   **Scheduled Action:** Parameter significantly outside tolerance. Schedule service/correction soon, consider clinical impact.
    *   **Immediate Action / Stop Treatment:** Parameter grossly outside tolerance, potential safety risk. Stop treatments, correct immediately.
*   **Physicist Judgment:** The QMP needs to interpret results in the context of clinical use and potential impact.
*   **Street Wisdom:** The tolerances aren't just numbers; they trigger actions. Knowing when to just watch something versus when to stop treating requires experience and good judgment.

## 8. Setting Up the Program

*   **Team Approach:** Involves physicists, therapists, engineers.
*   **Clear Procedures:** Document *how* each test is performed.
*   **Training:** Ensure staff are properly trained.
*   **Documentation:** Keep meticulous records of all QA results.
*   **Review:** Physicist reviews results regularly (daily, monthly, annual summaries).

**In summary, TG-142 provides the essential framework for modern linac QA, recognizing that advanced techniques like SRS/SBRT demand higher levels of mechanical, dosimetric, and imaging accuracy, requiring more frequent checks and significantly tighter tolerances than conventional radiotherapy.**
