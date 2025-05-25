# Deep Dive: AAPM MPPG 5.b - Commissioning and QA of TPS Dose Calculations (Electrons) (Section 4.2)

**Report:** AAPM Medical Physics Practice Guideline 5.b (MPPG 5.b), "Commissioning and QA of treatment planning dose calculations—Megavoltage photon and electron beams," published in the Journal of Applied Clinical Medical Physics, Vol. 23, No. 9, September 2022.

**Disclaimer:** This document provides a detailed interpretation and practical guidance based on AAPM MPPG 5.b. It is intended for educational purposes within the Radiation Oncology Academy curriculum and should not substitute the original report or professional judgment. Always refer to the official AAPM publications and institutional protocols for clinical practice.

**Context:** MPPG 5.b represents the current standard of practice for the commissioning and ongoing quality assurance (QA) specifically focused on the **dose calculation algorithms** within Treatment Planning Systems (TPS). It provides concrete, actionable tests, procedures, and quantitative tolerance levels, building upon the broader QA philosophy of TG-53. It recognizes the different capabilities and limitations of various algorithm types (Type A, B, C) and sets expectations accordingly.

## 1. Purpose and Scope: Ensuring Calculation Accuracy

The primary goal of MPPG 5.b is to ensure that TPS dose calculation algorithms accurately predict dose distributions under a wide range of clinically relevant conditions. This involves:

*   **Standardized Commissioning:** Providing a minimum set of tests and procedures to verify algorithm performance before clinical use.
*   **Quantitative Tolerances:** Defining acceptable levels of agreement between calculated and measured dose values for various scenarios.
*   **Algorithm-Specific Expectations:** Acknowledging that different algorithms (e.g., Pencil Beam vs. Monte Carlo) have different intrinsic accuracies and setting tiered tolerances.
*   **Ongoing QA:** Establishing requirements for periodic checks to ensure algorithm performance remains stable over time and after system updates.

**Focus:** Unlike TG-53 which covers the entire planning *process*, MPPG 5.b zooms in specifically on the **dose calculation engine** itself.

**Practical Implication:** Adherence to MPPG 5.b provides documented evidence that the TPS dose calculation algorithm has been rigorously tested and meets minimum standards for clinical use, enhancing patient safety and treatment accuracy.

## 2. Commissioning Electron Dose Calculation Algorithms: The Test Suite

MPPG 5.b details a comprehensive suite of tests comparing TPS calculations against reliable measurements (typically ion chamber or diode measurements in a water phantom, or film). These tests must be performed for all clinically used electron energies.

**Key Test Categories and Practical Guidance for Electrons:**

**2.1. Basic Beam Data Verification (Homogeneous Water Phantom):** Validates the fundamental beam model.

*   **Percent Depth Dose (PDD) Curves:**
    *   **Test:** Compare calculated vs. measured PDDs for a range of field sizes/applicators (e.g., 6x6, 10x10, 20x20 cm²) at the standard SSD (e.g., 100 cm).
    *   **Analysis Points:** Evaluate agreement at key points: surface dose ($D_s$), depth of maximum dose ($d_{max}$), depths in the fall-off region (e.g., $R_{90}, R_{80}, R_{50}$), practical range ($R_p$), and the Bremsstrahlung tail.
    *   **Tolerances (Examples - may vary slightly based on region/algorithm type):**
        *   Low Gradient Region (near $d_{max}$): Dose difference (DD) $\le 2\%$.
        *   High Gradient Region (fall-off): Distance-to-agreement (DTA) $\le 2$ mm.
        *   $R_{50}$ Depth: Agreement $\le 1$ mm.
        *   Surface Dose: DD $\le 3-5\%$ (can be challenging).
    *   **Practical Steps:** Use accurately measured PDDs (ideally with parallel-plate chamber per TG-70) as the gold standard. Perform point dose calculations or export calculated PDDs from TPS for comparison. Document comparisons graphically and numerically.
*   **Beam Profiles (Off-Axis Ratios - OARs):**
    *   **Test:** Compare calculated vs. measured profiles for representative field sizes/applicators at multiple depths (e.g., $d_{max}$, $R_{90}$, $R_{50}$). Ensure measurements cover the full field including the penumbra.
    *   **Analysis Points:** Evaluate agreement in the central axis region (flatness), penumbra region (width, position), and overall field size.
    *   **Parameters:** Field width (e.g., at 50% level), penumbra width (e.g., 80%-20% or 90%-10%), flatness, symmetry.
    *   **Tolerances (Examples):**
        *   Central 80% Field Width: DD $\le 2-3\%$.
        *   Penumbra Region (e.g., 80%-20%): DTA $\le 2$ mm.
        *   Field Width (at 50%): Agreement $\le 2$ mm.
    *   **Practical Steps:** Use high-resolution measurements (diode, small chamber, film). Compare calculated and measured profiles graphically. Analyze key parameters quantitatively.

**2.2. Output Factors:** Verifies relative dose output under different conditions.

*   **Test:** Compare calculated vs. measured relative output factors (dose/MU relative to reference field) for:
    *   **Applicator Factors:** All standard applicators.
    *   **Field Size Factors:** Representative square/rectangular field sizes within applicators.
    *   **Cutout Factors:** Representative custom cutout shapes (squares, circles, irregular) and sizes relative to the open applicator. This is **critical** for electrons due to significant scatter effects from the cutout edges.
*   **Measurement Point:** Typically at $d_{max}$ for each specific field size/cutout.
*   **Tolerance:** DD $\le 2-3\%$.
*   **Practical Steps:** Measure output carefully using a reliable chamber. Ensure TPS calculation conditions match measurement setup (SSD, depth). Pay close attention to cutout factors as these often show larger variations.

**2.3. SSD Dependence:** Validates the TPS correction for non-standard distances.

*   **Test:** Compare calculated vs. measured dose or output changes at various SSDs (e.g., 90, 100, 110, 120 cm) relative to the standard SSD.
*   **Analysis:** Verify the accuracy of the TPS inverse square correction method (often using a virtual/effective SSD, $SSD_{eff}$).
*   **Tolerance:** DD $\le 2\%$.
*   **Practical Steps:** Perform measurements at different SSDs in a water phantom or solid phantom. Compare ratios of readings/calculations to expected inverse square behavior using the $SSD_{eff}$ determined during beam data commissioning.

**2.4. Heterogeneities:** Crucial test of algorithm robustness for electrons.

*   **Test:** Compare calculated vs. measured dose distributions in phantoms containing tissue inhomogeneities (e.g., slab phantoms with materials simulating lung, bone, air).
    *   **Geometries:** Water/Lung/Water, Water/Bone/Water, Water/Air/Water.
    *   **Measurements:** Measure PDDs along the central axis and potentially profiles at different depths within and beyond the heterogeneity.
*   **Analysis:** Evaluate:
    *   Dose perturbations just before, within, and just after the heterogeneity.
    *   Shifts in $d_{max}$ and the dose fall-off region.
    *   Changes in penumbra width near heterogeneity edges (if measuring profiles).
*   **Tolerances:** Tolerances are generally **wider** than for homogeneous cases and **depend heavily on the algorithm type**:
    *   **Type A (MC, GBBS):** Expected to perform best. Tolerances might be in the range of DD $\le 3-5\%$ or DTA $\le 3$ mm, but may be larger in complex interface regions.
    *   **Type B/C (PB):** Known limitations. Deviations can be significant (DD > 5-10%, DTA > 5 mm), especially near interfaces and within low-density regions. The key is to **understand and document** these limitations.
*   **Practical Steps:** Use well-characterized slab phantoms. Perform careful measurements (film or small detectors are often useful near interfaces). Compare calculations and measurements, focusing on the regions of maximum expected deviation. **Crucially, establish clinical protocols that account for known algorithm limitations in heterogeneous sites.**

**2.5. Beam Modifiers:** Verifies handling of common clinical accessories.

*   **Bolus:**
    *   **Test:** Compare calculated vs. measured PDDs with bolus material placed on the phantom surface. Verify the shift in $d_{max}$ and the change in surface dose.
    *   **Tolerance:** DD $\le 2-3\%$ or DTA $\le 2$ mm for PDD shift.
    *   **Practical Steps:** Use clinically relevant bolus materials and thicknesses. Ensure no air gaps between bolus and phantom during measurement.
*   **Cutouts:** (Covered under Output Factors, but verification of profile shape is also important).
    *   **Test:** Compare calculated vs. measured profiles for fields shaped by custom cutouts.
    *   **Analysis:** Check penumbra shape and field size agreement.
    *   **Tolerance:** Similar to standard profile tolerances (e.g., DTA $\le 2$ mm in penumbra).

**2.6. Oblique Incidence / Irregular Surfaces:** Simulates clinical setup variations.

*   **Test:** Compare calculated vs. measured dose distributions for beams incident on angled phantom surfaces or phantoms with curved surfaces.
*   **Analysis:** Evaluate shifts in PDDs, changes in surface dose, and profile distortions.
*   **Tolerance:** DD $\le 3-5\%$ or DTA $\le 3$ mm (may depend on angle and algorithm).
*   **Practical Steps:** Use angled or curved phantoms. Measurements can be challenging; film or 2D arrays might be useful.

## 3. Ongoing Quality Assurance (QA): Maintaining Accuracy

Commissioning establishes the baseline; ongoing QA ensures continued accuracy.

*   **Frequency:** MPPG 5.b recommends **annual** QA as a minimum for comprehensive algorithm checks, with more frequent checks for critical parameters.
*   **Scope (Annual):** Perform a subset of the commissioning tests, focusing on representative cases covering:
    *   Basic PDDs and profiles.
    *   Output factors (reference field, representative applicator/cutout).
    *   A representative heterogeneity case.
    *   A representative oblique incidence or bolus case.
    *   Compare results against the commissioning baseline data.
*   **Checks After Updates:** Crucial step after any TPS software update, operating system change, hardware replacement, or modification of beam data.
    *   **Scope:** Perform tests relevant to the update. For major algorithm changes, near-full recommissioning might be required. For minor updates, a targeted subset of tests may suffice, based on vendor information and risk assessment.
    *   **Requirement:** QA *must* be performed and results verified *before* the updated system is used clinically.
*   **Patient-Specific Plan Checks:** MPPG 5.b focuses on the *algorithm*, but its results inform the confidence in patient-specific plans. It complements, but does not replace, patient-specific checks like independent MU calculations (essential for all plans) and measurement-based IMRT/VMAT QA (per TG-218).

**Practical Guidance:** Develop a detailed annual QA protocol based on MPPG 5.b tests. Maintain meticulous records of all QA results, including baseline commissioning data. Establish clear procedures and responsibilities for performing QA after updates.

## 4. Algorithm Types and Expectations: Know Your Algorithm!

MPPG 5.b explicitly categorizes algorithms and sets tiered expectations:

*   **Type A (e.g., Monte Carlo - MC, Grid-Based Boltzmann Solvers - GBBS):** Explicitly model electron transport physics. Highest accuracy, especially in complex geometries and heterogeneities. Expected to meet the tightest tolerances.
*   **Type B (e.g., Pencil Beam - PB with 3D scatter kernels, Convolution/Superposition):** Approximate electron scattering using analytical models. Intermediate accuracy. Generally good in water but struggle significantly with complex heterogeneities (interfaces, lateral effects).
*   **Type C (e.g., Simple Pencil Beam with 1D corrections):** Most basic approximation. Significant limitations, especially with heterogeneities, small fields, and oblique incidence. Tolerances are loosest, and **clinical use should be carefully restricted and validated.**

**Physicist Responsibility:** The medical physicist MUST:
*   Know which type of algorithm is implemented in their TPS.
*   Understand the inherent strengths and weaknesses of that algorithm, particularly regarding electron transport.
*   Perform commissioning tests (per MPPG 5.b) to quantify the algorithm's accuracy under various conditions.
*   Establish clinical protocols and potentially planning constraints based on the validated limitations of the algorithm (e.g., avoiding use of Type C algorithms for lung cases without significant validation or correction).

## 5. Relevance and Conclusion: The Standard for Calculation QA

MPPG 5.b is the current, essential standard for ensuring the accuracy of TPS dose calculations for electron beams.

*   **Actionable Guidance:** Provides specific tests, procedures, and tolerances.
*   **Safety Focus:** Directly addresses the accuracy of the calculated dose, a critical component of treatment safety.
*   **Complements TG-53:** Provides the detailed 

"how-to" for algorithm verification, ensuring calculations meet minimum standards.
*   **Consistency:** Promotes consistency in commissioning practices across different institutions.
*   **Algorithm Comparison:** Provides a framework for comparing the performance of different algorithms and understanding their specific limitations.

**Conclusion:** MPPG 5.b is the essential, practical standard for the commissioning and ongoing QA of electron dose calculation algorithms in modern TPS. By mandating specific tests and quantitative tolerances, it ensures that algorithms are rigorously evaluated before clinical use and monitored over time. Adherence to MPPG 5.b, in conjunction with the process-oriented framework of TG-53 and the measurement guidance of TG-70, is crucial for ensuring the accuracy, reliability, and safety of electron beam therapy planning.

