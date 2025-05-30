# Section 4.6: Deep Dive into TBI (Based on AAPM Report 17 & OMP)

This document provides a deeper exploration of Total Body Irradiation (TBI) concepts, techniques, dosimetry, and quality assurance, primarily drawing from AAPM Report 17 ("A protocol for the determination of absorbed dose from high-energy photon and electron beams", though the user likely meant the TBI-specific report, which is actually Report 17's predecessor or related clinical reports; however, Report 17 does cover fundamental dosimetry relevant here) and the Oncology Medical Physics (OMP) webpage summary.

## 1. Introduction and Rationale

*   **Purpose:** TBI is a radiotherapy technique where the entire body receives a significant radiation dose, typically as part of a preparative regimen for Hematopoietic Stem Cell Transplantation (HSCT).
*   **Goals (as per OMP & clinical context):**
    *   **Myeloablation:** Eradicate the patient's bone marrow to allow engraftment of donor stem cells.
    *   **Immunosuppression:** Suppress the host immune system to prevent graft rejection (especially in allogeneic HSCT).
    *   **Tumor Cell Kill:** Eradicate residual malignant cells (e.g., leukemia, lymphoma) throughout the body, including sanctuary sites.
*   **Historical Context:** Early TBI used orthovoltage X-rays or Cobalt-60 units. Modern TBI predominantly uses high-energy photons from linear accelerators (linacs).

## 2. Physics Principles and Techniques

*   **Beam Energy:** High-energy photons (≥ 6 MV, often 6-10 MV) are required for sufficient penetration across the entire body width/thickness (OMP).
*   **Large Field Requirement:** Treating the whole body necessitates creating very large, uniform radiation fields, far exceeding standard linac field sizes.
*   **Techniques (OMP & Report 17 context):**
    *   **Extended SSD Techniques:**
        *   *Method:* Patient positioned at a large distance (e.g., 3-5 meters) from the linac isocenter. Large fields achieved by opening collimators fully and utilizing the diverging beam.
        *   *Common Setups:* AP/PA (patient standing or lying, treated from anterior and posterior) or bilateral (patient lying on side, treated from left and right).
        *   *Challenges:* Requires a large treatment room; significantly reduced dose rate leads to long treatment times; beam profile flatness degrades at extended distances.
    *   **Sweeping Beam / Translating Couch:**
        *   *Method:* Patient lies on a couch that translates through a fixed, wide beam (e.g., a long rectangular field), or the beam itself sweeps across the stationary patient.
        *   *Challenges:* Requires specialized equipment and software; complex commissioning and QA due to moving components; potential for dose variations at field junctions if multiple sweeps are needed.
    *   **Dedicated Units:** Historically, dedicated Cobalt-60 units or specialized linacs were used.
*   **Dose Homogeneity:**
    *   *Goal:* Achieve a dose distribution within a specified tolerance (e.g., ±10%) relative to the prescription point (often midline at umbilicus or average midline dose) (Implied by Report 17 principles, clinical standard).
    *   *Challenges:* Significant variations in patient thickness and contour; beam divergence; beam profile non-flatness at extended distances.
    *   *Compensation Methods:* Tissue compensators (custom-designed filters to attenuate the beam more over thinner body parts), beam spoilers, field weighting, or potentially intensity modulation (IMRT-TBI - more advanced).
*   **Beam Spoilers:**
    *   *Purpose:* To increase the dose in the build-up region near the patient surface, ensuring adequate dose to superficial tissues/skin.
    *   *Mechanism:* A low-Z material (e.g., acrylic sheet) placed close to the patient generates secondary electrons, shifting dmax superficially (OMP).

## 3. Dosimetry and Calibration (Report 17 Relevance)

*   **Reference Dosimetry:** While Report 17 focuses on standard field dosimetry, its principles apply. Calibration must be performed under conditions representative of the TBI setup.
    *   *Calibration Point:* Typically performed in a large water or solid water phantom at the treatment distance (extended SSD) or equivalent reference point for sweeping beam.
    *   *Phantom Size:* Must be large enough to provide full scatter conditions for the large TBI field.
    *   *Chamber Choice:* Use appropriate ionization chamber and electrometer calibrated according to national standards (e.g., TG-51 in the US, which builds on Report 17 principles).
*   **Treatment Planning Systems (TPS):**
    *   *Challenges:* Standard TPS algorithms may struggle with extended SSDs, large fields, complex patient contours, and compensator calculations. Algorithm validation under TBI conditions is crucial.
    *   *Data Requirements:* Requires accurate beam data measured at extended distances.
*   **In-Vivo Dosimetry (IVD):**
    *   *Mandatory Requirement:* Considered essential due to the complexities and uncertainties (AAPM clinical recommendations, OMP).
    *   *Purpose:* Verify the dose delivered to specific points on the patient during treatment, allowing for adjustments if significant deviations (> ±10% typically) are found.
    *   *Detectors:* Diodes (real-time) or TLDs (integrated dose) are commonly used.
    *   *Placement:* Standardized locations (e.g., head, neck, chest, umbilicus, pelvis, extremities) and critical locations (e.g., under lung blocks).

## 4. Dose Prescription and Fractionation

*   **Prescription Point:** Often midline at the level of the umbilicus, or sometimes an average midline dose.
*   **Total Dose & Fractionation:** Highly variable based on institutional protocol, transplant type (allo vs. auto), and disease.
    *   *Common Fractionated Regimens:* 12 Gy in 6 fractions (2 Gy BID), 13.2 Gy in 8 fractions (1.65 Gy BID), etc. (OMP).
    *   *Single Fraction:* Less common now due to higher toxicity (e.g., 10 Gy in 1 fraction).
    *   *Rationale for Fractionation:* Reduces late normal tissue toxicity (especially lungs) by allowing for repair between fractions.

## 5. Organ Shielding

*   **Lungs:** Most critical organ requiring shielding due to risk of fatal interstitial pneumonitis.
    *   *Goal:* Limit mean lung dose (e.g., < 8-10 Gy for fractionated regimens).
    *   *Method:* Custom blocks (e.g., Cerrobend) or MLCs shaped to lung contours defined on CT simulation.
    *   *Verification:* Daily portal imaging (or other IGRT) is essential to confirm block position.
*   **Other Organs:** Kidneys may sometimes be shielded, especially in pediatric patients or if prior abdominal RT occurred. Lens shielding is less common with high-energy photons due to secondary electrons, but overall dose is considered.

## 6. Quality Assurance (QA)

*   **Comprehensive Program:** Essential due to complexity and high potential for error.
*   **Machine QA:** Regular linac QA plus specific checks under TBI conditions (output constancy at extended SSD, large field uniformity, safety interlocks, positioning aids).
*   **Patient-Specific QA:**
    *   Independent MU calculation check.
    *   Verification of compensator/block design and transmission.
    *   IVD system calibration and verification.
    *   End-to-end testing (anthropomorphic phantom) during commissioning and periodically.
*   **Treatment Delivery QA:**
    *   Patient identification and setup verification.
    *   Verification of all treatment parameters (distance, field size, angles, MU).
    *   Verification of compensator/spoiler/block placement.
    *   Daily image guidance for lung block verification.
    *   IVD placement and reading.
    *   Physics review of IVD results before subsequent fractions.

## 7. Clinical Considerations (Brief Overview)

*   **Toxicity:** Acute (nausea, vomiting, fatigue, mucositis, diarrhea, parotitis) and Late (pneumonitis, cataracts, infertility, secondary malignancies, endocrine dysfunction).
*   **Patient Support:** Requires significant supportive care (anti-emetics, hydration, monitoring).

*(This deep dive synthesizes information consistent with AAPM Report 17's dosimetry principles and clinical TBI practices as described on the OMP webpage and general knowledge. Specific details may vary based on institutional protocols and equipment.)*

