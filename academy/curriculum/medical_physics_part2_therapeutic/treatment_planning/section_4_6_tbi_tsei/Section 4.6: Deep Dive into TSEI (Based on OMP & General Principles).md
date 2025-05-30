# Section 4.6: Deep Dive into TSEI (Based on OMP & General Principles)

This document provides a deeper exploration of Total Skin Electron Irradiation (TSEI) concepts, techniques, dosimetry, and quality assurance, primarily drawing from the Oncology Medical Physics (OMP) webpage summary and general radiation physics principles, as AAPM TG-30 was not available.

## 1. Introduction and Rationale

*   **Purpose:** TSEI is a specialized radiotherapy technique designed to treat the entire skin surface while minimizing dose to underlying tissues.
*   **Primary Indication:** Cutaneous T-cell lymphomas (CTCL), particularly Mycosis Fungoides (MF) and Sézary Syndrome (SS), especially in advanced stages (plaques, tumors, erythroderma) refractory to topical or systemic therapies (OMP).
*   **Goal:** Deliver a uniform, therapeutic dose to the entire skin envelope (typically to a depth of a few millimeters) with rapid dose fall-off to spare deeper organs.

## 2. Physics Principles and Techniques

*   **Beam Energy:** Low-energy electrons (typically 4-9 MeV) are used. The energy is chosen based on the desired treatment depth (e.g., 6 MeV provides dmax near the surface and treats effectively to ~1 cm depth with rapid fall-off).
*   **Large Field Requirement:** Similar to TBI, treating the entire skin surface requires creating very large, uniform electron fields.
*   **Techniques (OMP & Common Practice):**
    *   **Stanford Technique (Translational / Large Field):**
        *   *Method:* Patient stands at an extended distance (e.g., 3-5 meters) from the linac. Multiple (commonly 6) large electron fields are delivered from different angles (anterior, posterior, 4 obliques) using dual fields (two gantry angles per patient position) to cover the entire body surface.
        *   *Beam Spoilers/Scatterers:* An acrylic scattering plate is typically placed in the beam path near the linac head to broaden the electron beam profile for better uniformity over the large treatment area and to increase the surface dose (OMP).
        *   *Positioning:* Requires specific, reproducible patient positioning (e.g., arms abducted, legs apart) to minimize self-shielding.
    *   **Rotational Techniques:**
        *   *Method:* Patient stands on a rotating platform relatively close to the linac, which delivers a vertically scanned or shaped electron beam. The rotation aims to improve dose uniformity.
        *   *Challenges:* Requires specialized equipment (rotating platform, potentially scanning beam); complex commissioning and QA.
    *   **Translating Couch Techniques:**
        *   *Method:* Patient lies on a couch that translates through a wide, shaped electron beam.
        *   *Challenges:* May require field matching; potential for dose inhomogeneity at junctions or due to patient curvature.
*   **Dose Uniformity:**
    *   *Goal:* Achieve a uniform dose (e.g., within ±10% or ±15%) across the entire skin surface.
    *   *Challenges:* Highly complex patient surface contour; beam obliquity; self-shielding (skin folds, perineum, soles, scalp); beam matching (if applicable); variation in SSD across the patient surface.
    *   *Mitigation:* Multiple beam angles (Stanford), rotation, beam spoilers, careful patient positioning, supplementary boost fields.

## 3. Dosimetry and Calibration

*   **Reference Dosimetry:** Calibration must be performed under TSEI-specific conditions due to the extended SSD, large field size, and use of spoilers.
    *   *Method:* Often involves calibrating the output (dose/MU) in a phantom at the treatment distance using appropriate detectors (e.g., parallel-plate chamber recommended for electrons, potentially cylindrical chamber cross-calibrated) following protocols like AAPM TG-51 but adapted for the non-reference conditions.
    *   *Verification:* Output factors, PDDs, and profiles must be measured for the specific TSEI setup.
*   **Treatment Planning Systems (TPS):**
    *   *Challenges:* Standard electron algorithms in TPS may not accurately model dose distribution for the highly complex TSEI geometry (extended SSD, large fields, spoilers, extreme surface curvature, oblique incidence). Monte Carlo simulations are often considered the gold standard but are computationally intensive.
    *   *Use:* TPS may be used for estimating dose, planning boosts, or potentially for IMRT-based TSEI (advanced), but extensive commissioning and verification against measurements are crucial.
*   **In-Vivo Dosimetry (IVD):**
    *   *Mandatory Requirement:* Considered essential for verifying dose uniformity and identifying under/overdosed areas (OMP, clinical standard).
    *   *Detectors:* TLDs (thermoluminescent dosimeters) or OSLDs (optically stimulated luminescence dosimeters) are most common due to their small size and ability to be placed on curved surfaces. Diodes can also be used.
    *   *Placement:* A large number of dosimeters (~20-40) are placed at standardized locations covering the entire body surface during the initial treatment fractions.
    *   *Purpose:* Quantify dose delivered to various skin regions, confirm overall dose level, and guide the planning of necessary boost treatments.

## 4. Dose Prescription and Fractionation

*   **Total Dose:** Typically 30-36 Gy (OMP, common practice).
*   **Fractionation:** Usually delivered in small daily fractions (e.g., 1-2 Gy) over several weeks (e.g., 4-5 fractions/week for 4-9 weeks).
*   **Rationale:** Allows for skin recovery between fractions, managing acute toxicity while delivering a curative dose.

## 5. Shielding

*   **Eyes:** Internal eye shields (tungsten shields placed under the eyelids) are mandatory to protect the lens and prevent cataracts (OMP).
*   **Nails:** Shielding of fingernails and toenails (e.g., using lead foil) is often done unless they are involved with disease, to prevent nail damage/loss.
*   **Other:** Specific shielding is generally not required as the electron dose falls off rapidly, sparing deeper organs.

## 6. Boost Fields

*   **Rationale:** Due to inherent dose inhomogeneity, certain areas consistently receive lower doses than prescribed.
*   **Common Boost Areas:** Scalp vertex, perineum, soles of feet, inframammary folds, axillae, groin, potentially ears or other shielded areas if involved (OMP).
*   **Planning & Delivery:** Supplementary electron fields are planned (often using standard electron applicators/cutouts at standard SSD) to deliver additional dose to these specific areas, typically towards the end of the main TSEI course.

## 7. Quality Assurance (QA)

*   **Comprehensive Program:** Essential due to the non-standard nature of the technique.
*   **Machine QA:** Regular linac QA plus specific checks under TSEI conditions (output calibration, beam uniformity/symmetry for large electron fields, energy verification, spoiler integrity/positioning, safety interlocks).
*   **Patient-Specific QA:**
    *   Verification of patient positioning and immobilization.
    *   IVD system calibration and placement protocol.
    *   Boost field plan check (independent MU calculation).
    *   End-to-end testing (anthropomorphic phantom) during commissioning and periodically.
*   **Treatment Delivery QA:**
    *   Patient identification and setup verification (including specific positioning for Stanford technique).
    *   Verification of all treatment parameters (distance, field angles, MU).
    *   Verification of spoiler placement.
    *   Verification of eye shield placement.
    *   IVD placement verification.
    *   Physics review of IVD results to plan boosts.

## 8. Clinical Considerations (Brief Overview)

*   **Toxicity:** Primarily dermatologic - erythema, dry desquamation, moist desquamation (especially in folds), pruritus, edema, temporary alopecia, potential nail changes. Systemic effects like fatigue are also common. Late effects are rare but can include persistent skin dryness or pigment changes.
*   **Patient Management:** Requires significant patient education (procedure, positioning, skin care), meticulous skin care during treatment (moisturizers, gentle cleansing), management of skin reactions, and support for the lengthy treatment course.

*(This deep dive synthesizes information consistent with general TSEI practices as described on the OMP webpage and radiation physics principles. Specific details may vary based on institutional protocols and equipment.)*

