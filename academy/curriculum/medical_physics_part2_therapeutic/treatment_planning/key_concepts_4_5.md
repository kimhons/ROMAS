# Section 4.5: Key Concepts - Special Procedures

**Section Goal:** To provide learners with a foundational understanding of the physics principles, clinical applications, quality assurance requirements, and safety considerations associated with various special radiation therapy procedures, including Stereotactic Radiosurgery (SRS), Stereotactic Body Radiation Therapy (SBRT), Total Body Irradiation (TBI), Total Skin Electron Irradiation (TSEI), Intraoperative Radiation Therapy (IORT), High-Dose-Rate (HDR) Brachytherapy, and Low-Dose-Rate (LDR) Brachytherapy.

This section builds upon previous modules and integrates concepts specific to these advanced and often complex treatment techniques.

## 1. Stereotactic Radiosurgery (SRS) and Stereotactic Body Radiation Therapy (SBRT)

*   **Definition & Distinction:**
    *   **SRS:** Typically refers to single-fraction, high-precision irradiation of intracranial targets.
    *   **SBRT (or SABR - Stereotactic Ablative Body Radiotherapy):** Refers to hypofractionated (usually 1-5 fractions), high-precision irradiation of extracranial targets.
    *   Common characteristic: High dose per fraction, steep dose gradients outside the target, requiring high geometric accuracy.
*   **Physics Principles:**
    *   **Localization:** High-resolution imaging (CT, MRI, PET) for target definition, often with image fusion (Ref: TG-101, TG-132 from Sec 4.3).
    *   **Immobilization:** Rigid immobilization (e.g., head frames for SRS) or advanced techniques (e.g., body frames, vacuum bags, abdominal compression for SBRT) to minimize intra-fraction motion (Ref: TG-101).
    *   **Motion Management:** Techniques to account for respiratory motion in SBRT (e.g., gating, tracking, abdominal compression, ITV concepts) (Ref: TG-76 from Sec 4.3, TG-101).
    *   **Treatment Planning:** Highly conformal dose distributions, often using non-coplanar beams/arcs, small field sizes, advanced algorithms (e.g., Monte Carlo, Collapsed Cone) capable of handling tissue heterogeneities accurately (Ref: TG-101).
    *   **Delivery Systems:** Specialized Linacs (e.g., with micro-MLCs, high dose rates, robotic arms), Gamma Knife, CyberKnife.
*   **Dosimetry & QA:**
    *   **Small Field Dosimetry Challenges:** Lack of lateral electronic equilibrium, detector volume averaging, specific detector recommendations (e.g., micro-ionization chambers, diodes, film, scintillators) (Ref: TG-101, potentially related concepts in TG-51 Addendum/TG-61 for specific energies if applicable).
    *   **End-to-End Testing:** Verifying the entire process chain from imaging to delivery using anthropomorphic phantoms (Ref: TG-101, TG-142 - *Reference Not Checked*).
    *   **Linac QA for SRS/SBRT (TG-142 - *Reference Not Checked*):** Stricter tolerances for mechanical parameters (e.g., isocenter accuracy, MLC positioning), output constancy, beam profiles compared to conventional RT.
    *   **IMRT/VMAT QA (TG-218 - *Covered in 4.4*):** Verification methodologies are crucial given the complex delivery.
*   **Clinical Applications:** Brain metastases, primary brain tumors, AVMs (SRS); Early-stage lung cancer, liver tumors, pancreatic cancer, spinal tumors, prostate cancer (SBRT).
*   **Safety & Risk (TG-100 - *Covered in 4.4*):** High dose per fraction increases risk of severe normal tissue toxicity if accuracy is compromised. Process mapping and FMEA are critical.
*   **Reporting (ICRU 91 - *Reference Not Checked*):** Standardized reporting nomenclature for stereotactic treatments.

## 2. Brachytherapy (HDR/LDR)

*   **Definition:** Placement of radioactive sources directly into or near the target volume.
    *   **HDR:** High activity sources used for short durations (minutes), typically delivered in multiple fractions.
    *   **LDR:** Lower activity sources implanted permanently or temporarily for longer durations (days).
*   **Physics Principles:**
    *   **Source Characteristics:** Isotopes (e.g., Ir-192 for HDR; I-125, Pd-103 for LDR prostate), activity, half-life, energy spectrum.
    *   **Dosimetry Formalism (TG-43 Update - *Found*):** Consensus methodology for calculating dose in medium around brachytherapy sources, accounting for geometry, scatter, attenuation. Key parameters: Air kerma strength (SK), dose rate constant (Λ), geometry function (G(r,θ)), radial dose function (g(r)), anisotropy function (F(r,θ)).
    *   **Model-Based Dose Calculation (TG-186 - *Covered in Brachy section*):** Advanced algorithms (e.g., collapsed cone, Monte Carlo) that explicitly account for patient anatomy, applicator attenuation/scatter, and tissue heterogeneities, moving beyond TG-43 limitations.
    *   **Treatment Planning:** Source dwell positions and times (HDR) or seed placement (LDR) optimized to cover the target while sparing organs at risk (OARs).
    *   **Applicators/Catheters:** Devices used to guide and position sources accurately (e.g., tandem & ovoids for GYN, interstitial needles, SAVI/MammoSite for breast).
*   **QA & Safety:**
    *   **Source Calibration:** Verifying source strength against vendor calibration (traceable to standards like NIST).
    *   **Treatment Planning System QA (TG-53, TG-186):** Verifying algorithm accuracy, source data, transfer integrity.
    *   **Applicator/Catheter QA:** Ensuring integrity, correct indexing/channel identification, positional accuracy (e.g., using imaging).
    *   **Treatment Delivery QA (HDR):** Timer accuracy, transit dose, source positional accuracy, emergency procedures.
    *   **Post-Implant Dosimetry (LDR):** Verifying seed placement and dose coverage using post-implant imaging (CT/MRI).
*   **Clinical Applications:** Cervical, endometrial, prostate, breast, skin, head & neck cancers.

## 3. Total Body Irradiation (TBI)

*   **Definition:** Irradiation of the entire body, typically as part of a conditioning regimen for hematopoietic stem cell transplantation (HSCT).
*   **Physics Principles:**
    *   **Goal:** Deliver a relatively uniform dose (e.g., ±10%) throughout the body while potentially shielding critical organs (e.g., lungs, kidneys).
    *   **Delivery Techniques:** Large fields (extended SSD), opposing beams (AP/PA or bilateral), sweeping beams, patient translation/rotation.
    *   **Dosimetry Challenges:** Dose uniformity across varying body thicknesses, dose build-up/skin dose, output factors for large fields, beam spoilers to increase surface dose.
    *   **In Vivo Dosimetry:** Use of detectors (e.g., diodes, TLDs, OSLDs) placed on the patient's skin or within cavities to verify delivered dose at specific points.
*   **QA & Commissioning (TG-29 - *Reference Not Checked*):** Characterizing beam for large fields, measuring output factors, verifying dose uniformity in phantoms, establishing procedures for patient setup and in vivo dosimetry.
*   **Clinical Applications:** Leukemia, lymphoma, multiple myeloma (pre-HSCT).

## 4. Total Skin Electron Irradiation (TSEI)

*   **Definition:** Irradiation of the entire skin surface using electrons, primarily for cutaneous T-cell lymphoma (CTCL), while minimizing dose to underlying tissues.
*   **Physics Principles:**
    *   **Goal:** Deliver a uniform dose to a specific depth in the skin (e.g., dmax or 80% isodose line) across the entire body surface.
    *   **Delivery Techniques:** Multiple large electron fields angled to intersect at the patient position (e.g., Stanford technique with 6 dual fields), patient standing on a rotating platform, use of spoilers/degraders to modify beam energy and improve uniformity.
    *   **Dosimetry Challenges:** Achieving dose uniformity over complex curved surfaces, field matching/junctions, electron energy selection for appropriate depth coverage, significant variations in output and beam flatness for large, angled fields.
    *   **In Vivo Dosimetry:** Essential for verifying dose uniformity and coverage, often using TLDs or OSLDs placed at multiple body sites.
*   **QA & Commissioning (TG-30 - *Reference Not Checked*):** Characterizing electron beams for TSEI conditions (large fields, extended distances, angles), developing patient setup procedures, commissioning in vivo dosimetry system.
*   **Clinical Applications:** Mycosis fungoides (CTCL).

## 5. Intraoperative Radiation Therapy (IORT)

*   **Definition:** Delivery of a single, large dose of radiation directly to the tumor bed or residual microscopic disease during surgery, after tumor resection.
*   **Physics Principles:**
    *   **Goal:** Deliver a high dose to the target while surgically retracting or shielding nearby sensitive normal tissues.
    *   **Delivery Modalities:** Dedicated mobile electron Linacs, low-energy X-ray systems (e.g., 50 kVp), HDR brachytherapy applicators.
    *   **Dosimetry:** Calibration and output measurement specific to IORT conditions (e.g., specialized applicators, short treatment times, non-standard geometries). Kilovoltage dosimetry principles (TG-61 - *Reference Not Checked*) are relevant for X-ray systems.
    *   **Applicators:** Various shapes and sizes placed directly into the surgical cavity to define the treatment volume.
*   **QA & Safety (TG-72 - *Reference Not Checked*):** QA specific to IORT devices (output constancy, beam energy, applicator factors, safety interlocks), radiation safety procedures in the operating room, coordination between surgical and radiation oncology teams.
*   **Clinical Applications:** Early-stage breast cancer, pancreatic cancer, colorectal cancer, sarcomas, head & neck cancers.

## 6. Kilovoltage Dosimetry

*   **Relevance:** Applicable to IORT using low-energy X-rays and potentially relevant to some brachytherapy source calibrations or superficial treatments.
*   **Principles (TG-61 - *Reference Not Checked*):** Dosimetry protocols for low- and medium-energy X-ray beams (typically < 300 kVp). Differs significantly from megavoltage dosimetry (TG-51) due to lack of transient electronic equilibrium and strong dependence of dose on medium composition.
*   **Formalisms:** Often based on air-kerma measurements in air with backscatter factors and tissue-phantom ratios or percentage depth dose data specific to the beam quality (HVL).
*   **Detectors:** Typically parallel-plate ionization chambers calibrated for air kerma.
*   **TG-51 Addendum (*Found*):** While primarily for MV beams, the addendum might contain relevant updates or context, particularly regarding reference conditions or specific detector types that could overlap.

*(Note: This document summarizes key concepts based on the section title and available/related references. Deep dives for specific TG reports will provide more detail. References marked "Not Checked" require verification of availability and content.)*

