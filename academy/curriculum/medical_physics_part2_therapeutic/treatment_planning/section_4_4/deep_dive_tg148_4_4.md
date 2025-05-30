# Section 4.4: Deep Dive - AAPM TG-148: QA for Helical Tomotherapy

**Reference:** Langen, K. M., Papanikolaou, N., Balog, J., Crilly, R., Followill, D., Goddu, S. M., ... & Shi, C. (2010). QA for helical tomotherapy: Report of the AAPM Task Group 148. *Medical Physics*, *37*(9), 4817-4853. https://doi.org/10.1118/1.3462971

## 1. Introduction: Need for Specific Tomotherapy QA

Helical Tomotherapy (HT) represents a unique integration of treatment planning, MVCT imaging, and rotational IMRT delivery using a binary multi-leaf collimator (MLC). While general QA principles from AAPM TG-40 and TG-142 apply, the specific hardware design and workflow of HT necessitate tailored QA procedures and recommendations.

TG-148 was commissioned to:
- Discuss QA techniques, frequencies, and tolerances specific to HT.
- Discuss dosimetric verification techniques applicable to HT.

The report aims to provide clinical medical physicists with the necessary insights to establish a comprehensive, independent QA program for HT units, building upon but adapting recommendations from previous task groups.

## 2. System Overview and Unique Aspects

- **Ring Gantry:** Linac rotates continuously around the patient.
- **Translating Couch:** Patient moves longitudinally through the gantry bore during treatment.
- **Binary MLC (bMLC):** Modulates beam intensity by rapidly opening/closing leaves during rotation. Leaf positions are either fully open or fully closed.
- **Fan Beam:** The treatment beam is collimated into a fan shape.
- **Integrated MVCT:** Uses the same treatment source and a detector array for onboard volumetric imaging before treatment.
- **Time-Based Delivery:** Plans are based on leaf open times rather than Monitor Units (MUs).

These unique features mean some traditional QA tests (e.g., light field/radiation field congruence) are not applicable, while others require modification or new tests are needed (e.g., synchrony between gantry rotation, couch translation, and MLC modulation).

## 3. Acceptance Testing and Commissioning Aspects

While detailed acceptance testing procedures (ATP) are vendor-driven, TG-148 emphasizes the physicist's role in commissioning:
- **Independent Verification:** Physicists must independently verify key parameters and performance aspects beyond the vendor ATP.
- **Beam Data:** Although HT uses a standard beam model, physicists must verify its accuracy through comprehensive measurements (profiles, output factors, PDDs - though PDDs are less critical due to rotational delivery).
- **MLC Performance:** Verifying leaf latency, transmission, and positional accuracy is crucial.
- **MVCT Commissioning:** Includes image quality assessment (spatial resolution, contrast, uniformity, noise, HU constancy) and geometric accuracy verification.
- **End-to-End Testing:** Essential to verify the entire workflow from planning to delivery.

## 4. Periodic QA Recommendations

TG-148 provides detailed recommendations for daily, monthly, quarterly, and annual QA tests, adapting TG-142 where applicable and adding HT-specific tests. Key areas include:

**4.1. Mechanical Alignments:**
- **Lasers:** Daily check (+/- 1 mm recommended, stricter than TG-142's +/- 2 mm).
- **Couch:** Checks for longitudinal travel accuracy, vertical/lateral stability, indexing.
- **Gantry:** Rotational accuracy, wobble.
- **Imaging/Treatment Plane Coincidence:** Critical for accurate dose delivery. Checked using MVCT scans of phantoms with markers.

**4.2. Beam Parameters & Dosimetry:**
- **Output Constancy:** Daily check (+/- 3%). Typically measured using vendor-provided phantom and procedure, but independent verification recommended.
- **Beam Quality/Energy:** Annual check (e.g., PDD measurement).
- **Profile Constancy:** Monthly/Annually.
- **Transmission Factors:** Checked annually (MLC, jaws).
- **Output Calibration (TG-51):** Annual calibration following TG-51 protocol, but adapted for the HT geometry (rotational delivery, specific phantom). TG-148 provides a detailed worksheet (Appendix A) for HT-specific TG-51 calibration, emphasizing measurements at 10 cm depth with rotation.

**4.3. Synchrony Tests:**
- **Gantry Speed/Angle vs. Time:** Checked monthly/annually.
- **Couch Speed vs. Time:** Checked monthly/annually.
- **MLC Timing/Latency:** Checked monthly/annually. Crucial for accurate modulation.
- **Jaw Timing/Position:** Checked monthly/annually.
- **Rotational Beam Profile/Position:** Checked monthly/annually to ensure beam stability during rotation.

**4.4. MVCT Imaging QA:**
- **Geometric Accuracy:** Daily check using phantom (e.g., "Cheese" phantom) to verify spatial integrity and alignment (+/- 1 mm).
- **Image Quality:** Monthly/Annually using phantoms (e.g., Catphan, Cheese) to assess:
    - HU Constancy (+/- 20 HU)
    - Spatial Resolution
    - Low Contrast Resolution
    - Uniformity & Noise
- **Imaging Dose:** Assessed annually.

**4.5. Treatment Planning System (TPS) QA:**
- Follows general principles of TG-53.
- **Data Integrity:** Checks on beam model, CT-density curve.
- **Calculation Accuracy:** Monthly/Annual checks using benchmark plans and phantom measurements.
- **Geometric Accuracy:** Validating coordinate systems, isocenter representation.

**4.6. Patient-Specific QA (IMRT QA):**
- **Essential:** Must be performed for every patient plan before treatment.
- **Methods:** Typically involves delivering the plan to a phantom (cylindrical or flat) and measuring the dose distribution using film, ion chamber arrays (e.g., ArcCHECK, Delta4), or other detectors.
- **Analysis:** Comparison between measured and calculated dose distributions using methods like gamma analysis (e.g., 3%/3mm criteria).
- **Log File Analysis:** Analyzing machine delivery log files can provide additional verification of delivery accuracy (MLC errors, gantry/couch deviations).

## 5. Summary Tables

The report provides comprehensive tables summarizing recommended QA tests, frequencies (daily, monthly, quarterly, annual), and suggested tolerances for:
- Dosimetry
- Mechanical Checks
- Imaging QA
- Safety Checks

These tables serve as a practical guide for implementing an HT QA program.

## 6. Appendices

Include valuable supplementary information:
- Detailed TG-51 calibration worksheet for HT.
- Discussion on control sinograms and XML files.
- Radiation safety considerations.
- Example daily test procedures.
- Notes on patient archives and planning tips.

## Conclusion

AAPM TG-148 provides essential, specific guidance for developing a comprehensive QA program for Helical Tomotherapy units. It adapts existing QA frameworks (TG-40, TG-142, TG-51, TG-53) to the unique characteristics of HT, emphasizing mechanical accuracy, beam parameter stability, imaging performance, treatment planning verification, and crucially, the synchrony between gantry rotation, couch translation, and MLC modulation. Regular and thorough execution of the recommended QA tests is vital for ensuring safe and accurate patient treatments with this complex modality.

