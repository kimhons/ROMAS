# Section 5.11: Methods of Quality Control and Quality Assurance (Therapeutic Context)

**Approximate Lecture Time:** 3-4 Hours

**Learning Objectives:**

Upon completion of this section, the student will be able to:

1.  **Define** Quality Control (QC) and Quality Assurance (QA) and **explain** their importance in radiation therapy.
2.  **Describe** the key recommendations and structure of AAPM Task Group reports relevant to therapeutic QA (e.g., TG-40, TG-142, TG-51, TG-43, TG-100).
3.  **Outline** the typical frequencies (daily, monthly, annual) and procedures for linear accelerator (linac) QA, covering:
    *   Dosimetry checks (output constancy, beam energy, flatness, symmetry).
    *   Mechanical checks (laser alignment, ODI, collimator/gantry/couch rotation accuracy, jaw position, MLC position).
    *   Safety checks (interlocks, emergency stops, audiovisual systems).
4.  **Explain** the principles and procedures for absolute dose calibration of linac photon and electron beams according to AAPM TG-51 protocol.
5.  **Describe** the QA procedures for treatment planning systems (TPS), including:
    *   Data commissioning (beam data acquisition and input).
    *   Algorithm verification (comparison with measured data for standard and complex geometries).
    *   Data transfer integrity checks (to/from R&V system).
    *   Ongoing checks (consistency, software updates).
6.  **Outline** the QA procedures specific to brachytherapy, including:
    *   Source calibration verification (LDR seeds, HDR source).
    *   HDR afterloader QA (timer accuracy/linearity, source positioning, interlocks, emergency retraction).
    *   Applicator verification and integrity checks.
    *   Treatment plan and calculation checks.
7.  **Describe** the QA procedures for simulation equipment (CT simulators, conventional simulators), focusing on spatial accuracy, laser alignment, and image quality.
8.  **Explain** the purpose and methods of patient-specific QA for Intensity Modulated Radiation Therapy (IMRT) and Volumetric Modulated Arc Therapy (VMAT) plans, including:
    *   Phantom-based measurements (film, ion chamber arrays, EPID).
    *   Analysis techniques (gamma analysis, dose difference, distance-to-agreement).
    *   Action levels and tolerance criteria.
9.  **Identify** common phantoms (water tank, solid water, anthropomorphic) and dosimetry equipment (ion chambers, diodes, film, OSLDs, EPIDs) used in therapeutic QA and **explain** their specific applications.
10. **Discuss** the importance of documentation, record keeping, action levels, and review processes within a comprehensive QA program.

**Key Points:**

*   **QA vs QC:** QA is the overall program to ensure quality; QC involves specific tests to verify equipment performance meets standards.
*   **Goal:** Ensure accurate and safe delivery of prescribed radiation dose to the correct patient volume.
*   **Key Reports:**
    *   **TG-40:** Comprehensive QA for linacs (historical, basis for TG-142).
    *   **TG-142:** Updated QA recommendations for linacs, incorporating IMRT, IGRT, R&V systems.
    *   **TG-51:** Absolute dose calibration protocol for photon and electron beams.
    *   **TG-43:** Brachytherapy source dosimetry formalism.
    *   **TG-53:** QA for TPS.
    *   **TG-66:** QA for CT simulators.
    *   **TG-100:** Risk-based QA methodology (FMEA - Failure Modes and Effects Analysis).
*   **Linac QA Frequencies:**
    *   **Daily:** Output constancy (photons/electrons), lasers, ODI, safety interlocks (door, audiovisual).
    *   **Monthly:** Output constancy (all energies), energy constancy, flatness/symmetry, light/radiation field coincidence, mechanical checks (gantry/coll angles, jaw positions), MLC checks.
    *   **Annual:** Full dosimetry calibration (TG-51), comprehensive mechanical checks, safety interlocks, imaging systems (MV/kV), MLC performance, TPS data verification.
*   **TG-51 Calibration:** Uses an ion chamber calibrated traceable to NIST in a water phantom under reference conditions (10x10 cm field, 10 cm depth for photons, d<sub>ref</sub> for electrons, 100 cm SSD).
    *   `Dose_w = M * N_D,w^Co60 * k_Q` (Photons)
    *   `Dose_w = M * P_gr * k_ecal * N_D,w^Co60` (Electrons)
*   **TPS QA:** Commissioning involves acquiring extensive beam data (PDDs, profiles, output factors) and verifying the TPS accurately models the measured data. Ongoing checks ensure consistency.
*   **Brachytherapy QA:** Source strength verification (well chamber), afterloader function (timer, position), applicator integrity, plan checks.
*   **Simulator QA:** Laser alignment, spatial accuracy (CT numbers, distances), image quality.
*   **IMRT/VMAT QA:** Patient-specific measurements comparing planned vs delivered dose distribution using phantoms and detectors. Gamma analysis (e.g., 3%/3mm criteria) commonly used.
*   **Documentation:** Meticulous records of all QA procedures, results, and corrective actions are essential for regulatory compliance and program review.

---

## 1. Introduction to QA/QC in Radiation Therapy

Quality Assurance (QA) encompasses all planned and systematic actions necessary to provide adequate confidence that a product or service will satisfy given requirements for quality. In radiation therapy, this means ensuring that patients consistently receive treatments as prescribed, safely and accurately.

Quality Control (QC) refers to the specific operational techniques and activities used to fulfill requirements for quality. These are the routine tests performed on equipment to verify it is functioning within established tolerance limits.

A comprehensive QA program integrates physics QC, clinical procedures, staff training, communication protocols, and continuous improvement processes.

**Importance:**
*   **Patient Safety:** Prevents errors that could lead to under-dosing the tumor or over-dosing normal tissues.
*   **Treatment Accuracy:** Ensures the delivered dose distribution matches the planned distribution.
*   **Regulatory Compliance:** Meets requirements set by licensing bodies (e.g., NRC, state) and accreditation organizations (e.g., ACR, ASTRO APEx).
*   **Equipment Performance:** Maintains optimal functioning of complex equipment.

## 2. Key AAPM Task Group Reports

The American Association of Physicists in Medicine (AAPM) provides crucial guidance through its Task Group (TG) reports.

*   **TG-40 (1994):** Established the framework for comprehensive linac QA, defining tests, frequencies, and tolerances. While superseded by TG-142 for many aspects, its principles remain fundamental.
*   **TG-142 (2009):** Updated linac QA recommendations, specifically addressing newer technologies like IMRT, VMAT, IGRT, and electronic portal imaging devices (EPIDs). It provides tables of recommended tests, frequencies, and tolerances for various systems (SRS/SBRT systems have tighter tolerances).
*   **TG-51 (1999) & Addendum (2014):** The standard protocol for calibrating high-energy photon and electron beams using ion chambers calibrated in terms of absorbed dose-to-water (N<sub>D,w</sub>) traceable to national standards.
*   **TG-43 (1995) & Updates:** Standard formalism for brachytherapy dose calculations and associated QA recommendations.
*   **TG-53 (1998):** Recommendations for QA of treatment planning systems.
*   **TG-66 (2003):** QA recommendations for CT simulators.
*   **TG-100 (2016):** Introduces a risk-based approach to QA, encouraging institutions to use tools like Failure Modes and Effects Analysis (FMEA) to identify potential errors in their specific processes and tailor their QA program accordingly, focusing resources on high-risk areas.

## 3. Linear Accelerator (Linac) QA (TG-142)

Linac QA involves a hierarchy of tests performed at different frequencies.

**3.1. Daily QA:** (Typically performed by radiation therapists before treatments)
*   **Dosimetry:** Output constancy (photons, electrons - often a subset of energies). Tolerance: ±3%.
*   **Mechanical:** Laser alignment (isocenter check). Tolerance: ±2 mm (non-IMRT), ±1.5 mm (IMRT), ±1 mm (SRS/SBRT).
*   **Mechanical:** Optical Distance Indicator (ODI) at isocenter. Tolerance: ±2 mm.
*   **Safety:** Door interlock, audiovisual systems functional.
*   **Imaging (if applicable):** Collision interlocks, positioning/repositioning checks.

**3.2. Monthly QA:** (Typically performed by medical physicists)
*   **Dosimetry:** Output constancy (all photon/electron energies). Tolerance: ±2%.
*   **Dosimetry:** Photon and electron energy constancy (e.g., PDD or TMR check). Tolerance: ±2%.
*   **Dosimetry:** Beam flatness and symmetry (photons/electrons). Tolerance: ±1% (symmetry), specific flatness criteria.
*   **Mechanical:** Light vs. radiation field coincidence. Tolerance: ±2 mm or 1% per side.
*   **Mechanical:** Gantry/collimator angle indicators. Tolerance: ±1°.
*   **Mechanical:** Jaw position indicators (symmetric, asymmetric). Tolerance: ±2 mm (non-IMRT), ±1 mm (IMRT/SRS).
*   **Mechanical:** Cross-hair centering. Tolerance: ±2 mm diameter (non-SRS), ±1 mm diameter (SRS).
*   **Mechanical:** Couch position indicators. Tolerance: ±2 mm / ±1°.
*   **Mechanical:** MLC position accuracy (e.g., picket fence test). Tolerance: ±1 mm (IMRT/SRS).
*   **Safety:** Emergency stops, interlocks.
*   **Imaging (if applicable):** kV/MV imager coincidence with isocenter, imaging dose checks.

**3.3. Annual QA:** (Typically performed by medical physicists)
*   **Dosimetry:** Full absolute calibration following TG-51 protocol.
*   **Dosimetry:** Output constancy (all energies, modes). Tolerance: ±2%.
*   **Dosimetry:** PDD/TMR measurements, profile checks (flatness, symmetry, penumbra). Verification against TPS data.
*   **Dosimetry:** Collimator scatter factor (Sc), Phantom scatter factor (Sp) verification.
*   **Dosimetry:** Monitor chamber linearity, dose rate constancy.
*   **Mechanical:** Comprehensive checks of gantry, collimator, couch rotation isocentricity. Tolerance: ≤ 2 mm diameter (non-SRS), ≤ 1 mm diameter (SRS).
*   **Mechanical:** Jaw position accuracy, MLC position and transmission verification.
*   **Mechanical:** Couch movement accuracy and limits.
*   **Safety:** Full check of all safety interlocks, follow-up on any issues.
*   **Imaging:** Comprehensive imaging system QA (geometric accuracy, spatial resolution, contrast, uniformity, imaging dose).
*   **TPS Data:** Verification of key beam data against measurements.

**Tolerances:** Note that tolerances are often tighter for SRS/SBRT procedures as recommended by TG-142.

## 4. Absolute Dose Calibration (TG-51)

Accurate beam calibration is the foundation of radiation therapy QA. TG-51 provides the standard protocol in North America.

**Key Concepts:**
*   **Traceability:** Uses an ion chamber with a calibration factor (N<sub>D,w</sub><sup>Co-60</sup>) traceable to a national standards laboratory (e.g., NIST in the US).
*   **Medium:** Measurements performed in a water phantom.
*   **Reference Conditions:** Specific setup conditions (field size, depth, SSD/SAD) defined for photons and electrons.
    *   Photons: 10x10 cm field, 10 cm depth, 100 cm SSD or SAD.
    *   Electrons: 10x10 cm field (or larger per protocol), reference depth d<sub>ref</sub> = 0.6 * R<sub>50</sub> - 0.1 cm, typically 100 cm SSD.
*   **Ion Chamber Corrections:** Raw chamber reading (M) must be corrected for temperature/pressure (P<sub>TP</sub>), electrometer calibration (P<sub>elec</sub>), ion recombination (P<sub>ion</sub>), and polarity effects (P<sub>pol</sub>).
    *   `M_corrected = M_raw * P_TP * P_elec * P_ion * P_pol`
*   **Beam Quality Conversion Factor (k<sub>Q</sub> for Photons):** Converts the Co-60 calibration factor to one specific for the user's beam quality. Determined from %dd(10)<sub>x</sub> (PDD at 10 cm depth for photons, excluding electron contamination).
*   **Electron Quality Factors (k'<sub>R50</sub>, P<sub>gr</sub>, k<sub>ecal</sub>):** Used for electron beams. k<sub>ecal</sub> links the chamber's photon calibration to an electron beam factor. P<sub>gr</sub> is the gradient correction at d<sub>ref</sub>. Beam quality specified by R<sub>50</sub> (depth of 50% dose).

**Formulas:**
*   **Photon Dose:** `Dose_w (Gy/MU) = (M_corrected / MU) * N_D,w^Co60 * k_Q`
*   **Electron Dose:** `Dose_w (Gy/MU) = (M_corrected / MU) * P_gr * k_ecal * N_D,w^Co60`

Calibration is typically performed annually and after major repairs.

## 5. Treatment Planning System (TPS) QA (TG-53)

Ensuring the TPS accurately calculates dose distributions is critical.

*   **Commissioning:**
    *   **Data Input:** Verifying correct input of measured beam data (PDDs, profiles, output factors, etc.).
    *   **Algorithm Verification:** Comparing TPS calculations against measured data for various standard fields (different sizes, depths, energies, wedges) and complex scenarios (small fields, asymmetric fields, inhomogeneous phantoms, MLC fields).
    *   **Hardware/Software:** Verifying system configuration, network connections, data integrity.
*   **Ongoing QA:**
    *   **Consistency Checks:** Regularly recalculating standard plans or test cases to ensure results haven't changed.
    *   **Data Transfer:** Verifying accurate transfer of plan data to the R&V system and linac.
    *   **Software Updates:** Re-verifying key calculations and performing regression testing after TPS software updates.
    *   **Output Checks:** Ensuring printed plans and DVHs match on-screen displays.

## 6. Brachytherapy QA

QA procedures vary for LDR and HDR.

*   **Source Calibration:**
    *   **LDR Seeds:** Sample seeds from each batch measured using a well-type ion chamber with calibration traceable to NIST standards. Verify source strength against vendor specification (typically ±3-5% tolerance).
    *   **HDR Source:** Source strength (Air Kerma Strength) measured upon receipt using a well chamber. Must be within ±5% of vendor calibration. Decay correction verified.
*   **HDR Afterloader QA (TG-56, TG-59):**
    *   **Daily:** Battery check, console checks, interlocks (door, head, applicator), emergency stops, radiation monitor.
    *   **Monthly:** Timer accuracy and linearity, source positioning accuracy (radiography or autoradiography), decay calculation check.
    *   **Quarterly/Annual:** Full source calibration verification, positional accuracy over full travel range, interlock checks, communication systems.
*   **Applicator QA:** Check for damage, integrity, correct labeling, source path obstructions. Verify dimensions against TPS models.
*   **Treatment Plan QA:** Independent check of plan parameters (source positions, dwell times), dose calculation verification (manual check or second system), transfer to afterloader console verification.

## 7. Simulator QA

Ensuring accurate patient positioning and imaging for planning.

*   **CT Simulator QA (TG-66):**
    *   **Daily:** Laser alignment.
    *   **Monthly:** Laser alignment accuracy, image quality (noise, uniformity, CT number accuracy using phantom), spatial integrity (distances on image vs phantom), couch movement accuracy.
    *   **Annual:** Comprehensive check of all mechanical alignments, imaging performance parameters (spatial resolution, contrast resolution, HU accuracy), radiation dose indices (CTDI).
*   **Conventional Simulator QA:** Focuses on mechanical alignments (lasers, ODI, field defining wires, gantry/collimator/couch angles), image quality (fluoroscopy), and safety features.

## 8. Patient-Specific IMRT/VMAT QA

Due to the complexity of IMRT/VMAT delivery, QA is performed for each patient's plan before treatment.

*   **Purpose:** Verify that the complex fluence patterns planned can be accurately delivered by the linac and MLC system, resulting in the intended dose distribution.
*   **Methodology:**
    1.  Deliver the patient's plan to a phantom (flat or cylindrical) equipped with a radiation detector.
    2.  Measure the resulting 2D or 3D dose distribution.
    3.  Compare 
(Content truncated due to size limit. Use line ranges to read in chunks)