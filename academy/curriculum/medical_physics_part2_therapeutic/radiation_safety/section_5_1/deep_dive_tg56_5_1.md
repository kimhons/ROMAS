# Deep Dive: AAPM Task Group 56 (TG-56) - Code of Practice for Brachytherapy Physics

This document provides a detailed deep dive into the recommendations of the AAPM Radiation Therapy Committee Task Group No. 56, focusing on the code of practice for brachytherapy physics. It emphasizes practical implementation, quality assurance (QA), and clinical relevance.

## Part 1: Information for Radiation Oncology Administration

*   **Context and Importance:**
    *   Brachytherapy offers superior dose localization compared to external beam therapy but involves steep dose gradients and heterogeneity.
    *   Technological advancements (imaging, planning systems, remote afterloaders) increase complexity and require robust physics support.
    *   Safe and effective brachytherapy requires a qualified medical physicist for facility design, procedure development, and treatment verification.
*   **Team Effort:**
    *   Emphasizes collaboration between administrators, radiation oncologists, medical physicists, dosimetrists, therapists, health physicists, and engineers.
    *   The physicist often leads the technical team, determining task delegation and review requirements.
*   **Facility Design and Licensing:**
    *   Physicist involvement is crucial for specifying equipment, designing shielded spaces, and ensuring regulatory compliance (NRC/Agreement State).
    *   The license is a contract with the hospital; the physicist helps draft applications to avoid overly restrictive terms.
    *   Compliance is critical; misadministrations must be reported and can lead to significant consequences.
*   **Acceptance Testing and Commissioning:**
    *   Physicist performs exhaustive testing of new equipment (sources, applicators, afterloaders, planning systems) to verify specifications and collect necessary clinical data.
    *   Includes verifying source calibration, dimensions, and positional/temporal accuracy of afterloaders.
*   **Procedure Development:**
    *   Physicist designs detailed clinical workflows, identifying critical points for QA checks to prevent errors (source positioning, treatment duration, dose delivery).
    *   Procedures must ensure patient/staff safety and institutional compliance.
*   **Resource Allocation:**
    *   Administrators must allocate sufficient physicist time and resources for QA, procedure development, and ongoing support, proportional to the complexity of the brachytherapy program.

## Part 2: A Code of Practice for Brachytherapy Physics

### I. Overview

*   Provides guidelines for the practice of brachytherapy physics, complementing previous reports like TG-40.

### II. Quality Assurance Program Goals

*   **A. QA Program Endpoints:**
    *   **Safety:** Protect patient, public, and staff from radiation hazards and treatment errors.
        *   *Clinical Relevance:* Preventing source misplacement, incorrect dose delivery, or unintended exposure.
    *   **Positional Accuracy:** Ensure sources and applicators are placed correctly relative to the target volume and critical structures.
        *   *Practical Guidance:* Requires robust imaging, localization techniques, and verification methods (e.g., post-implant imaging, stereotactic verification).
    *   **Temporal Accuracy:** Ensure treatment duration (LDR) or dwell times (HDR/PDR) are accurate.
        *   *Practical Guidance:* Requires accurate timers, afterloader controls, and verification procedures.
    *   **Dose Delivery Accuracy:** Ensure the delivered dose distribution matches the planned distribution within acceptable tolerances.
        *   *Practical Guidance:* Relies on accurate source calibration, dosimetry data, planning system calculations, and verification of all steps.
*   **B. Developing a QA Program:**
    *   **QA of Treatment Delivery Devices:** Regular testing of sources, applicators, afterloaders, and planning systems (details in Section VI).
    *   **Procedure-Specific QA:** Tailored checks for each type of brachytherapy procedure (e.g., GYN intracavitary, prostate seed implant, HDR interstitial) integrated into the clinical workflow.

### III. Physical Quantities in Brachytherapy

*   **A. Brachytherapy Source Strength:**
    *   **Recommendation:** Use **Air Kerma Strength (S_K)** universally.
        *   Units: $U = \mu Gy \cdot m^2 \cdot h^{-1} = cGy \cdot cm^2 \cdot h^{-1}$.
        *   Replaces older quantities like activity (mCi) or equivalent mass of radium (mgRaEq).
    *   **Rationale:** Provides a consistent, traceable, and physically meaningful measure of source output.
    *   **Implementation:** Use S_K for source ordering, calibration certificates (NIST/ADCL), planning system input/output, prescriptions, and documentation.
    *   **Dose Rate Constant (Λ):**
        *   Definition: Dose rate in medium per unit air kerma strength at 1 cm distance on the transverse axis ($cGy \cdot h^{-1} \cdot U^{-1}$).
        *   Accounts for differences in dose deposition between different source designs of the same radionuclide (e.g., 125I models).
        *   Must be obtained from reliable measurements or calculations (e.g., TG-43 recommendations).
*   **B. Source Strength Calibration:**
    *   **Traceability:** Calibrations must be traceable to NIST standards.
        *   **Direct Traceability:** Source or instrument calibrated against a national standard (NIST/ADCL).
        *   **Secondary Traceability:** Calibration by comparison with a source/instrument having direct traceability.
        *   **Secondary Traceability by Statistical Inference:** Calibration of a random sample from a batch.
    *   **Instrumentation:** Well-type ionization chambers are essential.
        *   Requires calibration factors specific to radionuclide and source design.
        *   Regular constancy checks with long-lived sources (e.g., 137Cs) are crucial (tolerance < 1%).
        *   Temperature/pressure corrections needed for air-communicating chambers.
    *   **Calibration Frequency & Sampling (LDR):**
        *   Calibrate *all* long half-life sources (e.g., 137Cs).
        *   Short half-life sources (e.g., 192Ir, 125I, 103Pd):
            *   Small batches: Calibrate all.
            *   Large batches (loose seeds): Calibrate random sample (>= 10%).
            *   Large batches (ribbons): Calibrate >= 10% or >= 2 ribbons (whichever is larger).
            *   Sterile sources: Calibrate a representative non-sterile source.
    *   **Verification of Vendor Calibration:**
        *   Institution *must* have a system to measure source strength independently.
        *   Verify vendor calibration before clinical use.
        *   **Tolerance (Mean of Batch):** Discrepancy <= 3% is acceptable. Investigate > 3%; report > 5% to vendor.
        *   **Tolerance (Individual Source):** Maximum deviation from batch mean <= 5%.
    *   **Source Uniformity/Integrity:**
        *   Verify uniformity of long half-life sources initially (e.g., autoradiograph).
        *   Visually inspect ribbons for seed spacing and count.
    *   **Calibration of High Strength Sources (HDR/PDR 192Ir):**
        *   **Challenge:** No direct NIST primary standard exists (at time of TG-56 publication).
        *   **Recommendation:** Use the **interpolative free-air secondary standard** method.
            *   Measure air kerma rate at distance (10-100 cm) with a buildup-capped ion chamber.
            *   Derive 192Ir calibration factor by interpolating between traceable 137Cs/orthovoltage factors.
            *   Requires corrections (room scatter, ion recombination, fluence gradients).
        *   **Implementation:**
            *   **Preferred:** Use a well-characterized re-entrant chamber calibrated for HDR 192Ir S_K by an accredited ADCL.
            *   **Alternative (Not Recommended):** Implement the free-air standard locally using a calibrated external beam chamber.
        *   **Requirement:** Physicist *must* calibrate *each* HDR/PDR source before clinical use using the institution's traceable system.
        *   **Confirmatory Check:** Perform a check using a *different* (tertiary) system (detector + electrometer) capable of detecting 5% errors to ensure redundancy.

### IV. Implant Design and Evaluation

*   **A. Manual Methods (Historical Context):**
    *   Manchester System (Paterson-Parker rules)
    *   Quimby System
    *   Memorial Nomographs
    *   Paris System (focus on geometry, basal dose points)
*   **B. Computer Methods of Implant Design:**
    *   **Applicator-Based Planning:** Using pre-defined applicator geometries and source loadings (common for GYN).
    *   **Image-Based Planning:** Using CT, MR, or US to define target volumes and critical structures for customized implants (e.g., prostate, brain).
        *   Requires accurate image registration and source localization.
*   **C. Dose Planning and Evaluation:**
    *   **Isodose Distributions:** Visual assessment of target coverage and avoidance of critical structures.
    *   **Dose Metrics (Examples):**
        *   Matched Peripheral Dose (MPD)
        *   Maximum Continuous-Contour Dose
    *   **Dose Volume Histograms (DVHs):**
        *   **Essential** for quantitative evaluation.
        *   **Integral (Cumulative) DVHs:** Plot volume receiving >= specified dose.
        *   **Differential DVHs:** Plot volume receiving dose within a specific range.
        *   **Target-Specific DVHs:** Require 3D target delineation (e.g., V100, D90 for target).
        *   **Natural Histogram:** Suppresses inverse square law effect, useful for assessing uniformity.
    *   **Quality Quantifiers (Derived from DVHs):**
        *   **Conformity Index (CI):** Ratio of treatment volume (e.g., prescription isodose volume) to target volume.
        *   **Homogeneity Index (HI) / Dose Homogeneity Index (DHI):** Measures dose uniformity within the target or treatment volume (e.g., fraction of volume receiving 100-150% of prescription dose).
        *   **Dose Non-uniformity Ratio (DNR):** Measures high dose regions (e.g., fraction of volume receiving >150% of prescription dose).
*   **D. Dose Specification and Reporting:**
    *   **Goal:** Standardize reporting for meaningful comparison of clinical outcomes.
    *   **Challenges:** Steep dose gradients, variations in practice.
    *   **ICRU Recommendations (Intracavitary - Report 38):**
        *   Report source strength, time, isodose contours.
        *   Report dimensions of 60 Gy isodose volume (combined EBRT + brachy).
        *   Report doses to specific Bladder and Rectal points.
        *   Report doses to points representing pelvic lymph nodes.
        *   *Critique:* ICRU reference volume dimensions (H, W, T) are highly correlated with total reference air kerma (or mgRaEq h) and may not be independent prognostic factors.
    *   **ICRU Recommendations (Interstitial - Report 58):** (Published after TG-56, but relevant)
        *   Focus on CT/MR-based target definition.
        *   Recommend reporting D90, V100, V150, V200 for target.
        *   Recommend reporting doses to relevant critical structures.
    *   **ABS Recommendations:**
        *   Emphasize practical clinical reporting.
    *   **AAPM Recommendations (TG-56):**
        *   **Intracavitary:**
            *   Adopt **Integrated Reference Air Kerma (IRAK)** instead of mgRaEq h.
                *   $K_{ref} = \sum_{i=1}^{N} (S_{K,i} \cdot t_i)$ (Units: cGy cm2)
            *   Develop written policies defining prescriptions based on clinical parameters.
            *   Maintain consistency with historical techniques when introducing new technology (sources, applicators, afterloaders) to ensure predictable outcomes.
            *   Physicist role is crucial in managing technological transitions.
        *   **Interstitial:**
            *   Specify dose relative to a defined target volume.
            *   Use image-based planning and evaluation where possible.
            *   Report relevant DVH parameters (e.g., D90, V100).

### V. Performing a Brachytherapy Procedure (Clinical Workflow & QA)

*   **A. Initial Planning:** Collaboration between oncologist and physicist.
*   **B. Treatment Prescription:** Clear, unambiguous, documented prescription including radionuclide, S_K, total dose or dose rate, treatment volume/points, fractionation (if applicable).
*   **C. Ordering Sources:** Use S_K, specify date/time needed.
*   **D. Receiving Sources:** Document receipt, perform radiation survey, verify label vs. order, secure storage.
*   **E. Checking Sources:**
    *   Verify physical integrity, radionuclide, S_K (as per Section III.B).
    *   Check dimensions, serial numbers, color coding.
    *   Perform leak tests as required.
*   **F. Source and Applicator Preparation:**
    *   Aseptic technique.
    *   Verify correct sources, applicators, loading sequence.
    *   Specific checks for seeds, ribbons, tubes.
*   **G. Loading Applicators and Sources:**
    *   Radiation safety procedures (time, distance, shielding).
    *   Verification of correct loading (manual or remote afterloader).
    *   **Remote Afterloader Specific:** Verify connection integrity, guide tube lengths, source transit.
*   **H. Removal, Security, and Return:**
    *   Account for all sources removed (temporary implants).
    *   Perform patient and room surveys.
    *   Secure storage or packaging for return/disposal.
    *   **Permanent Implants:** Final survey, documentation.
    *   **HDR:** Source retraction checks, emergency procedures.
*   **I. Source Localization:**
    *   Post-implant imaging (radiographs, CT, MR, US) appropriate for the technique.
    *   Accurate reconstruction of source/applicator positions relative to anatomy.
*   **J. Treatment Evaluation:**
    *   Perform dose calculations based on localized sources/dwell positions.
    *   Evaluate target coverage (isodoses, DVHs) and critical structure doses.
    *   Independent check of calculations (manual or computer).
    *   **HDR Specific:** Verify total time, dwell times vs. plan.
*   **K. Recording Physics Data:**
    *   Comprehensive documentation in patient chart: prescription, source details (radionuclide, S_K, calibration), implant geometry, calculations, DVHs, total dose/time, physicist signature/date.

### VI. Recommended QA Program for Brachytherapy Equipment

*   **A. Manual Afterloading Brachytherapy:**
    *   **Sources:** Calibration, leak testing, uniformity, inventory (as per Section III.B and Table I).
    *   **Applicators:** Inspect for damage, verify dimensions, ensure compatibility.
    *   **Calibration Equipment (Well Chamber):** Regular constancy checks, ADCL calibration.
    *   **Treatment Planning System:** (See Section VI.C).
*   **B. Remote Afterloading Brachytherapy Devices (HDR/PDR):**
    *   **Critical Importance:** Higher risk due to source strength and complexity.
    *   **Acceptance Testing (Vendor & Physicist):** Comprehensive verification of all functional and safety features before clinical use.
    *   **Commissioning:** Characterize device performance, obtain data for planning system.
    *   **Routine QA Frequencies:** Daily, Monthly, Quarterly, Annual.
    *   **1. Daily QA (Before First Treatment):**
        *   Safety checks: Door interlock, audio/visual monitors, radiation monitor, emergency stops.
        *   Console functions: Battery/power status, console messages.
        *   Source control: Transit test (dummy source), source position accuracy (autoradiograph/jig), timer accuracy/linearity.
        *   *Practical Guidance:* Develop efficient checklist, ensure therapist training.
    *   **2. Monthly/Quarterly QA:**
        *   More extensive checks of items from daily QA.
        *   Source calibration verification (constancy check).
        *   Timer accuracy and linearity (more thorough).
        *   Source position accuracy (multiple channels/catheters).
        *   Decay calculation verification.
        *   Inspection of applicators and transfer tubes.
        *   Review of safety procedures and emergency drills.
    *   **3. Annual QA:**
        *   Comprehensive repetition of acceptance tests.
        *   Full source calibration (traceable).
        *   Mechanical and electrical safety inspection.
        *   Review of entire QA program, procedures, and records.
        *   Preventive maintenance as per vendor recommendations.
*   **C. QA for Treatment Planning and Evaluation Systems:**
    *   **Acceptance/Commissioning:** Verify algorithm accuracy against published data/manual calculations for various sources and geometries. Test input/output, digitizer/image transfer accuracy, dose display, DVH calculation.
    *   **Routine QA:**
        *   Regular checks of calculation accuracy using standard test cases.
        *   Verification of source library data.
        *   Checks on consistency of output devices (printer/plotter).
        *   Verification of data transfer integrity (imaging, afterloader links).
        *   Review of software updates/changes.

## Appendices

*   **Appendix A:** Definition of a Qualified Medical Physicist (Certification, experience).
*   **Appendix B:** Brachytherapy Team Members and Physicist Responsibilities.
*   **Appendix C:** Recommended Instrumentation (Well chamber, survey meters, electrometers, phantoms, etc.).
*   **Appendix D:** Major References to NRC Documents.

*Disclaimer: This deep dive summarizes key aspects of AAPM TG-56. Users should always refer to the original report for complete details and context.*
