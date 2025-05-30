# Section 4.5: Assessment - SRS/SBRT

*(Instructions: Answer the following questions to the best of your ability, drawing upon the knowledge gained in Section 4.5.)*

## Part 1: Multiple Choice (Select the single best answer)

1.  The primary goal of the Winston-Lutz test in SRS/SBRT QA is to verify:
    a) The accuracy of the treatment planning system algorithm.
    b) The coincidence of the radiation, mechanical, and imaging isocenters.
    c) The output constancy of the linear accelerator for small fields.
    d) The effectiveness of the patient immobilization device.

2.  Loss of Lateral Electronic Equilibrium (LED) is a major concern in small field dosimetry primarily because it:
    a) Increases the linac output significantly.
    b) Makes detector readings highly dependent on factors other than local dose (e.g., scatter, detector perturbations).
    c) Causes blurring in portal images.
    d) Is only relevant for Flattening Filter Free (FFF) beams.

3.  For SBRT treatment of a liver metastasis using an ITV approach, the ITV is designed to account for:
    a) Microscopic tumor extension.
    b) Daily patient setup variations.
    c) The full range of tumor motion, typically due to respiration.
    d) Uncertainties in image registration.

4.  Which of the following represents the MOST critical dose-limiting structure when planning Spine SBRT?
    a) Esophagus
    b) Kidney
    c) Spinal Cord
    d) Skin

5.  Compared to conventional radiotherapy, SRS/SBRT typically involves:
    a) Larger treatment fields and shallower dose gradients.
    b) More fractions delivered over a longer period.
    c) Lower total biologically effective dose (BED).
    d) Higher dose per fraction and steeper dose gradients.

## Part 2: Short Answer Questions

6.  Briefly explain why multi-modal image fusion (e.g., CT and MRI) is often considered essential for accurate target delineation in SRS/SBRT planning for sites like the brain or spine.

7.  Describe two different motion management strategies used in SBRT for lung tumors and state one potential advantage and disadvantage of each.

8.  What is meant by "End-to-End Testing" in the context of SRS/SBRT QA, and why is it important?

9.  List three different types of detectors that can be suitable for relative dosimetry (e.g., measuring profiles or output factors) in small fields used for SRS/SBRT, and mention one key characteristic or challenge associated with each.

10. Explain the clinical rationale for using SBRT to treat oligometastatic disease.

## Part 3: Problem Solving / Scenario Analysis

11. **Scenario:** A patient is planned for prostate SBRT (36.25 Gy in 5 fractions). Gold fiducial markers were implanted. Daily IGRT involves CBCT alignment to bony anatomy initially, followed by kV orthogonal imaging alignment to the fiducial markers.
    *   **(a)** Why is alignment to fiducial markers preferred over bony anatomy for final positioning in prostate SBRT?
    *   **(b)** If the kV imaging shows the fiducials have shifted 4 mm anteriorly and 2 mm superiorly relative to the planned position after the initial CBCT bony alignment, what action should the radiation therapists take?

12. **Scenario:** During patient-specific QA for a single-fraction SRS plan using high-resolution film dosimetry, the gamma analysis using 2%/1mm criteria yields a passing rate of 88%. The institutional tolerance is >90% passing.
    *   **(a)** Is this result acceptable for proceeding with treatment? Why or why not?
    *   **(b)** What potential issues in the planning or delivery process could lead to such a QA result?

