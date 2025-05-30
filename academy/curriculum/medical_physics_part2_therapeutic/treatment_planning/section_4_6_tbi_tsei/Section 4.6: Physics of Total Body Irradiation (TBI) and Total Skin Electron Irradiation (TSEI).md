# Section 4.6: Physics of Total Body Irradiation (TBI) and Total Skin Electron Irradiation (TSEI)

This document delves into the detailed physics principles, techniques, dosimetry, and quality assurance required for the safe and effective delivery of Total Body Irradiation (TBI) and Total Skin Electron Irradiation (TSEI), aiming for a graduate-level understanding linked to practical clinical implementation.

## Part 1: Physics of Total Body Irradiation (TBI)

### 1.1. Fundamental Principles and Goals

*   **Objective:** Deliver a prescribed dose of radiation homogeneously (typically ±10%) to the entire body, primarily for hematopoietic stem cell transplant (HSCT) conditioning.
*   **Physics Challenge:** Achieving dose uniformity across a large, irregularly shaped volume with varying thicknesses, while simultaneously minimizing dose to critical organs, especially the lungs.
*   **Beam Choice:** High-energy photons (≥ 6 MV) are required for sufficient penetration across the body width/thickness (AP/PA or lateral dimensions).
    *   *Why High Energy?* Lower energies would result in excessive dose variation between the surface and midline, making compensation extremely difficult and increasing skin toxicity.

### 1.2. TBI Delivery Techniques

*   **Large Field Techniques (Extended SSD/SAD):**
    *   **Concept:** Position the patient at a significantly increased distance (e.g., 3-5 meters) from the source, utilizing the inverse square law fall-off and the periphery of a large field size (e.g., 40x40 cm at isocenter projected to a larger size at distance).
    *   **Setups:**
        *   **AP/PA:** Patient treated with anterior and posterior fields, often lying supine/prone or sitting/standing against a support frame.
        *   **Bilateral:** Patient treated with opposed lateral fields, typically lying on their side on a stretcher or standing.
    *   **Advantages:** Conceptually simpler field arrangement.
    *   **Disadvantages:** Requires very large treatment rooms; dose rate significantly reduced due to distance (inverse square law), leading to long treatment times; beam divergence can be significant; penumbra effects are magnified.
    *   *Practical Step:* Room geometry, gantry/collimator rotation limits, and couch positioning must be carefully assessed during commissioning.
*   **Sweeping/Translating Beam or Couch Techniques:**
    *   **Concept:** The linac gantry sweeps the beam across the stationary patient, or the patient is translated through a stationary beam (horizontal or vertical).
    *   **Advantages:** Can be performed in smaller rooms; potentially higher dose rates achievable compared to extreme SSD setups.
    *   **Disadvantages:** Requires specialized equipment or modifications; complex dosimetry and QA due to moving components; potential for dose variations at field junctions or due to speed inconsistencies.

### 1.3. Achieving Dose Homogeneity

*   **The Problem:** The human body has significant variations in thickness (e.g., chest vs. abdomen vs. head vs. extremities).
*   **Compensation Strategies:**
    *   **Compensating Filters:** Custom-designed filters (e.g., lead, brass, or specialized materials) placed in the beam path to selectively attenuate the beam in thinner body regions.
        *   *Design:* Requires detailed patient contour information (CT or manual measurements) and sophisticated calculation algorithms or manual methods.
        *   *Practical Step:* Filter placement must be accurate and reproducible; QA involves verifying filter transmission and position.
    *   **Tissue Compensation with Bolus/Missing Tissue Compensators:** Placing material (e.g., rice bags, water bags, custom molds) around thinner body parts to create a more uniform thickness for the beam to traverse.
        *   *Practical Step:* Bolus placement must be consistent; can be uncomfortable for the patient.
    *   **Beam Weighting:** Adjusting the relative monitor units (MU) delivered through opposing fields (e.g., AP vs. PA) based on patient thickness or IVD results.
*   **Beam Spoilers:**
    *   **Purpose:** To intentionally increase the dose deposited in the superficial few centimeters of tissue by generating secondary electrons closer to the patient surface.
    *   **Rationale:** For leukemia treatment, ensuring adequate dose to leukemic cells potentially residing near the surface or in the marrow just beneath the bone is crucial.
    *   **Implementation:** A sheet of low-Z material (e.g., acrylic, ~1-2 cm thick) placed close to the patient (e.g., 15-30 cm away).
    *   *Physics:* The spoiler provides a medium for photon interactions closer to the patient, increasing the electron fluence entering the patient surface, thus shifting dmax closer to the surface.
    *   *Practical Step:* Spoiler position and integrity must be verified daily.

### 1.4. Dosimetry and Calculation

*   **Reference Dosimetry:**
    *   **Calibration Conditions:** Must mimic the treatment setup (extended distance, large field, presence of spoiler/compensators). Output measured in a reference phantom (e.g., water tank or solid water stack) at the reference depth (e.g., dmax or 10 cm) at the treatment distance.
    *   **Output Factors:** Need to account for the large field size and extended distance (Sc, Sp, off-axis factors, inverse square corrections).
    *   **TPR/TMR Data:** Required for dose calculations, potentially measured or calculated for the specific non-standard conditions.
*   **Treatment Planning:**
    *   **Simple Calculations:** Often based on midline dose calculations using patient separation data and measured beam data (TPR/TMR, output factors).
    *   **TPS-Based Planning:** Modern TPS can model extended distance setups, but require careful beam modeling and commissioning for these non-standard conditions. CT-based planning allows for heterogeneity corrections and more accurate compensator design.
*   **In-Vivo Dosimetry (IVD):**
    *   **Critical Importance:** Considered mandatory by AAPM Report 17 due to uncertainties in patient setup, body contour changes, and calculation limitations.
    *   **Detectors:** Semiconductor diodes or Thermoluminescent Dosimeters (TLDs) are commonly used.
        *   *Diodes:* Provide real-time readout; require calibration for energy/temperature dependence; angular dependence can be a factor.
        *   *TLDs:* Integrating dosimeters; require careful calibration, handling, and readout procedures; provide retrospective dose information.
    *   **Placement:** Strategically placed on the patient surface (entrance and exit) at multiple representative locations (head, neck, chest, umbilicus, pelvis, thigh, ankle). Placement over critical shielded organs (e.g., lungs) is also vital.
    *   **Action Levels:** Typically ±10% deviation from expected dose triggers investigation and potential adjustment (e.g., beam weighting, treatment time adjustment).
    *   *Practical Step:* Consistent placement and accurate recording of IVD results are paramount. Physics staff must review results promptly.

### 1.5. Lung Shielding

*   **Rationale:** Lungs are highly sensitive to radiation; interstitial pneumonitis is a major, potentially fatal complication of TBI.
*   **Goal:** Limit the mean lung dose (or dose according to specific protocol constraints, often < 8-10 Gy for fractionated TBI).
*   **Methods:**
    *   **Custom Blocks:** Traditionally made from low-melting-point alloys (e.g., Cerrobend) based on lung contours delineated on simulation films or DRRs.
        *   *Physics:* Attenuate the primary beam significantly. Transmission factor must be accurately known (~3-5% typical).
        *   *Practical Step:* Block position must be verified daily using portal imaging.
    *   **Multileaf Collimators (MLCs):** Modern linacs can use MLCs to shape the field and shield the lungs.
        *   *Advantages:* More efficient workflow, potential for intensity modulation (IMRT-TBI - complex, less common).
        *   *Disadvantages:* Requires accurate IGRT to ensure MLC position relative to lungs; potential for dose uncertainty due to leaf transmission and penumbra.
*   **Dosimetry Under Blocks:** IVD placement under the blocks (on the patient surface) is crucial to verify the actual dose received by the shielded lungs.

### 1.6. Quality Assurance (QA)

*   **Machine QA:** Rigorous QA beyond standard annual/monthly checks, focusing on:
    *   Output calibration consistency at treatment distance.
    *   Beam energy constancy.
    *   Field size accuracy and light/radiation field congruence at extended distance.
    *   Profile constancy/symmetry for large fields.
    *   Safety interlocks specific to TBI setup.
    *   Mechanical accuracy of gantry/collimator/couch for sweeping techniques.
*   **Dosimetry System QA:** Calibration and cross-checking of all dosimetry equipment (chamber, electrometer, IVD system).
*   **Patient-Specific QA:**
    *   Independent calculation check.
    *   Verification of compensator/block design and transmission.
    *   Dry run of patient setup and IVD placement.
    *   Physics presence during the first treatment fraction is highly recommended.
    *   Review of IVD results after each fraction (or as per protocol).
*   **Procedure:** A detailed, step-by-step written procedure covering simulation, planning, QA, setup, IVD, and emergency procedures is mandatory.

## Part 2: Physics of Total Skin Electron Irradiation (TSEI)

### 2.1. Fundamental Principles and Goals

*   **Objective:** Deliver a uniform dose to the entire skin surface (typically to a depth of a few mm) while minimizing dose to underlying tissues, primarily for treating widespread cutaneous T-cell lymphoma (CTCL).
*   **Physics Challenge:** Generating a large, uniform electron field over complex body contours and ensuring adequate dose to challenging areas (scalp, perineum, soles) while protecting sensitive structures (eyes).
*   **Beam Choice:** Low-energy electrons (typically 4-9 MeV) are used.
    *   *Why Low Energy Electrons?* Electrons deposit dose relatively uniformly near the surface (dmax depends on energy) and then exhibit a rapid dose fall-off, sparing deeper tissues. The specific energy is chosen based on the desired treatment depth (e.g., 6 MeV might treat to ~1 cm depth).

### 2.2. TSEI Delivery Techniques

*   **Stanford Technique (and variations):** Most common approach.
    *   **Concept:** Uses multiple (typically 6) large electron fields created at an extended distance (e.g., 3-4 meters SSD) by angling the linac gantry up and down relative to the horizontal.
    *   **Setup:** Patient stands on a platform at the treatment distance, often holding specific poses (e.g., arms raised/akimbo) to expose different skin surfaces. The patient is treated with anterior, posterior, and four oblique fields (two right, two left).
    *   **Dual Fields:** Each treatment position (anterior, posterior, RPO/RAO, LPO/LAO) is irradiated by two gantry angles (e.g., ± ~20° from horizontal) to improve vertical dose uniformity.
    *   **Beam Spoilers/Degraders:** An acrylic scatter plate (~1 cm thick) is typically placed near the end of the collimator or closer to the patient to scatter the electrons, broaden the beam profile for better uniformity over the large area, and increase the surface dose.
*   **Rotational Techniques:**
    *   **Concept:** Patient stands on a slowly rotating platform while being irradiated by one or two large electron fields.
    *   **Advantages:** Can potentially improve dose uniformity, especially over cylindrical body parts.
    *   **Disadvantages:** Requires specialized rotating platform with precise speed control; dosimetry and QA are complex.
*   **Translational Techniques:**
    *   **Concept:** Patient lies on a translating couch that moves through a wide electron beam.
    *   **Disadvantages:** Difficult to treat the entire skin surface uniformly, especially lateral aspects and extremities.

### 2.3. Achieving Dose Uniformity

*   **Challenges:**
    *   **Curved Surfaces & Obliquity:** Electron dose distribution is highly sensitive to beam incidence angle and surface curvature.
    *   **Self-Shielding:** Areas like the perineum, soles of feet, scalp vertex, axillae, inframammary folds are naturally shielded or receive oblique incidence.
    *   **Field Matching/Overlap:** Dose variations can occur at the edges where the influence of different treatment fields meets.
*   **Strategies:**
    *   **Multiple Fields & Angles (Stanford):** The six-field approach inherently improves uniformity by cross-firing the patient.
    *   **Patient Positioning:** Specific poses are designed to minimize self-shielding (e.g., arms raised, legs apart).
    *   **Beam Spoilers:** Help flatten the beam profile over the large treatment area.
    *   **Boost Fields:** Areas identified as significantly underdosed via IVD (often >15-20% below prescription) require supplementary treatment with small, direct electron fields.
        *   *Practical Step:* Boost fields require separate simulation, planning, and QA.

### 2.4. Dosimetry and Calculation

*   **Reference Dosimetry:**
    *   **Calibration Conditions:** Must be performed under the specific TSEI treatment conditions (extended distance, specific gantry angles, spoiler in place).
    *   **Phantom:** Measurements typically made in a large slab phantom (e.g., solid water) at the treatment distance.
    *   **Measurement Point:** Usually at the depth of maximum dose (dmax) on the central axis (or defined reference point).
    *   **Output:** Calibration yields dose rate (cGy/MU or cGy/min) under reference conditions.
*   **Treatment Time/MU Calculation:** Based on the prescribed dose and the calibrated output rate. Often involves calculating dose per field for the multi-field techniques.
*   **In-Vivo Dosimetry (IVD):**
    *   **Critical Importance:** Considered mandatory due to the extreme sensitivity of dose distribution to patient setup, positioning, and beam characteristics.
    *   **Detectors:** TLDs are most common due to their small size and flexibility. Diodes can also be used.
    *   **Placement:** A large number of dosimeters (e.g., 15-30) are placed at standardized locations covering the entire body surface, including potentially underdosed areas (scalp, perineum, soles, axillae, inframammary folds, medial canthi) and over shielded areas (eyes).
    *   **Analysis:** Results are mapped onto a patient diagram. Areas significantly outside tolerance (e.g., ±10% or ±15%) are identified. Underdosed areas may require boosts; significantly overdosed areas may require modification of shielding or setup.
    *   *Practical Step:* Meticulous record-keeping and mapping are essential. Physics review of IVD results before subsequent fractions (especially early in treatment) is crucial.

### 2.5. Shielding

*   **Eyes:** Internal eye shields (placed under the eyelids, typically tungsten shells with an aluminum coating) are mandatory to protect the lens from cataract formation.
    *   *Practical Step:* Requires topical anesthetic; proper placement and removal must be ensured.
*   **Nails:** Fingernails and toenails may be shielded (e.g., using lead foil or wax) if not involved by disease, to prevent nail damage/loss.

### 2.6. Quality Assurance (QA)

*   **Machine QA:**
    *   Output calibration consistency under TSEI conditions.
    *   Electron energy verification (PDD check) at treatment distance.
    *   Large field uniformity verification (profile scans in phantom at treatment distance).
    *   Light/radiation field congruence.
    *   Accuracy of gantry angles, collimator settings, distance indicators (ODI).
    *   Safety interlocks.
    *   Rotational platform speed/position accuracy (if used).
*   **Dosimetry System QA:** Calibration and cross-checking of IVD system (TLDs/diodes).
*   **Patient-Specific QA:**
    *   Independent calculation check.
    *   Verification of patient positioning and immobilization.
    *   Dry run of setup and IVD placement.
    *   Physics presence during the first treatment is highly recommended.
    *   Review of IVD results.
*   **Procedure:** A detailed, step-by-step written procedure is mandatory.


