# Section 4.5: Clinical Scenarios - Special Procedures

**Objective:** To apply the physics principles and QA requirements of special procedures (SRS/SBRT, TBI, TSEI, IORT, Brachytherapy) to realistic clinical situations, enhancing problem-solving and decision-making skills.

## Scenario 1: SBRT for Early-Stage Lung Cancer

*   **Patient:** A 70-year-old male with a medically inoperable T1N0M0 non-small cell lung cancer (NSCLC) in the right upper lobe, measuring 2 cm.
*   **Challenge:** Deliver an ablative dose (e.g., 54 Gy in 3 fractions) to the tumor while minimizing dose to the ribs, spinal cord, esophagus, heart, and healthy lung tissue. The tumor exhibits significant respiratory motion (1.5 cm superior-inferior).
*   **Considerations & Tasks:**
    1.  **Motion Management:** Discuss the pros and cons of different motion management strategies (e.g., 4DCT-based ITV, abdominal compression, respiratory gating, real-time tracking). Which would be most appropriate here and why? (Ref: TG-76, TG-101)
    2.  **Immobilization:** What type of immobilization device would be suitable? How would its effectiveness be verified?
    3.  **Treatment Planning:** Describe the planning objectives (target coverage, OAR constraints based on TG-101). What beam arrangement (e.g., VMAT, static non-coplanar beams) might be used? Why is an advanced dose calculation algorithm crucial?
    4.  **QA:** What specific QA procedures are critical for SBRT delivery, beyond routine Linac QA? Consider small field dosimetry, end-to-end tests, and stricter Linac tolerances. (Ref: TG-101, TG-142 - *Not Checked*, TG-218)
    5.  **Delivery Verification:** How would you verify the accuracy of treatment delivery for each fraction (e.g., CBCT, orthogonal kV imaging)?

## Scenario 2: HDR Brachytherapy Boost for Cervical Cancer

*   **Patient:** A 55-year-old female undergoing external beam radiation therapy (EBRT) for locally advanced cervical cancer, now planned for an HDR brachytherapy boost.
*   **Challenge:** Deliver a high dose to the cervix and parametrium (defined on MRI) while strictly limiting dose to the bladder, rectum, and sigmoid colon, using a tandem and ovoid applicator.
*   **Considerations & Tasks:**
    1.  **Applicator Placement & Imaging:** Describe the process of applicator insertion and subsequent imaging (CT/MRI) for treatment planning. Why is MRI preferred for target delineation?
    2.  **Treatment Planning (TG-43 vs. MBDCA):** Plan the treatment using the TG-43 formalism. Discuss the dose objectives (e.g., Point A, HR-CTV D90) and OAR constraints (e.g., D2cc). Now, replan or evaluate using a Model-Based Dose Calculation Algorithm (MBDCA). What differences in dose distribution might be observed, particularly near the applicator or tissue interfaces? (Ref: TG-43 Update, TG-186)
    3.  **Source Calibration & QA:** Outline the essential QA steps for the HDR unit and the specific Ir-192 source, including source strength verification and positional accuracy checks.
    4.  **Delivery QA:** What checks are performed immediately before treatment delivery (e.g., applicator connection, plan transfer, length verification)? What emergency procedures should be in place?
    5.  **Combining EBRT & Brachytherapy Doses:** How are the doses from EBRT and brachytherapy combined biologically (e.g., using EQD2)?

## Scenario 3: Total Body Irradiation (TBI) Conditioning

*   **Patient:** A 15-year-old undergoing TBI (e.g., 12 Gy in 6 fractions, twice daily) as conditioning for a bone marrow transplant for leukemia.
*   **Challenge:** Deliver a uniform dose (±10%) to the entire body, with lung shielding to limit the mean lung dose (e.g., < 8 Gy).
*   **Considerations & Tasks:**
    1.  **Delivery Technique:** Describe a common TBI delivery technique (e.g., AP/PA large fields at extended SSD). What are the challenges in achieving dose uniformity?
    2.  **Commissioning:** What measurements are crucial during the commissioning of this TBI technique (e.g., output factors, TMR/TPR for large fields, phantom uniformity measurements)? (Ref: TG-29 - *Not Checked*)
    3.  **Patient Setup & Shielding:** How is the patient positioned? How are lung shields designed and placed? How is their position verified?
    4.  **In Vivo Dosimetry:** Where would you place in vivo dosimeters (e.g., OSLDs) on the patient? What is the purpose of these measurements, and what action is taken if measurements deviate significantly from the expected dose?
    5.  **Dose Calculation & Verification:** How is the monitor units (MU) or treatment time calculated? How does the in vivo dosimetry data relate to the planned dose?

## Scenario 4: IORT for Early-Stage Breast Cancer

*   **Patient:** A 60-year-old female undergoing lumpectomy for a small, early-stage breast cancer, eligible for IORT as a boost or sole treatment.
*   **Challenge:** Deliver a single dose (e.g., 20 Gy) to the surface of the lumpectomy cavity using a low-energy X-ray system (e.g., 50 kVp) during surgery.
*   **Considerations & Tasks:**
    1.  **Device & Applicator Selection:** Describe the low-energy X-ray IORT device. How is the appropriate applicator size and shape chosen by the surgeon and radiation oncologist?
    2.  **Dosimetry & Calibration:** How is the output of the IORT device calibrated? What formalism is used (Ref: TG-61 - *Not Checked*)? How is the dose prescribed (e.g., to the applicator surface, to a depth)?
    3.  **QA:** What daily QA checks are essential for the IORT device before use in the OR? (Ref: TG-72 - *Not Checked*)
    4.  **Procedure:** Describe the workflow in the operating room, including applicator placement, shielding of surrounding tissues (if any), radiation delivery, and radiation safety measures for staff.
    5.  **Limitations:** What are the limitations of IORT compared to conventional whole-breast irradiation or EBRT boost?

*(Note: These scenarios integrate concepts from multiple references, some of which were not checked for availability due to technical issues. Full details depend on the content of those specific reports.)*

