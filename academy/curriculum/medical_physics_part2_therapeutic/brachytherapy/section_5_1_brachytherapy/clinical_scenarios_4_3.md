# Clinical Scenarios: Section 4.3 - Brachytherapy Planning

This document presents various clinical scenarios involving brachytherapy planning to illustrate practical applications and challenges.

## Scenario 1: HDR Brachytherapy Boost for Cervical Cancer

*   **Patient Presentation:**
    *   62-year-old female diagnosed with FIGO Stage IIB squamous cell carcinoma of the cervix.
    *   Treatment plan involves definitive chemoradiation: EBRT to the pelvis (45 Gy in 25 fractions) with concurrent weekly cisplatin, followed by an HDR brachytherapy boost.
*   **Brachytherapy Procedure:**
    *   After completion of EBRT, patient undergoes placement of a tandem and ring intracavitary applicator under anesthesia.
    *   CT simulation is performed with the applicator in place.
*   **Planning Goals (GEC-ESTRO Guidelines):**
    *   **Target:** High-Risk Clinical Target Volume (HR-CTV) contoured based on MRI/CT and clinical exam.
        *   Goal: $D_{90}$ (dose covering 90% of HR-CTV) $\ge$ 85-90 Gy EQD2 (combined EBRT + Brachytherapy).
    *   **Organs at Risk (OARs):** Bladder, Rectum, Sigmoid Colon, Bowel.
        *   Goals (Hard Constraints): $D_{2cc}$ (max dose to 2cc volume) for Bladder < 90 Gy EQD2, Rectum < 75 Gy EQD2, Sigmoid < 75 Gy EQD2.
*   **Physics Planning Tasks:**
    *   **Applicator Reconstruction:** Accurately digitize the tandem and ring channels on the CT simulation images.
    *   **Contouring:** Assist radiation oncologist in contouring HR-CTV and OARs (Bladder, Rectum, Sigmoid).
    *   **Source:** HDR Ir-192 source.
    *   **Optimization:** Use inverse planning (e.g., IPSA) to optimize dwell times to achieve target $D_{90}$ goal while respecting OAR $D_{2cc}$ constraints.
    *   **Plan Evaluation:** Analyze DVHs for HR-CTV and OARs. Verify dose distribution visually on isodose lines. Calculate total EQD2 for target and OARs, combining EBRT and brachytherapy doses (using appropriate $\alpha/\beta$ ratios: e.g., 10 Gy for tumor/HR-CTV, 3 Gy for late-responding OARs).
    *   **QA:** Perform independent dose calculation check. Verify plan parameters before transfer to the afterloader.
*   **Potential Challenges:**
    *   Suboptimal applicator placement leading to difficulty covering HR-CTV without exceeding OAR limits.
    *   Significant variation in bladder/rectum filling between simulation and treatment fractions.
    *   Accurate contouring of HR-CTV, especially post-EBRT.

## Scenario 2: LDR Permanent Seed Implant for Low-Risk Prostate Cancer

*   **Patient Presentation:**
    *   68-year-old male with newly diagnosed, localized, low-risk prostate cancer (PSA < 10 ng/mL, Gleason Score 3+3=6, Stage T1c).
    *   Patient opts for LDR brachytherapy monotherapy.
*   **Brachytherapy Procedure:**
    *   Pre-planning: Transrectal Ultrasound (TRUS) volume study performed weeks before the implant to determine prostate size/shape and plan seed placement.
    *   Implant Day: Under anesthesia, TRUS guidance is used to place I-125 seeds interstitially throughout the prostate according to the pre-plan, using needles inserted through a template grid.
    *   Post-implant: CT scan performed within hours/days to assess the actual seed distribution and perform post-implant dosimetry.
*   **Planning Goals:**
    *   **Target:** Prostate gland (CTV = GTV).
        *   Goal: $D_{90}$ (dose covering 90% of prostate) $\ge$ 145 Gy (prescription dose for I-125).
        *   Goal: $V_{100}$ (prostate volume receiving 100% of prescription dose) $\ge$ 95%.
    *   **Organs at Risk (OARs):** Urethra, Rectum, Bladder.
        *   Goals: Urethral $D_{10}$ < 150% of Rx dose; Rectal $V_{100}$ (volume receiving 100% of Rx dose) < 1 cc.
*   **Physics Planning Tasks:**
    *   **Pre-planning (Volume Study):** Contour prostate on TRUS images. Use TPS to determine optimal number, strength ($S_K$), and spatial arrangement of I-125 seeds to achieve dose goals. Generate template coordinates for needle placement.
    *   **Intraoperative:** May involve real-time adjustments based on TRUS visualization.
    *   **Post-implant Dosimetry:** Fuse post-implant CT with planning TRUS (or contour directly on CT). Identify and digitize *all* implanted seeds accurately. Calculate the actual dose distribution based on the final seed positions. Evaluate target coverage ($D_{90}$, $V_{100}$) and OAR doses (Urethral $D_{10}$, Rectal $V_{100}$) against goals.
    *   **QA:** Verify seed strength ($S_K$) before implant. Ensure accurate seed localization in TPS. Perform independent check of post-implant dosimetry.
*   **Potential Challenges:**
    *   Seed migration after placement.
    *   Prostate edema (swelling) post-implant affecting geometry and dose distribution.
    *   Difficulty accurately identifying all seeds on post-implant CT, especially if clustered.
    *   Discrepancies between pre-plan and actual achieved dosimetry.

## Scenario 3: HDR Surface Applicator (Mold) for Skin Cancer

*   **Patient Presentation:**
    *   75-year-old patient with a basal cell carcinoma on the nose (approx. 1.5 cm diameter, < 2 mm depth).
    *   Surgical excision is not preferred due to cosmetic concerns.
    *   HDR brachytherapy using a custom surface mold is chosen.
*   **Brachytherapy Procedure:**
    *   Impression taken of the treatment area.
    *   Custom mold created (e.g., using thermoplastic or 3D printing) with embedded catheters for the HDR source.
    *   CT scan performed with the mold in place on the patient.
*   **Planning Goals:**
    *   **Target:** Lesion area plus a margin (e.g., 5 mm), prescribed to a specific depth (e.g., 3 mm or surface).
        *   Goal: Deliver prescribed dose (e.g., 40 Gy in 8 fractions) to the target volume/surface.
    *   **Organs at Risk (OARs):** Underlying cartilage (if applicable), eyes (if nearby).
        *   Goal: Minimize dose to underlying tissues beyond the target depth.
*   **Physics Planning Tasks:**
    *   **Applicator Reconstruction:** Digitize catheter paths within the mold on the CT scan.
    *   **Contouring:** Define target surface/volume and any relevant OARs.
    *   **Source:** HDR Ir-192 source.
    *   **Optimization:** Optimize dwell times and potentially positions to create a uniform dose distribution across the target surface/depth while ensuring rapid dose fall-off beyond the target.
    *   **Plan Evaluation:** Assess dose homogeneity across the target surface/volume. Check dose at specific points/depths. Evaluate dose to OARs.
    *   **QA:** Verify mold fit and positioning. Check catheter integrity. Perform standard HDR plan and delivery QA.
*   **Potential Challenges:**
    *   Ensuring intimate and reproducible contact between the mold and the curved skin surface.
    *   Accurate CT imaging and reconstruction of catheters relative to the skin surface.
    *   Achieving dose homogeneity over an irregular surface.

## Scenario 4: HDR Interstitial Brachytherapy for Breast Cancer Boost

*   **Patient Presentation:**
    *   50-year-old female status-post lumpectomy for early-stage breast cancer.
    *   Receiving whole breast EBRT (e.g., 42.5 Gy in 16 fractions).
    *   An HDR interstitial brachytherapy boost to the lumpectomy cavity is planned.
*   **Brachytherapy Procedure:**
    *   Multiple flexible catheters are placed interstitially through the lumpectomy bed region under imaging guidance (e.g., US or CT) after EBRT completion.
    *   CT simulation performed with catheters in place.
*   **Planning Goals:**
    *   **Target:** Lumpectomy cavity plus margin (CTV Boost).
        *   Goal: Deliver prescribed boost dose (e.g., 10 Gy in 2 fractions) such that $\ge$ 90-95% of the CTV Boost volume receives the prescription dose ($V_{100}$). Ensure dose homogeneity.
    *   **Organs at Risk (OARs):** Skin, Ribs, Lung, Heart (if left breast).
        *   Goals: Minimize dose to skin ($V_{150}$, $V_{200}$), ribs, lung, and heart.
*   **Physics Planning Tasks:**
    *   **Catheter Reconstruction:** Accurately digitize all catheter paths on the CT simulation.
    *   **Contouring:** Define CTV Boost and OARs.
    *   **Source:** HDR Ir-192 source.
    *   **Optimization:** Use inverse planning (IPSA) or graphical optimization to adjust dwell times to conform the prescription dose to the CTV Boost while minimizing high dose volumes ($V_{150}$, $V_{200}$) within the target and sparing OARs.
    *   **Plan Evaluation:** Analyze DVHs for CTV Boost ($V_{100}$, $V_{150}$, $V_{200}$) and OARs. Check dose homogeneity index. Verify dose distribution visually.
    *   **QA:** Verify catheter placement and integrity. Perform standard HDR plan and delivery QA.
*   **Potential Challenges:**
    *   Achieving optimal catheter geometry to cover the target adequately.
    *   Minimizing air gaps around catheters which can affect dose.
    *   Balancing target coverage with skin dose, especially for superficial cavities.
    *   Accurate contouring of the lumpectomy cavity CTV.


