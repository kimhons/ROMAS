# Section 4.3: Deep Dive - AAPM TG-263: Standardizing Nomenclatures in Radiation Oncology

## Introduction

AAPM Report TG-263, published in 2018, addresses the critical need for standardized nomenclatures for anatomical structures (targets and organs-at-risk - OARs), planning structures, and dosimetric metrics within radiation oncology. Inconsistencies in naming conventions hinder communication, data pooling, automated processing, quality assurance, and overall safety and efficiency. This report provides guidelines and recommendations to promote harmonization across clinical practice, research, and vendor platforms. This deep dive summarizes the key findings and recommendations of TG-263.

## 1. Background and Motivation

- **Data Pooling:** Lack of standard names makes it extremely difficult to aggregate and analyze data from different institutions or trials for outcomes research, identifying dose-response relationships, or building predictive models.
- **Communication:** Ambiguous or inconsistent names can lead to misinterpretations between physicians, physicists, dosimetrists, and therapists, potentially impacting treatment quality and safety.
- **Automation:** Standardization is essential for developing automated tools for contouring (e.g., atlas-based segmentation), plan checking (scripting), data extraction, and workflow management.
- **Interoperability:** Consistent naming facilitates data exchange between different software systems (TPS, OIS, PACS) using standards like DICOM.
- **Challenges:** Despite previous efforts (e.g., ICRU reports), significant variability persists in clinical practice due to historical conventions, vendor limitations, and lack of universally adopted standards.

## 2. Evaluation of Current Practices

TG-263 surveyed existing practices and identified widespread inconsistencies in naming:
- **Non-Target Structures (OARs):** Variations in abbreviations, laterality specification (L/R, Lt/Rt, Left/Right), use of underscores or spaces, inclusion of dose constraints in names, and overall anatomical precision.
- **Target Structures:** Variations in naming conventions for GTV, CTV, ITV, PTV, including suffixes for dose levels, boost volumes, or specific imaging modalities (e.g., GTV_PET, PTV_70Gy).
- **Derived/Planning Structures:** Inconsistent naming for structures created for planning purposes (e.g., optimization rings, avoidance structures, boolean combinations like PTV-OAR).
- **Dose/Volume Metrics:** Variations in specifying DVH parameters (e.g., D95 vs. D95%, V20Gy vs. V2000cGy, near-max dose D0.03cc vs. D1cc vs. Dmax).
- **Vendor/DICOM Limitations:** Historical limitations in DICOM structure naming fields and inconsistent implementation by vendors contributed to the problem.

## 3. Related Standards

TG-263 reviewed existing anatomical and coding standards relevant to radiotherapy:
- **Foundational Model of Anatomy (FMA):** A comprehensive ontology of anatomical structures.
- **SNOMED CT:** A clinical terminology system used in electronic health records.
- **DICOM:** The standard for medical image communication, including RT Structure Sets (RTSS) and RT Dose objects. TG-263 notes the importance of DICOM attributes like `StructureSetROISequence` and `RTROIObservationsSequence` for encoding structure identity beyond just the free-text name.

## 4. Recommendations for Non-Target Structure (OAR) Nomenclature

- **Guiding Principles:**
    - **Clarity & Unambiguity:** Names should be easily understood and unique.
    - **Conciseness:** Avoid unnecessary length.
    - **Machine Readability:** Facilitate automated processing.
    - **Consistency:** Use consistent patterns.
    - **Laterality:** Specify laterality (Left/Right) using prefixes `L_` and `R_`.
    - **Anatomical Hierarchy:** Use consistent terms based on anatomical standards (e.g., FMA).
    - **Avoid Dose/Planning Info:** Do not include dose constraints or planning intent (e.g., `_opti`, `_avoid`) in the primary anatomical name.
- **Structure:** `[Laterality_]BaseName[_Modifier]`
    - `Laterality_`: `L_` or `R_` (required for paired organs).
    - `BaseName`: Primary anatomical term (e.g., `Parotid`, `FemoralHead`, `SpinalCord`). Use CamelCase (capitalize first letter of each word, no spaces).
    - `_Modifier`: Optional suffix for specific parts or related concepts (e.g., `_prox` for proximal, `_dist` for distal, `_prv` for previously treated volume). Use lowercase after underscore.
- **Provided List:** TG-263 provides an extensive table of recommended standard names for common OARs across various body sites, mapped to FMA and SNOMED CT codes where possible.
    - *Examples:* `SpinalCord`, `Brainstem`, `L_Lens`, `R_FemoralHead`, `Heart`, `Esophagus`, `Rectum`.

## 5. Recommendations for Target Structure Nomenclature

- **Guiding Principles:** Build upon ICRU 50/62/83 definitions; maintain clarity, consistency, and machine readability.
- **Structure:** `[Type][Index][_Modifier][_Laterality][_Dose]`
    - `Type`: Core target type (required): `GTV`, `CTV`, `ITV`, `PTV`.
    - `Index`: Numerical index (required, starting from 1) to distinguish multiple targets of the same type (e.g., `GTV1`, `GTV2`).
    - `_Modifier`: Optional descriptor (lowercase) for specific characteristics (e.g., `_LN` for lymph node, `_prim` for primary, `_met` for metastasis, `_PET` for PET-defined, `_wk4` for week 4 adaptation).
    - `_Laterality`: Optional `_L` or `_R` if needed for specific targets (distinct from OAR laterality prefix).
    - `_Dose`: Optional dose level associated with the volume (e.g., `_70Gy`).
- **Examples:**
    - `GTV1` (Primary gross tumor)
    - `CTV1` (Clinical target volume associated with GTV1)
    - `PTV1_70Gy` (Planning target volume for GTV1, prescribed 70 Gy)
    - `GTV2_LN_L` (Gross tumor in a left lymph node, second GTV defined)
    - `CTV_wk4` (CTV adapted at week 4)

## 6. Recommendations for Dose Volume Histogram (DVH) Metrics

- **Units:** Use standard units: `Gy` for dose, `cc` for absolute volume, `%` for relative volume.
- **Dose Metrics (`Dx`):**
    - `Dmean`, `Dmedian`
    - `Dmax` (use with caution, prefer near-max)
    - `Dmin` (use with caution, prefer near-min)
    - `D<Vol>[Unit]`: Dose covering a specific volume (e.g., `D95%` = dose covering 95% of volume, `D2cc` = dose covering 2cc of volume).
- **Volume Metrics (`Vx`):**
    - `V<Dose>[Unit]`: Volume receiving at least a specific dose (e.g., `V20Gy` = volume receiving >= 20 Gy, `V100%` = volume receiving >= 100% of prescribed dose).
- **Conformity & Gradient Metrics:** Reference specific indices (e.g., Paddick CI, Gradient Index) by name.
- **Clarity:** Explicitly state units (`%` or `cc`/`Gy`).

## 7. Recommendations to Vendors

- Adopt and facilitate the use of TG-263 nomenclature within TPS and OIS.
- Provide flexible tools for managing and customizing structure name lists.
- Support longer DICOM tag fields for structure names if necessary.
- Leverage DICOM `RTROIObservationsSequence` to store coded anatomical identity (e.g., FMA/SNOMED codes) alongside the free-text name, enabling more robust data interpretation.
- Improve tools for automated DVH metric extraction using standardized naming.

## 8. Implementation and Future Directions

- **Pilot Study:** TG-263 conducted a pilot study showing feasibility and benefits of adopting the standard nomenclature.
- **Implementation:** Encourage gradual adoption by clinical sites, trial groups, and vendors. Provide templates and tools.
- **Clinical Trial Groups:** Recommend mandating standardized nomenclature for trial data submission.
- **Maintenance:** Propose establishing a standing working group to maintain and update the nomenclature lists as needed.

## Conclusion

Standardized nomenclature, as proposed by TG-263, is a foundational element for improving safety, quality, efficiency, and research capabilities in radiation oncology. By providing clear guidelines for naming structures and DVH metrics, the report aims to reduce ambiguity, enhance communication, and enable automation and large-scale data analysis. While adoption requires effort from clinicians, physicists, and vendors, the long-term benefits for the field are substantial. Consistent use of these standards is crucial for advancing the practice of radiation therapy.

