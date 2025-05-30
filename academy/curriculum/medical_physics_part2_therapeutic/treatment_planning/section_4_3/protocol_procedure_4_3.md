# Section 4.3: Sample Protocol - IGRT for Prostate SBRT using Fiducial Markers and CBCT

**Title:** Image-Guided Radiotherapy (IGRT) Protocol for Prostate SBRT using Implanted Fiducial Markers and Cone-Beam CT (CBCT)

**Purpose:** To define the standard procedure for patient setup, target localization, and intra-fraction motion monitoring using implanted fiducial markers and CBCT for patients undergoing Stereotactic Body Radiation Therapy (SBRT) for prostate cancer.

**Scope:** This protocol applies to all patients receiving prostate SBRT who have had fiducial markers implanted and are treated on Linacs equipped with kV CBCT systems.

**References:**
- AAPM TG-101: Stereotactic Body Radiation Therapy
- AAPM TG-132: Use of Image Registration and Fusion Algorithms and Techniques in Radiotherapy
- AAPM TG-142: Quality assurance of medical accelerators
- Institutional policies on SBRT and IGRT.

**Personnel:** Qualified Radiation Therapists (RTTs), Medical Physicists, Radiation Oncologists.

**Equipment:**
- Linear Accelerator with kV CBCT capability
- Treatment Planning System (TPS) with fiducial visualization and registration tools
- Record & Verify (R&V) System
- Patient immobilization system (e.g., vacuum bag, leg shuttle)
- Fiducial markers (implanted prior to simulation)

**Procedure:**

**1. Pre-Treatment Simulation & Planning:**
   1.1. **Fiducial Implantation:** Performed by urologist/radiation oncologist prior to simulation.
   1.2. **Simulation:**
       - Patient immobilized in treatment position.
       - Adherence to institutional bladder/rectal preparation protocol verified.
       - CT simulation scan acquired with appropriate slice thickness (e.g., <= 2.5 mm).
       - Fiducial markers clearly visualized and identified on planning CT.
   1.3. **Planning:**
       - Target volumes (GTV, CTV, PTV) and OARs delineated.
       - Fiducial markers contoured/identified in TPS.
       - Treatment plan optimized according to prescription and constraints.
       - Digitally Reconstructed Radiographs (DRRs) generated.
       - Plan approved by Radiation Oncologist and Physicist.
       - Plan data, including fiducial locations relative to isocenter, transferred to R&V system.

**2. Daily Treatment Setup and Localization:**
   2.1. **Patient Preparation:** Patient follows institutional bladder/rectal preparation protocol.
   2.2. **Initial Setup:**
       - Patient positioned on treatment couch using immobilization device.
       - Initial alignment performed using external lasers/tattoos to setup marks.
   2.3. **Pre-Treatment CBCT Acquisition:**
       - Acquire kV CBCT scan using site-specific protocol (e.g., Prostate SBRT protocol).
       - Ensure patient remains still during acquisition.
   2.4. **Image Registration:**
       - Transfer CBCT to IGRT workstation/TPS.
       - Perform **automatic 3D-3D rigid registration** of the CBCT to the planning CT, **based on fiducial markers**. (Primary registration method).
       - *Verification Step 1:* Visually inspect the fiducial marker alignment on fused images/orthogonal views. Ensure all markers are well-aligned.
       - *Verification Step 2:* Perform a secondary registration based on bony anatomy (e.g., pelvis). Note the difference in shifts between fiducial and bony registration.
       - **Action:** If fiducial alignment is satisfactory and consistent, proceed. If alignment is poor or inconsistent (e.g., markers migrated, significant deformation), consult physicist/oncologist immediately.
       - **Action:** If there is a significant discrepancy (> 3-5 mm, per institutional policy) between fiducial and bony shifts, prioritize the fiducial match but investigate the cause (e.g., rectal filling change, bladder filling change, patient rotation not captured by bony match). Document the discrepancy.
   2.5. **Shift Application:**
       - Obtain required couch shifts (X, Y, Z, Pitch, Roll, Yaw - if 6D couch available) from the **fiducial marker registration**.
       - Verify shifts are within institutional tolerances.
       - Apply shifts remotely via R&V system.
   2.6. **Pre-Beam Confirmation (Optional but Recommended):**
       - Acquire orthogonal kV or MV images to confirm final marker position relative to isocenter/field aperture, especially if large shifts were applied or if concerns exist.

**3. Treatment Delivery:**
   3.1. Deliver treatment beams as per the approved plan.
   3.2. Monitor patient for movement during delivery via CCTV.

**4. Intra-Fraction Motion Monitoring (As per institutional policy/plan):**
   4.1. **Rationale:** To detect significant target drift during potentially longer SBRT fraction times.
   4.2. **Method (Examples):**
       - **Mid-Treatment CBCT:** Acquire a CBCT part-way through delivery (e.g., after first arc/group of beams). Register to planning CT or initial CBCT using fiducials. Apply corrections if shifts exceed tolerance (e.g., > 2-3 mm).
       - **Triggered kV Imaging:** If system allows, acquire kV images triggered at specific gantry angles or time intervals. Perform 2D fiducial match and apply corrections if shifts exceed tolerance.
   4.3. **Tolerance:** Define institutional action level for intra-fraction motion (e.g., 3 mm vector shift).
   4.4. **Action:** If intra-fraction motion exceeds tolerance, interrupt treatment, re-localize using CBCT/kV imaging, apply corrections, and resume treatment. Document all interruptions and corrections.

**5. Post-Treatment:**
   5.1. Assist patient off the treatment couch.
   5.2. Complete treatment record in R&V system, documenting all IGRT shifts, registration methods used, verification steps, and any deviations or actions taken.

**6. Quality Assurance (QA):**
   6.1. **Daily:** CBCT image quality checks (e.g., Catphan phantom), laser alignment, imaging/treatment isocenter coincidence (Winston-Lutz or equivalent).
   6.2. **Monthly/Annually:** Comprehensive TG-142 QA including CBCT geometric accuracy, registration software accuracy (using phantoms with known shifts/rotations), couch movement accuracy.
   6.3. **Registration Software QA (TG-132):** Commissioning tests and periodic verification of registration algorithm accuracy for fiducial matching.

**Contingencies:**
- **Poor CBCT Image Quality:** Repeat scan if possible; if persistent, consult physicist. May require alternative localization (e.g., orthogonal kV if markers visible).
- **Fiducial Migration/Loss:** If markers cannot be reliably identified or appear to have migrated significantly, consult physicist/oncologist. May require re-simulation or alternative IGRT strategy.
- **Patient Unable to Tolerate Immobilization/Hold Still:** Consult oncologist. May require modification of treatment plan or technique.

**Approval:**
- Lead Physicist: [Signature/Date]
- Lead Radiation Oncologist: [Signature/Date]
- Lead Radiation Therapist: [Signature/Date]

**Review Cycle:** Annually or as needed based on technology/policy changes.

