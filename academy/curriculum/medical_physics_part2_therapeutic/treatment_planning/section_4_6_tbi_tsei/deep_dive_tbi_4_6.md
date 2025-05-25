# Section 4.6: Deep Dive - Total Body Irradiation (TBI) Physics and Dosimetry (Based on AAPM Report 17 & OMP)

This document provides an in-depth exploration of the physical aspects and dosimetry procedures for Total Body Irradiation (TBI), primarily drawing from the recommendations and discussions within AAPM Report 17 (Task Group 29) and supplemented by information from the Oncology Medical Physics (OMP) webpage. The focus is on achieving graduate-level detail, practical implementation insights, and integrated examples.

## 1. Introduction and Clinical Context (Brief Recap)

*   **Purpose:** TBI delivers a relatively uniform radiation dose to the entire body, primarily used for myeloablation and immunosuppression before Hematopoietic Cell Transplantation (HCT) for various malignant and non-malignant diseases. Lower doses are used palliatively for certain widespread cancers (e.g., CLL).
*   **Challenge:** Delivering a uniform dose (target ±10% or better) across a large, irregular volume while respecting critical organ tolerances (especially lungs) is technically demanding.
*   **Accuracy Requirement:** AAPM Report 17 emphasizes the need for high accuracy (ideally better than ±5%) due to steep dose-response curves for both efficacy and toxicity (e.g., pneumonitis). The APARA principle (As Precise As Readily Achievable) is paramount.

## 2. Irradiation Methods and Facility Considerations (AAPM Report 17, Section 2)

Report 17 outlines various methods, reflecting the historical evolution and available equipment. The choice impacts dosimetry complexity and achievable uniformity.

*   **Dedicated Facilities (Multiple/Dual Sources):** Historically used Cobalt-60 sources arranged specifically for TBI. Offers potentially good uniformity but less common now.
*   **Dedicated Facilities (Single Source):** Often a linac in a large, dedicated room allowing for very extended SSDs (e.g., > 5 meters).
*   **Conventional Units Modified for Large Fields:** Using existing linacs by extending SSDs within standard vaults.
    *   **Horizontal Beams:** Gantry at 90° or 270°, patient positioned far from isocenter (standing, sitting, lying). Most common approach.
    *   **Vertical Beams:** Gantry at 0° or 180°. Requires either treating the patient in a pit below floor level or reflecting the beam off the ceiling (rare).
*   **Conventional Treatment Units (Standard SSDs):** Requires multiple matched fields (e.g., sequential AP/PA fields covering upper, mid, and lower body). Complex field matching and dose uniformity challenges, generally discouraged if extended SSD is feasible.
*   **Selecting a Technique:** Factors include available equipment, room size, desired dose rate, required uniformity, patient positioning capabilities, and shielding needs.
*   **Back-up Technique:** Report 17 strongly recommends having a fully commissioned and documented back-up TBI technique in case the primary method becomes unavailable.

## 3. Basic Phantom Dosimetry (AAPM Report 17, Section 3)

This forms the foundation for TBI commissioning. All measurements must be performed under the specific geometric conditions used for treatment (SSD, field size, gantry/collimator angles, presence of scatterers/trays).

*   **Dosimetry Phantoms:**
    *   **Water Tank:** Must be large enough to provide full scatter conditions (e.g., 60x60x60 cm or larger). Used for fundamental beam data (PDD/TMR, profiles, output factors).
    *   **Solid Phantoms:** Water-equivalent plastic (e.g., Solid Water™, Plastic Water®) slabs stacked to appropriate dimensions. Useful for point dose measurements, IVD calibration, and simulating specific setups.
    *   **Anthropomorphic Phantoms:** Essential for end-to-end testing, verifying dose in complex anatomy, assessing compensator/shielding effectiveness, and validating IVD procedures.
*   **Dosimeters:**
    *   **Ionization Chambers:** Calibrated cylindrical chambers (Farmer type) are the standard for absolute dose calibration. Must use appropriate corrections (P_ion, P_pol, P_TP, N_D,w, k_Q). Parallel-plate chambers may be useful for surface dose measurements if spoilers are used.
    *   **TLDs/OSLDs:** Used for point dose measurements, uniformity checks in phantoms, and essential for *in vivo* dosimetry. Require careful calibration under TBI beam conditions.
    *   **Diodes:** Can be used for relative dosimetry (profiles) and IVD, but require corrections for energy, temperature, and dose rate dependence.
    *   **Film (Radiochromic):** Excellent for high-resolution 2D dose distribution mapping (uniformity checks, compensator verification) in phantoms.
*   **Dose Calibration:**
    *   **Reference Point:** Typically midline at mid-separation in the large phantom at the TBI treatment SSD.
    *   **Procedure:** Follow TG-51 adapted for non-reference conditions. Measure charge (M), apply corrections, use N_D,w from standard calibration, and determine dose per MU at the reference point.
    *   **Consistency:** Output should be checked regularly under TBI conditions.
*   **Central Ray Data:** PDD or TMR curves must be measured in the large phantom at the TBI SSD. Data from standard SSD cannot be directly used due to changes in scatter and divergence.
*   **Inverse Square Law Test:** Verify ISL holds accurately over the range of distances used, ensuring distance indicators are correct.
*   **Output Factors (Sc, Sp, Scp):** Critical for MU calculations. Must be measured for the large TBI field size at the treatment SSD.
    *   *Measurement:* Scp often measured directly as the ratio of dose at reference depth in the large phantom (TBI field) to dose at the same depth in a small phantom (reference 10x10 field) at the reference SSD, correcting for ISL.
    *   *OMP Note:* Suggests calculations based on nominal beam data vary by <1.5% from TBI-specific data, but Report 17 emphasizes direct measurement.
*   **Beam Profiles:** Measure transverse and longitudinal profiles at various depths in the large phantom at TBI SSD. Assess flatness, symmetry, and penumbra under treatment conditions.
*   **Attenuation Data:** Measure transmission factors for blocking tray, compensator materials, and shielding materials using broad beam geometry representative of TBI.

## 4. Patient Dosimetry (AAPM Report 17, Section 4)

Addresses the complexities of delivering a prescribed dose accurately to the patient.

*   **Dose Prescription:** Must be clearly defined.
    *   **Location:** E.g., Midline at umbilicus, average midline dose, dose to isocenter (if applicable).
    *   **Dose & Fractionation:** Total dose, dose per fraction, number of fractions, time interval (e.g., BID).
    *   **Dose Rate:** Specified average dose rate at the prescription point (e.g., < 20 cGy/min).
    *   **Uniformity Goal:** E.g., ±10% along the patient midline or within a target volume.
    *   **Organ Constraints:** E.g., Mean lung dose < 10 Gy (fractionated), maximum lens dose.
*   **Effects of Patient Size and Shape:** Major source of dose variation.
    *   **Incident Contour Variation:** Leads to dose differences (ISL, attenuation).
    *   **Lack of Lateral Scatter:** Reduced dose near the patient's sides compared to the center.
    *   **Lack of Backscatter:** Reduced dose near the exit surface.
*   **Methods of Compensating for Contour Variation:**
    *   **Tissue Equivalent Bolus:** Placed on patient to build up missing tissue. Simple but increases skin dose and can be uncomfortable.
    *   **Missing Tissue Compensators:** Filters placed far from the patient.
        *   *Design:* Requires patient contour data (CT or manual measurements), beam data (TMR/TPR), and compensator attenuation data. Algorithms range from simple 1D calculations to complex 3D TPS-based designs.
        *   *Verification:* Must be verified, e.g., using film in a phantom or IVD on the patient.
        *   *Practical Example:* To compensate for the thinner neck vs. trunk in a lateral setup, thicker lead/brass is placed in the beam path corresponding to the neck region.
*   **Inhomogeneities (Lungs):** Critical consideration.
    *   **Dose Increase:** Dose within and beyond lungs is significantly higher (10-25%) than water-equivalent calculations predict due to reduced attenuation and scatter.
    *   **Methods of Lung Dose Determination:**
        *   *Calculation:* Using heterogeneity correction algorithms (Effective Path Length, ETAR, Convolution/Superposition, Monte Carlo) based on CT data.
        *   *Measurement (Phantom):* Using anthropomorphic phantoms with lung-equivalent materials and detectors.
        *   *Measurement (In Vivo):* Using IVDs placed entrance/exit over the lung region, combined with calculations or phantom-derived correction factors.
    *   **Methods of Compensating for Lungs (Shielding):**
        *   *Goal:* Reduce mean lung dose below tolerance.
        *   *Design:* Custom blocks (Cerrobend) or MLCs shaped to lung contours. Often partial transmission (e.g., 50%) to avoid underdosing adjacent tissue/tumor.
        *   *Verification:* Port films (if feasible), IVD under the shield.
*   **Dose Distributions:** Full 3D dose distributions are ideal (from TPS) but challenging to obtain accurately for TBI. At minimum, midline dose profiles and doses to critical organs should be estimated/measured.
*   **Anthropomorphic Phantom Measurements:** Crucial step before treating patients. Irradiate a phantom representing the patient, including compensators and shields. Measure dose at multiple points (midline, organs, surface) using ion chambers, TLDs/OSLDs, film. Compare measurements to calculations/prescription goals.
*   **In Vivo Measurements (IVD):** Essential final verification on the patient.
    *   **Placement:** Multiple points (e.g., forehead, neck, chest, umbilicus entrance/exit, pelvis, thigh, ankle, points over lungs/kidneys).
    *   **Analysis:** Compare measured doses to expected doses. Deviations >5-10% should be investigated. Can be used to adjust subsequent fractions if significant discrepancies are found consistently.
    *   *Practical Example:* IVDs placed entrance/exit at umbilicus measure 160 cGy and 145 cGy, respectively. Patient thickness is 30 cm. Using a TMR-based method or pre-determined factors, the midline dose is estimated. If the target was 150 cGy, this result might be acceptable or prompt investigation depending on tolerance levels.

## 5. Special Considerations (AAPM Report 17, Section 5)

*   **Junctions for HBI:** If treating half-body sequentially, careful field matching is needed to avoid significant hot or cold spots at the junction. Techniques include small gaps, field feathering, or customized blocking.
*   **Shielding:** Design and verification of lung, kidney, gonad, or lens shields. Ensure correct placement and account for beam divergence and penumbra.
*   **Port Filming:** Verification of patient positioning and shield placement. Challenging at extended SSDs due to poor image quality and large field size. EPIDs may offer better options if available and usable at extended distances.

## 6. Summary of Recommendations (AAPM Report 17, Section 6 - Paraphrased & Expanded)

1.  **Technique Selection:** Choose a technique (preferably extended SSD) that maximizes uniformity and minimizes dose rate, considering available resources. Have a commissioned back-up.
2.  **Basic Dosimetry:** Perform comprehensive beam characterization (output, PDD/TMR, profiles, scatter factors, attenuation data) under TBI conditions using large phantoms.
3.  **Calibration:** Calibrate dose per MU accurately at a reference point under TBI conditions.
4.  **Compensation:** Use appropriate methods (compensators preferred over bolus) to achieve dose uniformity (aim for ≤ ±10% midline).
5.  **Inhomogeneities:** Account for lung dose increase using reliable calculation methods or measurements. Use lung shielding to meet tolerance constraints.
6.  **Patient Dose Specification:** Clearly define prescription point, dose, fractionation, dose rate, uniformity goals, and organ constraints.
7.  **Phantom Verification:** Perform end-to-end tests using anthropomorphic phantoms before clinical implementation.
8.  **In Vivo Dosimetry:** Implement a robust IVD program for *every* patient to verify delivered dose.
9.  **Quality Assurance:** Establish a comprehensive QA program covering machine performance, dosimetry systems, and treatment procedures specific to TBI.
10. **Documentation:** Maintain meticulous records of all procedures, measurements, calculations, and patient treatments.

## 7. OMP Insights and MU Calculation Example

*   **OMP MU Formula:** Provides a practical formula for parallel-opposed TBI:
    *   MU_per_beam = (Prescribed_Dose_Midline / 2) / [Output * Sc * Sp * (SCD/SMD)^2 * TMR(d_mid, Sp_FS)]
        *   *Output:* cGy/MU at reference (e.g., 100 SSD, dmax, 10x10).
        *   *Sc:* Collimator scatter for jaw setting.
        *   *Sp:* Phantom scatter for effective field size at patient midline.
        *   *SCD:* Source-to-calibration distance (100 cm).
        *   *SMD:* Source-to-midline distance (TBI setup).
        *   *TMR:* Tissue maximum ratio at midline depth (d_mid) for effective field size (Sp_FS).
*   **Clinical Example (OMP Style):**
    *   *Prescription:* 150 cGy to midline, 30 cm separation (d_mid=15cm), 400 cm SMD, 6 MV.
    *   *Reference Output:* 1.0 cGy/MU (100 SSD, dmax, 10x10).
    *   *Factors (Assume measured/calculated for TBI max field):* Sc=1.05, Sp=1.10 (for effective FS at patient), TMR(15cm, eff_FS)=0.750.
    *   *MU per beam:* (150/2) / [1.0 * 1.05 * 1.10 * (100/400)^2 * 0.750]
        *   MU = 75 / [1.0 * 1.05 * 1.10 * 0.0625 * 0.750] = 75 / 0.05414 ≈ 1385 MU.
    *   *(Note: This result is similar to the previous example, differences arise from how Sc/Sp/TMR are defined and measured relative to reference conditions).*

## 8. Conclusion

Accurate and safe TBI delivery requires meticulous attention to physics principles and dosimetry procedures. Comprehensive commissioning, robust QA, use of compensation and shielding, and routine in vivo dosimetry are essential components highlighted by AAPM Report 17 and practical guidelines. Achieving the required uniformity and respecting organ tolerances demands a deep understanding of the unique challenges posed by these large-field, extended-distance treatments.


