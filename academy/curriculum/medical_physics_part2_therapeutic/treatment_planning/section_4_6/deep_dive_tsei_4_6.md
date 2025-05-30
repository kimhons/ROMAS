# Section 4.6: Deep Dive - Total Skin Electron Irradiation (TSEI) Physics and Dosimetry (Based on OMP & General Principles)

This document provides an in-depth exploration of the physical aspects and dosimetry procedures for Total Skin Electron Irradiation (TSEI), primarily drawing from information presented on the Oncology Medical Physics (OMP) webpage and supplemented by general electron beam physics principles (e.g., AAPM TG-25 concepts where applicable). Note: The primary reference, AAPM TG-30, was not available for this review. The focus is on achieving graduate-level detail, practical implementation insights, and integrated examples for the commonly used Stanford technique.

## 1. Introduction and Clinical Context (Brief Recap)

*   **Purpose:** TSEI aims to deliver a uniform electron dose to the entire skin surface (epidermis and dermis) while minimizing dose to underlying tissues. Its primary indication is Mycosis Fungoides (MF), a type of Cutaneous T-cell Lymphoma (CTCL).
*   **Challenge:** Achieving dose uniformity (e.g., ±8-10%) over a complex 3D surface using electrons, while ensuring appropriate penetration depth (e.g., R80 ≥ 4mm) and minimizing X-ray contamination (<4% or <0.7-1.6 Gy total body dose), requires specialized techniques and meticulous dosimetry.

## 2. The Stanford Technique: Physics Principles

This is the most widely adopted method for TSEI.

*   **Extended SSD (3-8 meters):** Necessary to create a very large electron field (e.g., 200 cm high x 80 cm wide) capable of encompassing the entire patient.
    *   *Inverse Square Law:* Applies, but the primary reason for extended SSD is field size, not dose rate reduction (unlike TBI).
    *   *Energy Loss in Air:* Electrons lose significant energy traversing large air gaps (~1 MeV per 4 meters). The initial energy selected at the linac must be higher than the desired energy at the patient surface.
        *   *Practical Example:* If 4 MeV is desired at the patient surface at 6 meters SSD, the linac might need to be set to 5.5 MeV (6m * (1 MeV/4m) = 1.5 MeV loss).
*   **Dual Fields (Angled Beams):** Two large electron fields are used simultaneously, typically angled ±20° relative to the horizontal plane (one aimed above the head, one below the feet).
    *   *Coverage:* The overlapping fields cover the patient's height.
    *   *X-ray Contamination Reduction:* Bremsstrahlung X-rays, produced mainly in the accelerator head and collimators, are forward-peaked. Angling the central axes away directs the most intense part of the X-ray contamination away from the patient, significantly reducing the dose contribution to deeper tissues.
*   **Six Patient Positions:** The patient stands in six distinct orientations relative to the dual-field beam (AP, PA, RAO, LPO, LAO, RPO).
    *   *Uniformity Averaging:* Electrons scatter readily and have complex interactions with curved surfaces. A single field would produce highly non-uniform dose. Irradiating from multiple directions averages out hot and cold spots caused by varying angles of incidence and self-shielding (e.g., arms shielding the trunk in lateral positions), leading to clinically acceptable uniformity over the entire skin surface.
*   **Scatterer (Spoiler):** A sheet of low-Z material (~1 cm acrylic) placed ~15-30 cm in front of the patient.
    *   *Mechanism:* Induces multiple Coulomb scattering of electrons just before they reach the patient, increasing their angular divergence.
    *   *Primary Effect (Uniformity):* Broadens the effective beam profile, improving dose coverage on tangential surfaces and curved areas, making the dose distribution more uniform laterally.
    *   *Secondary Effects:*
        *   Increases surface dose relative to dmax.
        *   Slightly reduces electron penetration (dmax, R80, Rp) due to energy loss in the scatterer and increased average obliquity.
        *   Makes the dose fall-off slightly less steep.
*   **Patient Platform:** Elevating the patient reduces dose contribution from electrons scattered off the floor.

## 3. Electron Beam Characteristics in TSEI Geometry

*   **Energy Spectrum:** The electron beam reaching the patient is significantly degraded compared to the beam at the accelerator window due to energy loss and scattering in air and the spoiler. The spectrum is broadened, and the average energy is lower.
*   **Depth Dose:** Must be measured under full TSEI conditions (extended SSD, with scatterer).
    *   *Parameters:* Surface dose (Ds), depth of max dose (dmax), therapeutic depth (e.g., R90, R80), practical range (Rp).
    *   *Requirements (EORTC/OMP):* R80 ≥ 4 mm; R50 between 5-15 mm; R20 < 20 mm. These ensure adequate dose to the dermis with rapid sparing of subcutaneous tissue.
    *   *Shape:* Compared to standard electron fields, TSEI depth dose curves typically show a higher surface dose relative to dmax (Ds/Dmax closer to 1.0) and a less steep dose fall-off due to the broad, scattered nature of the beam and oblique incidence.
*   **Beam Profiles (Uniformity):** Critical parameter. Measured at the treatment plane (patient position) in air or on a phantom surface.
    *   *Requirements (TG-30/OMP):* Typically ±8% vertically over ~160 cm and ±4% horizontally over ~80 cm for a single dual field.
The 6-field technique further improves the final uniformity on the patient.
    *   *Factors Influencing Uniformity:* Linac beam steering/flatness, scattering foil design, SSD, scatterer presence/position, collimator settings, room scatter.
*   **Output Stability:** Must be reliable at the extended SSD and specific TSEI settings.

## 4. Dosimetry Procedures and Calibration (Adapting TG-51/TG-25)

*   **Reference Dosimeter:** Calibrated parallel-plate ionization chamber is essential (per TG-25/TG-30). Cylindrical chambers are unsuitable due to perturbation effects in low-energy, broad electron fields.
*   **Phantoms:**
    *   *Flat Phantom:* Water or solid water, large enough for profile/PDD measurements under TSEI conditions.
    *   *Cylindrical Phantom:* ~30 cm diameter polystyrene or similar, used to simulate the patient trunk for measuring surface dose distribution from the 6-field technique and determining the B-factor.
*   **Absolute Calibration (Calibration Point Dose Rate):**
    *   *Location:* At dmax on the central axis (or midpoint) in the flat phantom at the treatment SSD, with the scatterer in place, for a single dual-field irradiation.
    *   *Procedure (TG-51 Adaptation):*
        1.  Obtain N_D,w^Co60 for the parallel-plate chamber.
        2.  Measure ionization in a Co-60 or high-energy electron beam to determine k_ecal (chamber calibration factor relative to reference chamber).
        3.  Determine k'_R50 for the TSEI beam quality (effective R50 measured under TSEI conditions).
        4.  Determine P_gr for the parallel-plate chamber in the TSEI beam.
        5.  Measure ionization (corrected for P_ion, P_pol, P_TP, P_elec) at the calibration point.
        6.  Dose = M * P_gr * k'_R50 * N_D,w^Co60 * k_ecal (or similar formalism based on cross-calibration).
    *   *Output Factor:* Expressed as cGy/MU at the calibration point for one dual field.
*   **Relative Dosimetry:**
    *   *PDD Curves:* Measured with parallel-plate chamber.
    *   *Profiles:* Measured with small ion chambers, diodes, or film.
    *   *Surface Dose Uniformity (6-field):* Measured on the cylindrical phantom using film (Gafchromic preferred) or multiple TLDs/OSLDs.
*   **B-Factor Determination:** Crucial link between calibration point dose and patient skin dose.
    *   *Definition:* B = (Average Dose near surface of cylindrical phantom from 6 fields) / (Dose at calibration point in flat phantom from 1 dual field).
    *   *Measurement:* Requires careful measurement of both quantities under their respective defined conditions.
    *   *Value:* Typically 2.5-3.1, reflecting the overlap and contribution from multiple fields at the surface.
    *   *Constancy:* Must be verified periodically as it depends critically on beam geometry and uniformity.
*   **MU Calculation:**
    *   MU_per_beam = (Prescribed_Dose_per_fraction) / (Output_Factor_cal_point * B_Factor)
    *   Relies entirely on the accurate determination of the output factor and B-factor.
    *   *Practical Example:* If Rx = 100 cGy/fraction, Output = 0.04 cGy/MU, B = 3.0, then MU per beam = 100 / (0.04 * 3.0) = 100 / 0.12 = 833 MU.

## 5. X-ray Contamination: Measurement and Control

*   **Source:** Bremsstrahlung from electron interactions (accelerator head, air, scatterer, patient).
*   **Measurement:** Measured as %dd(x) = (Dose at depth beyond Rp / Dose at dmax) * 100%.
    *   Use an ion chamber in a flat phantom at a depth like 10 cm.
    *   Ensure sufficient buildup material over the chamber for photon dose measurement.
*   **Requirement:** Should be low, typically <4% (OMP), contributing <0.7-1.6 Gy total body dose over the course (EORTC/OMP).
*   **Control:** Primarily achieved by the dual-field angulation strategy. Careful selection of scatterer material (low Z) also helps.

## 6. In Vivo Dosimetry (IVD) Procedures

*   **Purpose:** Essential to verify dose delivery uniformity on the actual patient, identify systematic under/overdosing, and confirm shield effectiveness.
*   **Detectors:** TLDs or OSLDs preferred. Must be calibrated for the TSEI electron energy spectrum.
*   **Placement:** Standardized locations (~10-20 points) covering representative areas (forehead, chest, back, flanks, limbs) and potentially critical areas (e.g., near eyes, boost regions, intertriginous zones).
*   **Frequency:** Typically performed at the start of treatment and periodically throughout the course.
*   **Analysis:** Compare measured doses to the expected prescription dose. Deviations (e.g., > ±10-15%) may indicate setup issues or the need for adjustments/boosts.
    *   *Practical Example:* IVD results consistently show <85% of prescribed dose on the soles of the feet and scalp vertex. This confirms the need for planned boost fields to these areas.

## 7. Shielding and Boost Field Dosimetry

*   **Shielding:**
    *   *Eyes:* Internal lead shields (~1-2 mm thick, depending on energy). Dose under the shield should be verified (phantom measurement or IVD placed near eye during treatment) to be <15%.
    *   *Nails:* Lead strips (~2 mm).
    *   *Dosimetry:* Requires knowledge of electron transmission through lead at the relevant energy.
*   **Boost Fields:**
    *   *Purpose:* Treat underdosed areas or thick tumors.
    *   *Technique:* Standard electron fields (appropriate energy, standard SSD, using applicators).
    *   *Dosimetry:* Standard electron field dosimetry (TG-51) applies. Energy selected based on target depth (e.g., R90 = depth).
    *   *Integration:* Need to estimate the dose contribution from the main TSEI treatment to the boost area to determine the required boost dose.

## 8. Quality Assurance Specific to TSEI

Extends standard linac QA (TG-142) with TSEI-specific checks.

*   **Output Constancy:** Daily/weekly check at TSEI SSD/setup.
*   **Energy Constancy:** Periodic check of PDD curve (Rp, R80) at TSEI SSD.
*   **Beam Uniformity:** Periodic check of flatness/symmetry profiles at treatment plane.
*   **X-ray Contamination:** Periodic measurement.
*   **B-Factor Constancy:** Periodic verification.
*   **Safety Interlocks:** Door interlocks, audio/visual monitoring.
*   **Mechanical Checks:** Gantry/collimator angle accuracy, distance indicators (lasers, ODI), patient positioning devices.
*   **Dosimetry System QA:** Calibration of parallel-plate chamber, IVD system calibration and checks.
*   **End-to-End Phantom Test:** Irradiate anthropomorphic or cylindrical phantom with IVDs, simulating the entire process from calculation to delivery verification.

## 9. Conclusion

TSEI, particularly the Stanford technique, is a complex procedure requiring specialized physics support and meticulous dosimetry. Achieving uniform skin dose while sparing deep tissues and minimizing X-ray contamination relies on careful beam generation, geometric setup (extended SSD, angled dual fields, 6 positions, scatterer), and rigorous dosimetry. Key elements include calibration with parallel-plate chambers under TSEI conditions, accurate determination of the B-factor, comprehensive beam uniformity measurements, control of X-ray contamination, and routine use of in vivo dosimetry. Robust QA is essential to ensure safe and effective treatment delivery.


