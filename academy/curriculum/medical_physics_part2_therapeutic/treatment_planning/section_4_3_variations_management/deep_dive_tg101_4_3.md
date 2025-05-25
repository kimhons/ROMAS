# Section 4.3: Deep Dive - AAPM TG-101: Stereotactic Body Radiation Therapy

## Introduction

AAPM Report TG-101, published in 2010, provides comprehensive guidance for medical physicists, clinicians, and therapists on the implementation and practice of Stereotactic Body Radiation Therapy (SBRT). SBRT is characterized by the delivery of high doses per fraction in a small number of fractions (typically 1-5) to extracranial targets, requiring high precision and accuracy. This deep dive summarizes the key recommendations and considerations from TG-101, focusing on aspects relevant to managing inter- and intra-fraction variations.

## 1. Rationale and Characteristics of SBRT

- **High Biological Effective Dose (BED):** Large doses per fraction lead to a potent biological effect, potentially overcoming radioresistance and achieving high rates of local control, similar to Stereotactic Radiosurgery (SRS) for intracranial targets.
- **High Conformality & Steep Dose Gradients:** To minimize normal tissue toxicity despite the high doses, SBRT requires highly conformal dose distributions with rapid dose fall-off outside the target volume.
- **Key Distinctions from Conventional RT (Table I in TG-101):**
    - Higher dose/fraction (6-30 Gy vs 1.8-3 Gy).
    - Fewer fractions (1-5 vs 10-30+).
    - Tighter margins (millimeters vs centimeters).
    - Emphasis on direct geometric verification (IGRT) vs indirect monitoring.
    - Highest need for respiratory motion management.
    - Requires specialized training and technology.

## 2. Simulation Imaging and Treatment Planning

### a) Simulation Imaging
   - **Multimodality Imaging:** Often utilizes CT, PET-CT, and MRI for accurate target delineation.
   - **Patient-Specific Motion Assessment:** Crucial for mobile tumors (lung, liver, pancreas, kidney).
     - **4DCT:** Recommended as the primary method to assess tumor motion due to respiration. Allows visualization of the tumor trajectory and creation of motion-encompassing volumes (ITV) or selection of phases for gating/tracking.
     - **Other methods:** Fluoroscopy, slow CT, breath-hold CTs can also provide motion information.
   - **Immobilization:** Robust immobilization is critical to minimize both inter- and intra-fraction patient movement. Devices range from vacuum bags (BodyFIX) to stereotactic body frames, sometimes combined with abdominal compression.
   - **Imaging Artifacts:** Motion during CT can cause artifacts. 4DCT helps mitigate some artifacts but requires careful QA.

### b) Treatment Planning
   - **Target Definition:**
     - GTV: Gross Tumor Volume.
     - CTV: Clinical Target Volume (often GTV = CTV for well-defined SBRT targets).
     - ITV: Internal Target Volume, encompassing GTV/CTV motion across all respiratory phases (derived from 4DCT).
     - PTV: Planning Target Volume (ITV + Setup Margin, or GTV/CTV + Motion Margin + Setup Margin depending on motion management strategy).
     - **Margins:** PTV margins are typically much smaller (e.g., 5 mm) than conventional RT, reflecting the high precision required and the use of IGRT.
   - **Motion Management Integration:** The planning process must incorporate the chosen motion management strategy (e.g., planning on an average CT for ITV approach, planning on specific phases for gating).
   - **Dose Prescription & Reporting:**
     - Often prescribed to an isodose line covering the PTV (e.g., 80% isodose line).
     - Reporting should include dose to PTV, max dose, dose heterogeneity, conformity indices, and gradient indices.
   - **Dose Calculation:**
     - **Algorithm Choice:** Algorithms accurately modeling lateral electron transport (e.g., Monte Carlo, Collapsed Cone Convolution) are preferred, especially for lung SBRT due to tissue inhomogeneities.
     - **Grid Size:** Small calculation grid size (e.g., <= 2 mm) is recommended due to steep dose gradients.
   - **Beam Arrangement:** Often uses multiple non-coplanar beams or VMAT to achieve high conformality and rapid dose fall-off.
   - **Normal Tissue Constraints:** Critical due to high doses per fraction. TG-101 provides summary tables of suggested dose constraints based on available literature (recognizing these are evolving).

## 3. Patient Positioning, Immobilization, Localization, and Delivery

- **Immobilization:** Must be robust, reproducible, and compatible with imaging and treatment delivery. Should minimize patient movement and potentially restrict respiratory motion (e.g., abdominal compression).
- **Image-Guided Localization (IGRT):** Mandatory for SBRT.
    - **Frequency:** Required before *each* fraction, and often during treatment (intra-fraction verification).
    - **Modalities:** CBCT, orthogonal kV/MV imaging (with fiducials or bony anatomy), CT-on-rails, MRI-Linac.
    - **Registration:** Accurate registration (bony anatomy, soft tissue, fiducials) is critical. Fiducials often preferred for targets without clear bony surrogates.
    - **Correction Strategy:** 6D couch corrections (X, Y, Z, Pitch, Roll, Yaw) are often necessary.
- **Motion Management during Delivery:** Must be consistent with the simulation/planning strategy.
    - **Motion Encompassing (ITV):** Relies on IGRT to position the ITV correctly.
    - **Gating:** Requires accurate real-time monitoring and beam control based on surrogate signal.
    - **Tracking:** Requires real-time target localization and beam adjustment.
    - **Breath-Hold:** Requires reproducible breath-holds verified by monitoring.
- **Delivery Reporting:** Detailed records of setup corrections, motion management parameters, and any deviations are essential.

## 4. Special Dosimetry Considerations

- **Small Fields:** SBRT often uses small field sizes or segments.
    - **Detector Choice:** Dosimetry is challenging due to lack of lateral electronic equilibrium and detector volume averaging. Small volume detectors (micro-ion chambers, diodes, diamond detectors) or film are recommended for output factor and profile measurements.
    - **Algorithm Accuracy:** Treatment planning system algorithms must be validated for small field accuracy.
- **Heterogeneity:** Accurate dose calculation in heterogeneous regions (like lung) is critical. Type B algorithms (considering electron transport) are strongly recommended over Type A (simple heterogeneity corrections).

## 5. Clinical Implementation and QA

- **Establishing a Program:** Requires a multidisciplinary team (physician, physicist, dosimetrist, therapist), appropriate technology (4DCT, IGRT, robust immobilization, accurate planning system), and dedicated time/resources.
- **Commissioning & QA:** Rigorous commissioning and ongoing QA are paramount.
    - **End-to-End Testing:** Verifying the entire process from imaging to delivery using anthropomorphic phantoms is crucial. Tests should incorporate motion.
    - **Imaging QA:** Geometric accuracy, image quality, registration accuracy (TG-132), 4DCT phase sorting accuracy.
    - **Motion Management System QA:** Gating accuracy, latency, breath-hold monitoring accuracy, tracking accuracy (TG-76).
    - **Delivery System QA:** Mechanical accuracy (isocenter, couch, MLCs - TG-142), output consistency, small field dosimetry validation.
    - **Patient-Specific QA:** Plan verification (measurement vs. calculation), pre-treatment checks.
- **Patient Safety:** Emphasis on redundancy in verification, clear procedures, checklists, and robust error reduction processes.

## Conclusion

TG-101 establishes the high standards required for safe and effective SBRT delivery. Accurate management of inter- and intra-fraction motion through robust immobilization, 4D imaging, sophisticated planning, mandatory IGRT, and rigorous QA is central to the technique. The report underscores that SBRT is a complex process demanding specialized expertise, technology, and a strong commitment to quality and safety from the entire radiotherapy team. Its recommendations provide a framework for implementing and maintaining a high-quality SBRT program, ensuring precise delivery of ablative doses while minimizing toxicity.

