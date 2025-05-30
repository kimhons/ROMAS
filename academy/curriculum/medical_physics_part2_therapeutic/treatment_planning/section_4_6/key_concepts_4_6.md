# Section 4.6: Key Concepts in Total Body Irradiation (TBI) and Total Skin Electron Irradiation (TSEI)

This document outlines the key concepts for Total Body Irradiation (TBI) and Total Skin Electron Irradiation (TSEI), procedures requiring specialized techniques to treat large volumes or surfaces. The content aims for graduate-level depth, drawing from AAPM Report 17 and other provided references.

## Part 1: Total Body Irradiation (TBI)

### 1.1 Clinical Rationale and Indications

*   **Core Purpose:** TBI involves irradiating the entire body, primarily used as a conditioning regimen before Hematopoietic Cell Transplant (HCT), also known as Bone Marrow Transplant (BMT) or Stem Cell Transplant. Its main goals are immunosuppression to prevent graft rejection and eradication of residual malignant cells (e.g., leukemia, lymphoma) or genetically abnormal cells.
    *   **Immunosuppression:** TBI effectively ablates the host's immune system, particularly T-lymphocytes, reducing the risk of the recipient's body rejecting the donor marrow (graft-versus-host disease, GVHD, is a separate complication where donor cells attack the host).
    *   **Malignant Cell Eradication:** High doses aim to eliminate remaining cancer cells throughout the body, including sanctuary sites where chemotherapy might be less effective.
    *   **Myeloablation:** TBI destroys the patient's existing bone marrow, creating space for the transplanted donor stem cells to engraft and repopulate.
*   **Common Indications & Dose Regimens:**
    *   **High-Dose TBI (for HCT):**
        *   *Diseases:* Acute Leukemias (ALL, AML), Chronic Myelogenous Leukemia (CML), Aplastic Anemia, Lymphomas, Multiple Myeloma, certain solid tumors (e.g., Ewing's sarcoma as adjuvant).
        *   *Dose/Fractionation:* Historically, single high doses (e.g., 7.5-10 Gy) were used, but led to significant toxicity, especially pulmonary. Modern practice favors fractionated regimens (e.g., 12-14 Gy in 6-8 fractions over 3-4 days, often BID - twice daily) to improve the therapeutic ratio by exploiting differences in repair capacity between normal tissues and malignant cells. Hyperfractionation (more frequent, smaller doses) may further spare late-responding tissues.
        *   *Dose Rate:* Lower dose rates (e.g., 5-20 cGy/min) are crucial, particularly for single-fraction or hypofractionated regimens, to reduce acute and late toxicities, especially interstitial pneumonitis. Fractionation allows for higher total doses while potentially mitigating some dose-rate dependence.
    *   **Low-Dose TBI:**
        *   *Diseases:* Chronic Lymphocytic Leukemia (CLL), low-grade lymphomas, neuroblastoma.
        *   *Dose/Fractionation:* Typically involves very low daily doses (e.g., 10-15 cGy) given over several days/weeks (e.g., total dose 1.5-2 Gy). The intent is cytoreduction rather than complete ablation.
    *   **Half-Body Irradiation (HBI):** While distinct, HBI shares large-field techniques. Used for palliation of widespread metastatic disease (e.g., bone metastases) or sometimes as consolidation. Upper, lower, or mid-body fields are treated sequentially with high doses (e.g., 6-8 Gy single fraction).

### 1.2 Treatment Techniques and Setup

*   **Goal:** Deliver a uniform dose (typically aiming for +/- 10% along the midline or specified target volume) to the entire body while respecting critical organ tolerances, especially the lungs.
*   **Beam Energy:** Megavoltage photons (Cobalt-60 or linear accelerator) are used. Higher energies (e.g., 6-18 MV) are generally preferred:
    *   *Advantages:* Increased penetration provides better dose homogeneity across varying body thicknesses. Reduced skin dose (though this can be a disadvantage if skin is part of the target). Reduced lateral scatter dependence (Tissue Lateral Effect), improving uniformity near edges.
    *   *Disadvantages:* Requires methods to increase surface dose if needed (spoilers/scatter plates).
*   **Field Geometry & Patient Positioning:** Requires very large fields, achieved by extending the treatment distance (SSD).
    *   **Extended SSD:** Source-to-surface distances of 3-6 meters or more are common. This necessitates sufficient room space and often involves treating patients far from the isocenter.
    *   **Beam Arrangement:**
        *   *Parallel-Opposed Fields (AP/PA or Bilateral):* Most common. Patient stands, sits, or lies down (decubitus position for AP/PA, supine/prone for lateral).
            *   *AP/PA:* Often preferred for better dose uniformity and easier lung shielding. Requires support structures for standing/sitting or specialized couches.
            *   *Lateral:* Simpler setup (patient lying supine/prone), but requires more complex compensation for varying thickness (head, neck, legs).
        *   *Multiple Fields/Arcs:* Less common, potentially used in specialized facilities.
    *   **Immobilization:** Crucial for reproducibility, especially with fractionated treatments. Vacuum bags, alpha cradles, or specialized chairs/stands are used.
*   **Dose Rate Reduction:** Achieved by:
    *   Using very large SSDs (inverse square law).
    *   Lowering the machine output (pulse repetition frequency on linacs).
    *   Introducing beam attenuators or flattening filter removal (FFF beams inherently have higher dose rates, requiring careful management).
*   **Field Shaping & Shielding:**
    *   **Collimation:** Jaws are opened to maximum, often requiring collimator rotation (e.g., 45 degrees) to maximize diagonal field size.
    *   **Lung Shielding:** Lungs are a primary dose-limiting organ due to risk of fatal radiation pneumonitis. Custom blocks (e.g., Cerrobend) or MLCs (if feasible at extended distance) are used to reduce the mean lung dose (e.g., to < 8-10 Gy, depending on fractionation). Shielding is typically partial transmission (e.g., allowing 50% dose) to avoid underdosing adjacent tissues or tumor within the lung.
    *   **Other Shielding:** Kidneys, eyes (lens), gonads (if fertility preservation is desired) may also be shielded.

### 1.3 Dosimetry Principles and Challenges

*   **Calibration:** Must be performed under TBI conditions (extended SSD, large field size) as output factors, scatter conditions, and beam quality can differ significantly from standard calibration geometry (SSD=100cm, 10x10 field). Requires a suitable large phantom.
    *   **Reference Point:** Dose is typically prescribed and calibrated to a specific point, often the patient midline at the level of the umbilicus.
    *   **Dosimeters:** Ion chambers (calibrated according to TG-51 or similar protocol, with corrections for non-reference conditions), TLDs, OSLDs, diodes.
*   **Dose Uniformity:** Achieving dose uniformity (+/- 10%) is challenging due to:
    *   **Varying Patient Thickness:** Significant dose variations occur from head/neck to thorax to legs.
    *   **Lack of Scatter:** Reduced scatter contribution at edges (lateral) and exit surfaces (backscatter) compared to central regions.
    *   **Beam Horns/Flatness:** Beam profiles are less flat at extended distances.
    *   **Inverse Square Law:** Dose rate varies across the patient's length/width.
*   **Compensation Methods:** Used to achieve dose uniformity.
    *   **Compensating Filters:** Custom-shaped attenuators (e.g., lead, brass, acrylic) placed in the beam path (often near the machine head or on a shadow tray) to selectively reduce dose to thinner body parts. Requires careful design and placement.
    *   **Bolus:** Tissue-equivalent material placed directly on the patient surface. Increases skin dose and reduces the impact of contour irregularities but can be cumbersome.
    *   **Field Modulation (IMRT/VMAT):** Theoretically possible but technically complex and rarely used for TBI due to extreme field sizes and setup variations.
    *   **Positional Adjustments:** Varying SSD along the patient length (e.g., boosting extremities).
*   **Inhomogeneity Corrections (Lungs):** Dose calculation must account for the low density of lung tissue, which increases transmission and can lead to overdose if not corrected. Methods include:
    *   CT-based planning with heterogeneity corrections.
    *   Effective path length calculations.
    *   Direct measurement (in vivo dosimetry).
*   **In Vivo Dosimetry (IVD):** Essential for verifying delivered dose and ensuring accuracy, especially given the complexities and potential for error. TLDs, OSLDs, or diodes are placed at multiple points on the patient's skin (entrance/exit) and sometimes within cavities (e.g., oral) during treatment.
    *   Midline dose can be estimated from entrance/exit measurements.
    *   Provides verification of calculated doses, compensator effectiveness, and lung shielding.
*   **Output Factors & Scatter:** Collimator (Sc) and phantom (Sp) scatter factors differ significantly from standard conditions and must be measured or calculated for the specific TBI geometry.

### 1.4 Quality Assurance (QA)

*   **Comprehensive Program:** Requires a rigorous QA program beyond standard linac QA, addressing the unique aspects of TBI.
*   **Machine QA:** Includes standard checks (output, flatness, symmetry) but extended to TBI conditions (specific SSD, field size, gantry/collimator angles, low dose rate modes).
*   **Dosimetry System QA:** Calibration and cross-checks of all dosimeters used (ion chambers, IVD systems).
*   **Procedure QA:**
    *   **Phantom Measurements:** Full dosimetry measurements in anthropomorphic or large water phantoms simulating the TBI setup, verifying dose calculations, uniformity, compensator/shielding effects, and IVD procedures.
    *   **End-to-End Testing:** Simulating the entire process from prescription to delivery verification.
    *   **Patient-Specific QA:** Verification of compensator design/placement, shield placement, IVD placement, and initial treatment delivery monitoring.
    *   **Safety Interlocks & Procedures:** Verification of room monitors, communication systems, emergency procedures.

## Part 2: Total Skin Electron Irradiation (TSEI)

### 2.1 Clinical Rationale and Indications

*   **Core Purpose:** TSEI aims to deliver a uniform dose of electrons to the entire skin surface while minimizing dose to underlying tissues. Primarily used for widespread, superficial skin malignancies.
*   **Primary Indication:** Mycosis Fungoides (MF), a type of cutaneous T-cell lymphoma (CTCL). TSEI is highly effective, especially in early to intermediate stages (patch/plaque stage), offering high rates of complete response.
*   **Other Potential Indications:** Other rare widespread cutaneous conditions.
*   **Treatment Goal:** Eradicate malignant T-cells residing in the epidermis and dermis.
*   **Dose/Fractionation:** Typically 30-36 Gy delivered over 6-10 weeks (e.g., 4 days/week). Lower dose regimens (e.g., 12 Gy) may be used for palliation or in combination therapies.

### 2.2 Treatment Techniques and Setup (Stanford Technique Focus)

*   **Goal:** Achieve uniform electron dose (+/- 8-10% vertically, +/- 4% horizontally) over the entire skin surface to a specific depth (e.g., 80% isodose at >= 4mm) with rapid dose fall-off to spare underlying tissues and minimize X-ray contamination (< 0.7-1.6 Gy total).
*   **Electron Energy:** Low energies are required (typically 4-9 MeV at the accelerator window, resulting in 3-7 MeV at the patient surface) to limit penetration.
    *   Energy loss in air (~1 MeV per 4 meters) must be accounted for.
*   **Field Geometry & Patient Positioning (Stanford Technique):** Most common method, developed at Stanford University.
    *   **Extended SSD:** Large distances (3-8 meters) are used to create a large, uniform electron field (e.g., 200 cm high x 80 cm wide).
    *   **Dual Fields (Gantry Angulation):** To cover the patient height, two large electron fields are angled: one aimed above the head (~+20 deg) and one aimed below the feet (~-20 deg). These fields overlap significantly in the central region.
        *   *Reduces X-ray Contamination:* Angling the central axes away from the patient minimizes the dose contribution from forward-peaked Bremsstrahlung X-rays generated in the accelerator head, collimators, and air.
    *   **Six Positions:** The patient stands in 6 different positions (anterior, posterior, and four oblique: RAO, LPO, LAO, RPO) relative to the beam.
        *   Treatment is typically delivered over 2 or 3 days, treating 3 or 2 positions per day, respectively.
        *   This multi-field approach averages out dose variations, significantly improving surface dose uniformity compared to fewer fields.
    *   **Patient Platform:** Patient stands on a platform, often elevated to reduce floor scatter.
    *   **Scatterer (Spoiler):** A sheet of low-Z material (e.g., ~1 cm acrylic) is often placed ~15-30 cm in front of the patient.
        *   *Purpose:* Increases electron scattering angles, broadening the beam profile and improving dose uniformity across the curved patient surface, especially in tangential regions. It also increases the surface dose relative to the depth dose.
        *   *Effect:* Reduces electron penetration slightly and makes the dose fall-off less sharp.
*   **Alternative Techniques:**
    *   **Rotational:** Patient stands on a rotating platform while being irradiated by a large horizontal electron field.
    *   **Translational:** Patient moves horizontally through a large vertical electron field.
    *   **Arcing Beams (e.g., Pendulum Arc):** Gantry sweeps through an arc, potentially avoiding field matching issues.
    *   **Multiple Match Fields:** Using standard linac electron fields carefully matched together (complex and less common for total skin).

### 2.3 Dosimetry Principles and Challenges

*   **Calibration:** Complex due to non-standard conditions (extended SSD, large scattered fields, angled beams, presence of scatterer).
    *   **Reference Point:** Often defined at the patient treatment plane, at isocenter height, at dmax, for a single dual-field irradiation.
    *   **Dosimeters:** Parallel-plate ion chambers are recommended (per TG-25/TG-30/TG-51 principles adapted for TSEI conditions). Film (Gafchromic), TLDs, OSLDs, diodes are used for profile measurements, uniformity checks, and in vivo dosimetry.
    *   **Phantom:** Cylindrical phantoms (e.g., 30 cm diameter polystyrene) are often used to simulate the patient trunk for measuring surface dose uniformity and the 'B-factor'.
*   **Dose Uniformity:** Achieving uniformity over the complex 3D body surface is the primary challenge.
    *   **Factors Affecting Uniformity:** Beam flatness/symmetry, patient positioning accuracy, effectiveness of the 6-field technique, scatterer presence/position, room scatter.
    *   **Measurement:** Requires extensive measurements using film or multiple dosimeters on cylindrical and anthropomorphic phantoms.
*   **Penetration & Depth Dose:** Must ensure adequate dose at the target depth (e.g., 4mm) with rapid fall-off.
    *   **Measurement:** Depth dose curves measured using parallel-plate chambers in flat phantoms under TSEI conditions (extended SSD, scatterer).
    *   **Obliquity:** Effective depth dose is shallower than for perpendicular incidence due to the angled fields and curved patient surface.
*   **X-ray Contamination:** Must be minimized to limit dose to deeper organs and total body dose.
    *   **Sources:** Bremsstrahlung production in accelerator head, collimators, air, scatterer, and patient.
    *   **Measurement:** Measured at depth (e.g., 10 cm) beyond the electron range using ion chambers or TLDs. Should be < 4% of surface dose, contributing < 0.7-1.6 Gy total body dose over the course.
*   **Output Measurement & MU Calculation:**
    *   **Calibration Point Dose:** Dose measured per MU at the reference point for a single dual-field.
    *   **Treatment Skin Dose:** Mean dose measured near the surface of a cylindrical phantom irradiated by all 6 fields.
    *   **B-Factor:** Ratio relating the calibration point dose (from one dual field) to the average treatment skin dose (from all six fields). Typically 2.5-3.1. Accounts for dose contributions from multiple fields overlapping at the surface.
    *   **MU Calculation:** Uses the prescription dose, B-factor, and the calibration point dose output factor (cGy/MU).
*   **In Vivo Dosimetry (IVD):** Crucial for verifying dose delivery to critical areas and identifying under/overdosed regions. TLDs or OSLDs are placed at numerous standardized locations on the patient.
    *   Helps confirm uniformity and guide boost field requirements.

### 2.4 Shielding and Boosts

*   **Shielding:** Necessary to protect sensitive structures or areas not intended for treatment.
    *   **Eyes:** Internal lead eye shields (often coated with wax/plastic to reduce backscatter to the eyelid) are used to keep lens dose low (<15% of prescription).
    *   **Fingernails/Toenails:** Lead strips are often used to shield nail beds if not involved.
    *   **Other:** Specific areas may be shielded based on prior treatment or patient condition.
*   **Boost Fields:** Required for areas consistently underdosed by the 6-field technique or for treating thicker tumor nodules.
    *   **Underdosed Areas:** Perineum, soles of feet, scalp vertex, inframammary folds, inner thighs.
    *   **Boost Technique:** Typically delivered using standard electron fields (appropriate energy for depth) or sometimes orthovoltage X-rays.
    *   **Dose:** Aim to bring the dose in these regions up to the prescription level.

### 2.5 Quality Assurance (QA)

*   **Comprehensive Program:** Essential due to the non-standard technique and potential for significant dose errors.
*   **Machine QA:** Standard linac QA plus specific checks for TSEI mode (output stability at extended SSD, beam energy verification, profile constancy, safety interlocks, field size indicators).
*   **Dosimetry QA:** Calibration of dosimetry equipment under TSEI conditions. Verification of beam energy, depth dose, uniformity, output factors, B-factor, and X-ray contamination.
    *   Requires large water tanks or specialized phantoms.
    *   Regular checks of beam flatness/symmetry are critical.
*   **Procedure QA:**
    *   **Phantom Measurements:** Full simulation using anthropomorphic and cylindrical phantoms to verify dose distribution and IVD procedures.
    *   **Patient Positioning:** Verification using light fields, lasers, and potentially imaging.
    *   **IVD Program:** Robust procedure for placement, reading, and interpretation of IVD results.
    *   **Safety:** Clear procedures, checklists, communication protocols, emergency stops.


