# Section 4.3: Management of Inter- and Intra-fraction Variations - Clinical Scenarios

## Introduction

These scenarios illustrate the practical application of concepts discussed in managing inter- and intra-fraction variations in radiation therapy. They highlight the decision-making process, technological considerations, and the importance of various Task Group recommendations in real-world clinical settings.

## Scenario 1: Lung SBRT with Significant Respiratory Motion

- **Patient:** 68-year-old male with a 2 cm medically inoperable Stage I non-small cell lung cancer (NSCLC) in the right lower lobe.
- **Challenge:** A 4DCT simulation reveals the tumor moves approximately 1.8 cm in the superior-inferior (SI) direction and 0.5 cm in the anterior-posterior (AP) direction due to respiration.
- **Management Options Considered:**
    1.  **Motion-Encompassing (ITV):** Create an Internal Target Volume (ITV) encompassing the tumor's full range of motion observed on the 4DCT, plus a setup margin (PTV = ITV + SM). *Concern:* This results in a large PTV, potentially increasing dose to the lung, ribs, and other nearby structures, which is undesirable for SBRT where dose gradients are steep.
    2.  **Respiratory Gating:** Deliver radiation only during a specific portion of the respiratory cycle (e.g., end-exhale phase) when tumor motion is minimal. Requires real-time monitoring.
    3.  **Tracking:** Use a system (like CyberKnife or potentially DMLC tracking) to follow the tumor's motion in real-time. *Availability:* Not available at this institution.
    4.  **Breath-Hold (DIBH):** Patient holds breath at deep inspiration. *Feasibility:* Patient has moderate COPD and finds consistent DIBH difficult.
- **Chosen Strategy: Respiratory Gating**
    - **Rationale:** Offers a good compromise by reducing the required margin compared to the ITV approach while being feasible for the patient.
    - **Workflow:**
        - **4DCT Analysis:** Maximum Intensity Projection (MIP) and Average Intensity Projection (AvIP) CTs are generated. The tumor extent is carefully delineated on all phases to define the GTV envelope.
        - **Surrogate Correlation:** An external marker block (RPM system) is placed on the patient's abdomen during 4DCT. The external marker motion is correlated with the internal tumor motion derived from the 4DCT phases.
        - **Gate Window Selection:** The end-exhale phase (e.g., 40-70% of the cycle) is chosen as the gating window, where tumor motion is observed to be smallest and most stable.
        - **Planning:** The GTV is defined on the average CT or a specific phase within the gate window. A smaller margin (compared to ITV) is added for residual motion within the gate and setup uncertainty to create the PTV.
        - **IGRT & Delivery:**
            - Daily pre-treatment kV CBCT is acquired and registered to the planning CT (using bony anatomy and verifying tumor position) to correct setup errors.
            - The RPM system monitors the patient's breathing. The linac beam is automatically turned on only when the external marker signal falls within the predefined 40-70% phase window.
            - Intra-fraction verification (e.g., triggered kV images or periodic CBCT) may be used to check for baseline drift or changes in the breathing pattern/correlation.
- **Relevant TGs:** TG-76 (detailed guidance on respiratory motion management), TG-101 (specifics for SBRT precision and margins).

## Scenario 2: Prostate IMRT with Inter-fraction Organ Motion

- **Patient:** 72-year-old male receiving definitive IMRT (78 Gy in 39 fractions) for intermediate-risk prostate cancer.
- **Challenge:** Daily kV CBCT imaging reveals significant day-to-day variation in prostate position, primarily driven by changes in rectal filling. On some days, a full rectum displaces the prostate anteriorly by up to 1 cm compared to the planning CT.
- **Management Strategy: Daily Online IGRT with Soft-Tissue Registration**
    - **Rationale:** Correcting for daily setup variations and organ motion is essential to ensure accurate dose delivery to the prostate while sparing the rectum and bladder.
    - **Workflow:**
        - **Immobilization:** Patient immobilized in a vac-lok bag.
        - **Planning:** Gold fiducial markers were implanted into the prostate prior to CT simulation. Planning CT acquired with instructions for moderately full bladder and empty rectum. PTV margin created around CTV (prostate +/- seminal vesicles) accounts for microscopic extension, setup uncertainty, and expected organ motion.
        - **IGRT & Delivery:**
            - Patient is instructed to follow bladder/rectal preparation protocol before each treatment.
            - Daily pre-treatment kV CBCT is acquired.
            - **Registration:** The CBCT is automatically registered to the planning CT based on the implanted gold fiducial markers. Bony registration is used as a secondary check. Soft-tissue registration (aligning the prostate contour) is also reviewed.
            - **Correction:** Calculated translational and rotational shifts are applied via remote couch movement.
            - **Verification:** If shifts are large (> 5-7 mm), a verification CBCT may be acquired after correction.
            - Treatment is delivered.
    - **Considerations:**
        - **Margin Adequacy:** Consistent large shifts may prompt a review of PTV margin adequacy.
        - **Offline ART:** If systematic changes are observed (e.g., prostate consistently displaced anteriorly despite protocol adherence), offline adaptation (re-planning) might be considered, although daily online correction is often sufficient.
- **Relevant TGs:** TG-132 (principles and QA of image registration algorithms, crucial for accurate alignment).

## Scenario 3: Head & Neck IMRT with Anatomical Changes During Treatment

- **Patient:** 55-year-old female undergoing concurrent chemoradiation for oropharyngeal cancer.
- **Challenge:** During week 4 of a 7-week treatment course, the patient experiences significant weight loss (~5 kg) and mucositis. The weekly verification CBCT shows noticeable tumor shrinkage and medial displacement of the parotid glands compared to the initial planning CT. The thermoplastic mask fit also appears slightly loose.
- **Management Strategy: Offline Adaptive Replanning**
    - **Rationale:** The observed anatomical changes are significant enough to potentially compromise target coverage (if the tumor has shrunk away from the high-dose region) and increase dose to OARs (parotids now closer to high-dose areas). The standard PTV margin may not adequately cover these changes, and the initial plan is no longer optimal.
    - **Workflow:**
        - **Detection:** Changes identified during routine weekly IGRT (CBCT) review by the physician and physicist.
        - **Decision:** Team decides that the anatomical changes warrant adaptive replanning.
        - **Re-simulation:** A new CT simulation is acquired, potentially with a new mask if the fit is poor.
        - **Re-contouring:** Target volumes and OARs are re-delineated on the new CT scan.
        - **Plan Evaluation:** The original plan's dose is recalculated on the new CT/contours to quantify the dosimetric impact of the changes.
        - **Re-planning:** A new IMRT plan is created and optimized based on the current anatomy and clinical goals.
        - **QA:** The new plan undergoes standard physics QA checks.
        - **Implementation:** The adapted plan is implemented for the remaining treatment fractions.
- **Relevant TGs:** TG-132 (image registration needed to compare initial and new CTs accurately), TG-263 (standardized nomenclature essential for consistent re-contouring and plan evaluation).

## Scenario 4: Potential Application of Online Adaptive Radiotherapy (Illustrative)

- **Patient:** 60-year-old male with borderline resectable pancreatic cancer undergoing SBRT.
- **Challenge:** The pancreas and target volume are adjacent to highly mobile organs like the duodenum and stomach. Daily variations in bowel gas and organ position pose a significant risk of OAR overdose or target underdose with conventional IGRT and PTV margins.
- **Potential Strategy: Online Adaptive Radiotherapy (e.g., using MRI-Linac)**
    - **Rationale:** Allows for daily visualization of soft tissues and adaptation of the plan immediately before treatment to account for the specific anatomy of the day.
    - **Hypothetical Workflow:**
        - **Daily Imaging:** Pre-treatment MRI scan acquired on the MRI-Linac.
        - **Registration & Contouring:** Daily MRI registered to planning CT/MRI. OARs and target may be re-contoured or adjusted using deformable registration and AI-based tools.
        - **Plan Adaptation:** The treatment plan is re-optimized based on the daily anatomy, ensuring target coverage while respecting OAR constraints.
        - **Online QA:** Rapid verification checks are performed on the adapted plan.
        - **Delivery:** Treatment is delivered, potentially with real-time MRI monitoring/gating.
- **Note:** This advanced technique aims to minimize margins and maximize accuracy for challenging cases with significant inter-fraction variation near critical structures.
- **Relevant TGs:** TG-281 (provides guidance on the implementation and QA of online ART; *report currently unavailable for deep dive*).

