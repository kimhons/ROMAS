# Deep Dive: AAPM TG-70 - Clinical Electron Beam Dosimetry: Supplement to TG-25 (Section 4.2)

**Report:** AAPM Report No. 99, Task Group 70 (TG-70), "Clinical electron beam dosimetry: Supplement to the recommendations of Task Group 25," published by the AAPM, 2009.

**Disclaimer:** This document provides a detailed interpretation and practical guidance based on AAPM TG-70. It is intended for educational purposes within the Radiation Oncology Academy curriculum and should not substitute the original report or professional judgment. Always refer to the official AAPM publications and institutional protocols for clinical practice.

**Context:** Published nearly two decades after TG-25, TG-70 serves as a critical update, bridging the gap between the foundational principles of TG-25 and the modern absolute dosimetry protocol, TG-51. Electron beam technology and measurement techniques had evolved, necessitating revised recommendations for accurate clinical dosimetry.

## 1. Purpose and Scope: Updating Electron Dosimetry Practices

TG-70's primary objective was to modernize the recommendations for clinical electron beam dosimetry by:

*   **Integrating TG-51:** Explicitly incorporating the TG-51 protocol for reference (absolute) dosimetry, replacing the TG-21 based methods referenced in TG-25.
*   **Refining Relative Dosimetry Techniques:** Providing updated guidance on detector selection and measurement procedures for relative dose distributions (PDDs, profiles, output factors) based on improved understanding and technology.
*   **Addressing Modern Linacs:** Reflecting the characteristics and capabilities of contemporary linear accelerators.

**Practical Implication:** TG-70 is essential reading alongside TG-51 for any physicist performing electron beam calibrations or commissioning. It clarifies how to apply the TG-51 framework specifically to electrons and provides best practices for relative measurements needed for TPS commissioning and QA.

## 2. Reference Dosimetry: Applying TG-51 to Electrons

This is a cornerstone of TG-70. It definitively establishes TG-51 as the standard for absolute dose calibration of electron beams.

*   **Supersession:** TG-70 clearly states that TG-51 supersedes TG-21/TG-25 for determining absorbed dose to water under reference conditions.
*   **Reference Conditions:** Consistent with TG-51:
    *   **Phantom:** Water.
    *   **Field Size:** 10x10 cm² field size for energies with $R_{50} \ge 4.3$ cm (approx. 10 MeV). For lower energies ($R_{50} < 4.3$ cm), a 20x20 cm² field size is recommended to ensure adequate lateral scatter equilibrium, *or* the largest available applicator if 20x20 cm² is not available (provided it's at least 10x10 cm²).
    *   **SSD:** 100 cm (or the clinical standard SSD).
    *   **Depth:** Reference depth $d_{ref} = 0.6 R_{50} - 0.1$ cm.
*   **TG-51 Formalism:** The absorbed dose to water ($D_w^Q$) at the reference depth for electron beam quality Q is given by:
    $$ D_w^Q = M P_{gr}^Q k_{ecal} k_Q N_{D,w}^{Co-60} $$
    Let's break down the practical application of each term for electrons:
    *   **$M$ (Corrected Reading):** The electrometer reading corrected for:
        *   Temperature and Pressure ($P_{TP}$): Standard correction for vented chambers.
        *   Ion Recombination ($P_{ion}$): Measured using the two-voltage technique. Can be significant for pulsed beams, especially with parallel-plate chambers. TG-51 provides specific guidance.
        *   Polarity Effect ($P_{pol}$): Measured by reversing polarity. Should be small for well-guarded chambers.
        *   Electrometer Calibration Factor.
    *   **$N_{D,w}^{Co-60}$ (Calibration Factor):** The absorbed-dose-to-water calibration factor for the ionization chamber in a Co-60 beam, obtained from an Accredited Dosimetry Calibration Laboratory (ADCL).
    *   **$k_Q$ (Quality Conversion Factor):** Converts the Co-60 calibration factor to one applicable for the user's electron beam quality Q. This is the most critical factor specific to the beam quality.
        *   **Determination:** $k_Q$ values are provided in the TG-51 protocol (or its addendum) based on the **beam quality specifier $R_{50}$** and the **chamber type** (cylindrical or parallel-plate).
        *   **Practical Steps:**
            1.  Measure the electron beam PDD accurately (see Section 3).
            2.  Determine $R_{50}$ (depth beyond $d_{max}$ where dose is 50% of $D_{max}$) from the PDD.
            3.  Use this $R_{50}$ value to look up the appropriate $k_Q$ factor for your specific chamber model in the TG-51 tables.
    *   **$k_{ecal}$ (Co-60 Conversion Factor):** This factor is specific to **cylindrical chambers** only. It converts the older air-kerma ($N_K$) or exposure ($N_X$) based calibration factors (used with TG-21) into the $N_{D,w}^{Co-60}$ factor needed for TG-51. Values are provided in TG-51 based on the chamber model. For parallel-plate chambers, $k_{ecal}$ is implicitly included in their $N_{D,w}^{Co-60}$ factor provided by the ADCL.
    *   **$P_{gr}^Q$ (Gradient Correction Factor):** This factor corrects for the dose gradient across the volume of a **cylindrical chamber** when placed at the reference depth $d_{ref}$.
        *   **Determination:** Values are provided in TG-51 based on $R_{50}$ and the chamber's inner radius.
        *   **Parallel-Plate Chambers:** For parallel-plate chambers, the effective point of measurement is the inside surface of the proximal electrode, and $P_{gr}^Q = 1.0$ when the chamber is positioned with this surface at $d_{ref}$.
*   **Chamber Choice for Reference Dosimetry:**
    *   **Cylindrical Chambers:** Allowed by TG-51, but require both $k_{ecal}$ and $P_{gr}^Q$ corrections. Their use is generally discouraged for lower electron energies due to larger perturbation effects and gradient issues.
    *   **Parallel-Plate Chambers:** Recommended, especially for lower energies. They require an $N_{D,w}^{Co-60}$ calibration factor directly from the ADCL (which includes $k_{ecal}$) and have $P_{gr}^Q = 1.0$.

**Practical Workflow (TG-51 Calibration):**
1.  Setup the linac and water phantom under reference conditions (correct field size, SSD).
2.  Accurately measure the PDD to determine $R_{50}$.
3.  Calculate the reference depth $d_{ref} = 0.6 R_{50} - 0.1$ cm.
4.  Position the calibrated chamber (preferably parallel-plate) with its effective point of measurement at $d_{ref}$.
5.  Obtain the corrected electrometer reading $M$ (applying $P_{TP}$, $P_{ion}$, $P_{pol}$).
6.  Look up $N_{D,w}^{Co-60}$ from the chamber calibration certificate.
7.  Look up $k_Q$ from TG-51 tables using $R_{50}$ and chamber type.
8.  If using a cylindrical chamber, look up $k_{ecal}$ and $P_{gr}^Q$ from TG-51 tables.
9.  Calculate $D_w^Q$ using the TG-51 equation.
10. This $D_w^Q$ value corresponds to the dose delivered for a specific number of Monitor Units (MUs) under reference conditions, establishing the linac's absolute output (cGy/MU).

## 3. Relative Dosimetry Measurements: Refining TG-25

TG-70 provides updated best practices for measuring relative dose distributions, crucial for TPS commissioning.

*   **Detectors:**
    *   **Parallel-Plate Chambers:** **Strongly recommended** as the detector of choice for electron PDD measurements, especially in the build-up and high-gradient regions. Their advantages (minimal perturbation, well-defined EPOM at the front surface) lead to more accurate PDD curves compared to cylindrical chambers.
    *   **Cylindrical Chambers:** Can still be used for relative dosimetry (e.g., profiles in low-gradient regions, output factors at $d_{max}$), but TG-70 reaffirms the need for the **EPOM correction** when measuring in a gradient (e.g., for PDDs). The effective measurement point should be shifted **upstream by $0.5 r_{cav}$** (cavity radius).
        *   **Practical Issue:** Applying this shift accurately during scanning can be complex and introduces potential errors, reinforcing the preference for parallel-plate chambers for PDDs.
    *   **Diodes:** Acknowledged as suitable for relative measurements due to small size. However, TG-70 emphasizes awareness and potential correction for:
        *   **Energy Dependence:** Response can change significantly with depth as electron energy decreases. This can distort PDD measurements, especially in the fall-off region.
        *   **Dose Rate Dependence:** May be relevant for some linacs or modes.
        *   **Recommendation:** Use diodes specifically designed for electron dosimetry (often shielded or compensated) and characterize their energy/depth dependence against ion chamber measurements.
    *   **Film (Radiochromic):** Increasingly preferred over radiographic film due to near water equivalence and less energy dependence. Excellent for high-resolution 2D measurements (profiles, cutout shapes, field matching).
    *   **Diamond Detectors:** Offer small size and near water equivalence but can exhibit dose rate dependence.
*   **Phantoms:** Water remains the standard. Solid phantom use requires careful validation of scaling factors (depth, stopping power) against water measurements, as per TG-25 principles.
*   **Measurement Techniques:**
    *   **PDDs:** Use a parallel-plate chamber scanned vertically. Ensure the chamber window is parallel to the water surface. Start scan from the surface or slightly above.
    *   **Profiles:** Use a suitable small detector (diode, diamond, small ion chamber, film) scanned horizontally at relevant depths (e.g., $d_{max}$, $R_{90}$, $R_{50}$). Ensure detector orientation is consistent (e.g., cylindrical chamber axis perpendicular to scan direction).
    *   **Output Factors:** Measure dose per MU relative to the reference condition (e.g., 10x10 cm² at $d_{ref}$ or $d_{max}$). Measurements should ideally be made at the $d_{max}$ specific to each field size/applicator/cutout being measured. Use a reliable, calibrated chamber (parallel-plate often preferred due to stable EPOM).

**Practical Guidance:** Invest in a good quality parallel-plate chamber for electron PDDs. Carefully characterize diodes if used for relative dosimetry. Use radiochromic film for detailed 2D verification.

## 4. Energy Specification Parameters: Consistency with TG-51

TG-70 reinforces the energy and range parameters defined in TG-25 but emphasizes their role within the TG-51 framework:

*   **$R_{50}$:** Confirmed as the **key beam quality specifier (Q)** for selecting $k_Q$ (and $P_{gr}^Q$ if applicable) in the TG-51 protocol.
*   **$E_0$ (Mean Energy at Surface):** Still related to $R_{50}$ ($E_0 \approx 2.33 R_{50}$), useful for general beam characterization.
*   **$E_{p,0}$ (Most Probable Energy):** Still related to $R_p$, but less critical for modern dosimetry protocols.
*   **Other Range Parameters ($R_{100}, R_{90}, R_{80}, R_p$):** Remain important for clinical energy selection and TPS beam modeling.

**Practical Implication:** Accurate measurement of $R_{50}$ from the PDD curve is the most critical step for linking relative dosimetry (PDD shape) to absolute dosimetry (TG-51 calibration).

## 5. Data for Treatment Planning Systems (TPS)

TG-70 implicitly recognizes the increasing sophistication of TPS algorithms (including early Monte Carlo and Grid-Based Boltzmann Solvers - GBBS) and the corresponding need for high-quality commissioning data.

*   **Accuracy Requirement:** The accuracy of TPS calculations is fundamentally limited by the accuracy of the input beam data.
*   **Comprehensive Data:** Reinforces the need for PDDs, profiles, output factors (including cutouts), and SSD dependence measured across the full range of clinical use.
*   **Detector Choice Matters:** Using the recommended detectors (e.g., parallel-plate for PDDs) ensures the input data accurately reflects the true dose distribution, leading to better beam model fitting and more reliable TPS calculations.

**Practical Link to MPPG 5.b:** TG-70 provides the guidance for *acquiring* the high-quality measured data that is then used as the benchmark for *commissioning* the TPS algorithm according to the tests and tolerances specified in MPPG 5.b.

## 6. Key Updates and Emphasis Compared to TG-25

*   **Reference Dosimetry Standard:** Formal adoption of TG-51.
*   **Detector Hierarchy:** Stronger recommendation for parallel-plate chambers for PDDs and reference dosimetry.
*   **EPOM:** Clear reaffirmation of the $0.5 r_{cav}$ upstream shift for cylindrical chambers in gradients.
*   **Beam Quality Specifier:** Solidification of $R_{50}$ as the key parameter for $k_Q$ selection.
*   **Modernization:** Provides context relevant to improved detector technology and the data needs of advanced TPS algorithms.

## Conclusion: The Modern Standard for Electron Measurements

TG-70 is an indispensable guide for medical physicists performing clinical electron beam dosimetry. By integrating the TG-51 protocol and refining recommendations for relative dosimetry measurements, it provides the current best practices necessary for:

*   Accurate absolute dose calibration.
*   Acquiring high-quality beam data for TPS commissioning.
*   Performing reliable routine QA measurements.

Adherence to TG-70 recommendations ensures consistency with national standards and contributes directly to the accuracy and safety of electron beam radiation therapy. It should be used in conjunction with TG-51 for absolute calibration and provides the measurement foundation for TPS commissioning guided by MPPG 5.b.

