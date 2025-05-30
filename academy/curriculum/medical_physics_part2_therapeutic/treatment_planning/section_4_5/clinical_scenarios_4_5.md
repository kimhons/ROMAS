# Section 4.5: Clinical Scenarios in SRS/SBRT

*(Note: These scenarios are designed to integrate the physics, clinical, and practical aspects of SRS/SBRT discussed in the core documents for Section 4.5. They incorporate robust details and decision-making points based on reference materials and guidelines.)*

## Scenario 1: Medically Inoperable Early-Stage NSCLC (Peripheral)

*   **Patient Profile:**
    *   76-year-old female with severe COPD (FEV1 35% predicted), history of smoking.
    *   Incidental finding on chest CT: 2.2 cm spiculated nodule in the left lower lobe (LLL), peripheral location.
    *   PET/CT confirms FDG-avidity in the LLL nodule only (SUVmax 8.5), no nodal or distant metastases (cT1bN0M0).
    *   Biopsy confirms adenocarcinoma.
    *   Patient deemed high-risk for surgery by thoracic surgery.
*   **Clinical Challenge:** Provide curative-intent local therapy for early-stage NSCLC in a medically inoperable patient.
*   **Treatment Decision:** SBRT is the standard of care in this situation.
*   **Simulation & Planning:**
    *   **Immobilization:** BodyFIX vacuum bag for reproducibility.
    *   **Imaging:** 4D-CT simulation to assess respiratory motion. Thin-slice (1.5mm) contrast-enhanced CT fused with diagnostic PET/CT.
    *   **Motion Assessment:** 4D-CT reveals 1.2 cm superior-inferior (SI) motion, < 0.5 cm in AP/LR. Correlation with external surrogate (abdominal pressure sensor) is stable.
    *   **Motion Management Strategy:** Respiratory gating selected to minimize treated volume compared to ITV. Gating window set around end-exhale (e.g., 30-40% phase), confirmed via 4D-CT analysis to limit residual motion within the gate to < 3 mm.
    *   **Target Delineation:** GTV contoured on average CT dataset within the gating window. PTV margin = GTV + 5 mm isotropic margin (accounts for residual motion, setup uncertainty).
    *   **Dose Prescription:** 54 Gy in 3 fractions prescribed to the 80% isodose line covering the PTV (high BED regimen suitable for peripheral tumor).
    *   **Planning Technique:** VMAT plan optimized for high conformality and steep dose fall-off.
    *   **OAR Constraints:** Easily met due to peripheral location (chest wall, spinal cord, heart, esophagus, contralateral lung well below tolerance based on TG-101).
*   **Delivery & QA:**
    *   **Machine QA:** Daily checks including Winston-Lutz test confirm sub-millimeter isocenter accuracy (TG-142).
    *   **Patient-Specific QA:** Pre-treatment phantom measurement confirms accurate dose delivery (e.g., Gamma analysis 98% passing at 3%/2mm criteria).
    *   **IGRT:** Daily CBCT for initial setup verification. Intra-fractional kV imaging used to verify target position relative to gating surrogate before each beam delivery.
    *   **Gating Delivery:** Beam automatically held when respiratory signal moves outside the predefined gating window.
*   **Potential Complications & Management:**
    *   **Acute:** Fatigue (common, supportive care), Cough (managed symptomatically), Skin erythema (rare for SBRT, topical creams if needed).
    *   **Late:** Rib fracture (low risk for 3 fx, manage pain if occurs), Chest wall pain (can occur months later, manage with analgesics), Radiation pneumonitis (typically asymptomatic/mild grade 1-2 changes on imaging around PTV, steroids rarely needed for peripheral SBRT).
*   **Follow-up:** Serial CT scans every 3-6 months to assess local control and monitor for regional/distant recurrence. Monitor for late toxicity.

## Scenario 2: Oligometastatic Disease - Liver Metastasis

*   **Patient Profile:**
    *   62-year-old male treated 2 years ago for colorectal cancer (sigmoid colectomy, adjuvant chemo).
    *   Surveillance PET/CT shows a new solitary 3.0 cm FDG-avid lesion in segment VII of the liver (SUVmax 10.2). No other sites of disease.
    *   Good performance status (ECOG 0), normal liver function (Child-Pugh A).
*   **Clinical Challenge:** Treat isolated liver metastasis with curative intent in the context of oligometastatic disease.
*   **Treatment Decision:** Options include surgical resection, thermal ablation (RFA/MWA), or SBRT. Given the location and patient preference for non-invasive therapy, SBRT is chosen after multidisciplinary discussion.
*   **Simulation & Planning:**
    *   **Immobilization:** BodyFIX vacuum bag with abdominal compression belt to reduce respiratory motion.
    *   **Imaging:** 4D-CT simulation with IV contrast (arterial and portal venous phases) to optimize GTV visualization. Diagnostic MRI (liver protocol with diffusion-weighted imaging) fused for improved delineation.
    *   **Motion Assessment:** 4D-CT under compression shows residual SI motion of 0.8 cm.
    *   **Motion Management Strategy:** ITV approach chosen. GTV contoured on all phases of 4D-CT, combined to create ITV. PTV = ITV + 5 mm margin.
    *   **Target Delineation:** GTV contoured using fused MRI and contrast CT. ITV generated. PTV created.
    *   **Dose Prescription:** 50 Gy in 5 fractions prescribed to the 80% isodose line covering the PTV. (5 fractions chosen to better spare normal liver and nearby bowel, given tumor size and ITV approach).
    *   **Planning Technique:** Multi-arc VMAT plan, potentially using non-coplanar beams to improve OAR sparing.
    *   **OAR Constraints:** Critical constraints include:
        *   Normal Liver: Mean dose < 15-18 Gy, Volume receiving > 20 Gy (V20) < 30%. At least 700 cc of normal liver must receive < 15 Gy.
        *   Stomach/Bowel: Max point dose constraints (e.g., Dmax < 30-35 Gy for bowel in 5 fx).
        *   Kidneys, Spinal Cord, Chest Wall (if nearby).
*   **Delivery & QA:**
    *   **Machine QA:** Standard SRS/SBRT QA protocols.
    *   **Patient-Specific QA:** Mandatory pre-treatment verification.
    *   **IGRT:** Daily CBCT aligned to liver anatomy (using vessel bifurcations or contrast if visible) or implanted fiducials if placed. Intra-fractional monitoring considered if significant drift suspected.
*   **Potential Complications & Management:**
    *   **Acute:** Fatigue, Nausea (anti-emetics), Transient elevation of liver enzymes (usually resolves).
    *   **Late:** Radiation-Induced Liver Disease (RILD - low risk with Child-Pugh A and dose constraints met), Biliary stricture (if near porta hepatis), GI toxicity (ulcer, bleeding, perforation - risk depends on proximity and dose), Chest wall pain/rib fracture (if superior lesion).
*   **Follow-up:** Serial MRI or contrast CT scans every 3 months. Monitor liver function tests. Assess for new metastatic disease.

## Scenario 3: Spine Metastasis with Cord Proximity

*   **Patient Profile:**
    *   55-year-old female with history of breast cancer, presenting with new severe mid-back pain.
    *   MRI shows a 2.0 cm lytic lesion in the T8 vertebral body with posterior extension into the epidural space, abutting but not compressing the spinal cord.
    *   PET/CT confirms this is the only site of active disease.
    *   Neurologically intact.
*   **Clinical Challenge:** Provide rapid pain relief and durable local control while protecting the spinal cord from high-dose radiation.
*   **Treatment Decision:** Spine SBRT is an excellent option for durable pain control and local control, potentially delaying or avoiding cord compression.
*   **Simulation & Planning:**
    *   **Immobilization:** Rigid body frame with vacuum bag, ensuring minimal rotation and flexion/extension.
    *   **Imaging:** Thin-slice (1mm) CT simulation fused with high-resolution contrast-enhanced MRI (T1, T2, STIR sequences) for precise delineation of GTV, vertebral body, epidural space, and spinal cord.
    *   **Motion Assessment:** Minimal motion expected at thoracic spine level, confirmed during simulation.
    *   **Target Delineation:** GTV includes enhancing lesion. CTV often includes the entire involved vertebral body segment(s) based on risk pathways (institutional variation). PTV margin is very tight (e.g., GTV/CTV + 1-2 mm) due to cord proximity.
        *   **Spinal Cord Contouring:** Thecal sac contoured as surrogate, often with a Planning Risk Volume (PRV) margin (e.g., 1-2 mm) to account for uncertainties.
    *   **Dose Prescription:** 24 Gy in 2 fractions prescribed to the PTV periphery (e.g., 90% isodose). (Multi-fraction regimen chosen to further mitigate cord risk compared to single fraction).
    *   **Planning Technique:** Highly conformal VMAT or IMRT, often using non-coplanar beams and very tight MLC margins around the cord PRV.
    *   **OAR Constraints (Critical):**
        *   Spinal Cord PRV: Maximum point dose strictly limited (e.g., Dmax < 17 Gy in 2 fx, check institutional/RTOG protocols for specific limits based on total dose/fractionation). Volume constraints (e.g., V14Gy < 0.1 cc) also critical.
        *   Esophagus, Lungs, Kidneys (depending on level).
*   **Delivery & QA:**
    *   **Machine QA:** Sub-millimeter isocenter accuracy verified daily (Winston-Lutz).
    *   **Patient-Specific QA:** Mandatory, often with high-resolution film or detector array, potentially tighter tolerances (e.g., 2%/1mm or 2%/2mm).
    *   **IGRT:** Daily CBCT aligned to bony anatomy of the involved and adjacent vertebrae. Verification must be extremely precise. Intra-fractional checks may be warranted.
*   **Potential Complications & Management:**
    *   **Acute:** Transient pain flare (common, manage with steroids/analgesics), Fatigue, Esophagitis (if esophagus nearby).
    *   **Late:** Vertebral Compression Fracture (VCF - risk increased if >50% body involvement or lytic disease, consider prophylactic vertebroplasty in some cases), Radiation Myelopathy (rare but devastating, strict adherence to dose limits is preventative).
*   **Follow-up:** Clinical assessment for pain relief. Serial MRI scans to assess local control and monitor for cord changes or VCF.



## Scenario 4: Post-Operative Brain Metastasis Cavity SRS

*   **Patient Profile:**
    *   60-year-old male with history of melanoma, presented with seizures.
    *   MRI revealed a single 3.5 cm hemorrhagic metastasis in the right parietal lobe with significant surrounding edema and mass effect.
    *   Patient underwent gross total resection of the metastasis.
    *   Post-operative MRI confirms resection cavity, minimal residual enhancement questionable for tumor vs. post-op changes.
    *   Staging scans negative for other metastatic disease.
*   **Clinical Challenge:** Reduce the risk of local recurrence in the surgical cavity while avoiding WBRT to preserve neurocognitive function.
*   **Treatment Decision:** Post-operative SRS to the resection cavity is chosen over observation or WBRT.
*   **Simulation & Planning:**
    *   **Timing:** Typically performed 2-4 weeks post-surgery to allow for cavity stabilization and resolution of acute post-operative changes.
    *   **Imaging:** High-resolution post-operative contrast-enhanced MRI (T1 post-Gd, FLAIR/T2 for edema/cavity) fused with thin-slice CT simulation scan.
    *   **Immobilization:** Frameless mask system.
    *   **Target Delineation (Controversial Area):**
        *   *Option 1 (Common):* CTV = Surgical cavity (visualized on T2/FLAIR) + 1-2 mm margin. Some centers may include subtle marginal enhancement if present.
        *   *Option 2:* CTV = Surgical cavity only.
        *   *Decision:* Based on institutional protocol and discussion, CTV defined as cavity + 1 mm margin.
        *   PTV = CTV + 1-2 mm margin.
    *   **Dose Prescription:** 30 Gy in 5 fractions prescribed to the PTV (e.g., 95% of PTV covered by 30 Gy). Fractionation preferred over single fraction for larger cavities/uncertain margins to reduce radionecrosis risk.
    *   **Planning Technique:** VMAT optimized for PTV coverage and sparing adjacent normal brain.
    *   **OAR Constraints:** Standard brain OARs (brainstem, optic pathway, normal brain V12Gy etc.).
*   **Delivery & QA:**
    *   **Machine QA:** Standard SRS protocols.
    *   **Patient-Specific QA:** Mandatory.
    *   **IGRT:** Daily CBCT aligned to skull anatomy, potentially using cavity shape if clearly defined and stable.
*   **Potential Complications & Management:**
    *   **Acute:** Fatigue, headache, potential worsening of edema (may require short course of steroids).
    *   **Late:** Radionecrosis (risk increased with larger cavity size and dose/fractionation), neurocognitive effects (generally less than WBRT), leptomeningeal disease (potential failure pattern).
*   **Follow-up:** Serial MRI scans every 3 months initially to monitor for recurrence (often marginal) vs. radionecrosis.
*   **Street Wisdom:** Contouring the post-op cavity CTV is challenging and lacks universal consensus. Fractionation is generally safer than single-fraction SRS for cavities, especially if > 2.5-3 cm diameter. Radionecrosis remains a significant risk.

## Scenario 5: Prostate SBRT with Rectal Spacer

*   **Patient Profile:**
    *   68-year-old male diagnosed with Gleason 3+4=7 (Grade Group 2) prostate cancer, PSA 6.5 ng/mL, cT1c.
    *   Healthy, active, seeking curative treatment with minimal disruption.
    *   MRI shows prostate volume 45 cc, no extraprostatic extension or seminal vesicle invasion.
*   **Clinical Challenge:** Deliver curative-intent radiation with maximal rectal sparing to minimize toxicity, using an ultra-hypofractionated SBRT regimen.
*   **Treatment Decision:** Patient opts for SBRT after discussion of options (conventional RT, brachytherapy, active surveillance, surgery). Hydrogel rectal spacer placement is planned to optimize rectal sparing.
*   **Simulation & Planning:**
    *   **Procedures:** Gold fiducial markers placed in prostate. Hydrogel spacer (e.g., SpaceOAR) injected between prostate and rectum under transrectal ultrasound guidance (confirms >1 cm separation achieved).
    *   **Imaging:** CT simulation performed ~1 week after spacer placement (allows stabilization) fused with planning MRI (T2 weighted).
    *   **Immobilization:** Pelvic cradle, strict bladder filling (e.g., void then drink 500ml water 1 hr prior) and rectal emptying protocol.
    *   **Target Delineation:** CTV = Prostate gland. PTV = CTV + 4 mm isotropic margin (reduced to 3 mm posteriorly due to spacer and fiducial tracking).
    *   **Dose Prescription:** 40 Gy in 5 fractions (8 Gy/fx) prescribed to the PTV.
    *   **Planning Technique:** VMAT plan optimized to cover PTV while maximally sparing rectum, bladder, femoral heads.
    *   **OAR Constraints (Leveraging Spacer):** Aim for significantly lower rectal doses than without spacer (e.g., Rectum V36Gy < 0.1cc, V32Gy < 1cc, V18Gy < 10%). Bladder constraints also applied (e.g., V37Gy < 10cc).
*   **Delivery & QA:**
    *   **Machine QA:** Standard SRS/SBRT protocols.
    *   **Patient-Specific QA:** Mandatory.
    *   **IGRT:** Daily kV imaging targeting fiducial markers is essential. Corrections applied before each fraction. Intra-fractional monitoring (e.g., periodic kV or CBCT) used to check for drift.
*   **Potential Complications & Management:**
    *   **Acute:** Urinary frequency/urgency (common, managed with alpha-blockers), mild rectal discomfort (less common with spacer). Spacer-related: temporary discomfort, rare risk of infection/migration.
    *   **Late:** Rectal toxicity (proctitis, bleeding) significantly reduced with spacer. Urinary toxicity (stricture, incontinence) rare. Erectile dysfunction risk similar to other RT modalities.
*   **Follow-up:** PSA checks every 3-6 months. Monitor for late urinary/rectal symptoms.
*   **Street Wisdom:** Rectal spacers make achieving stringent rectal dose constraints much easier in prostate SBRT, reducing toxicity risk. Accurate fiducial tracking is non-negotiable. Consistent bladder/rectal preparation is important for reproducibility.

## Scenario 6: Re-irradiation Spine SBRT

*   **Patient Profile:**
    *   65-year-old male with history of metastatic prostate cancer, previously treated 3 years ago with conventional palliative RT (30 Gy in 10 fractions) to T10-L2 for painful bony metastases.
    *   Now presents with progressive, localized pain at T11, refractory to analgesics.
    *   MRI shows progressive metastatic lesion confined to the T11 vertebral body, stable epidural space, but abutting the previously irradiated spinal cord.
    *   Good performance status (ECOG 1).
*   **Clinical Challenge:** Provide effective pain palliation via re-irradiation while minimizing the high risk of radiation myelopathy given the prior treatment.
*   **Treatment Decision:** Re-irradiation SBRT considered due to potential for durable pain relief and local control, but requires extreme caution and detailed risk discussion with the patient.
*   **Simulation & Planning:**
    *   **Prior Dose Record Retrieval:** Essential to obtain detailed records of the previous RT plan (dose distribution, fractionation, dates).
    *   **Imaging:** Thin-slice CT simulation fused with current high-resolution MRI (T1 post-Gd, T2). Prior RT plan DICOM data imported into TPS.
    *   **Immobilization:** Rigid body frame with vacuum bag.
    *   **Dose Summation & Cord Tolerance:**
        *   *Deformable Image Registration:* Used to register the prior CT/dose distribution to the current simulation CT.
        *   *Dose Accumulation:* Sum the previously delivered dose (converted to BED or EQD2 using appropriate alpha/beta ratio, e.g., 2 Gy for cord) with the planned SBRT dose.
        *   *Cumulative Cord Limit:* The maximum cumulative cord dose (EQD2) is the critical limiting factor. Tolerance for re-irradiation is lower and less certain than for primary treatment (e.g., cumulative EQD2 max point dose often limited to ~50-60 Gy, but highly debated and institution-dependent). Requires careful review of literature (e.g., Nieder et al.) and institutional guidelines.
    *   **Target Delineation:** GTV = Progressive lesion at T11. CTV = GTV + minimal margin or involved vertebral body compartment. PTV = CTV + 1-2 mm margin.
    *   **Dose Prescription:** Dose and fractionation chosen to provide palliation while respecting cumulative cord limit. Often requires significant dose de-escalation or fractionation compared to de novo SBRT (e.g., 25-30 Gy in 5 fractions, potentially lower).
    *   **Planning Technique:** Highly conformal technique (VMAT/IMRT) with extreme focus on minimizing dose overlap onto the cord from the SBRT component. May require compromising PTV coverage near the cord.
*   **Delivery & QA:**
    *   **Machine QA:** Rigorous sub-millimeter accuracy checks.
    *   **Patient-Specific QA:** Mandatory, potentially with tighter tolerances and careful verification near the cord avoidance region.
    *   **IGRT:** Daily high-precision CBCT alignment is critical.
*   **Potential Complications & Management:**
    *   **Acute:** Pain flare (high likelihood, premedicate/manage with steroids), Fatigue.
    *   **Late:** Radiation Myelopathy (primary concern, risk minimized by strict adherence to cumulative dose limits, but risk remains elevated), VCF.
*   **Follow-up:** Close clinical monitoring for pain relief and neurological status. Serial MRI to assess response and monitor cord signal changes.
*   **Street Wisdom:** Re-irradiation SBRT is high-risk, high-reward. It requires meticulous planning, accurate dose summation (using deformable registration), conservative cord constraints based on cumulative dose, and extensive patient counseling regarding the risk of myelopathy.

