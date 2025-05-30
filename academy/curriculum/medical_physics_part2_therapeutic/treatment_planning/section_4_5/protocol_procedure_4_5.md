# Section 4.5: Generic SRS/SBRT Protocol/Procedure Outline

*(Disclaimer: This is a generic outline and must be adapted based on specific treatment site, institutional resources, available technology, and established clinical protocols. It emphasizes key steps and quality checks inherent to SRS/SBRT.)*

**1. Patient Consultation and Selection**
    *   1.1. Multidisciplinary review (Rad Onc, Physics, Surgery, Med Onc, Radiology).
    *   1.2. Confirmation of indication and appropriateness for SRS/SBRT.
    *   1.3. Assessment of patient fitness, comorbidities, prior treatments.
    *   1.4. Detailed discussion with patient regarding goals, procedure, risks, benefits, alternatives.
    *   1.5. Informed consent obtained.

**2. Pre-Treatment Procedures (If Applicable)**
    *   2.1. Fiducial marker placement (e.g., prostate, pancreas, liver) - procedure, imaging confirmation, documentation.
    *   2.2. Pre-medication orders (e.g., steroids for brain SRS, anti-emetics).

**3. Immobilization and Simulation**
    *   3.1. **Device Selection:** Choose appropriate immobilization based on site (e.g., cranial frame/mask, body frame + vacuum bag).
    *   3.2. **Device Creation:** Create custom mask, mold, or vacuum bag according to institutional procedure.
    *   3.3. **Patient Positioning:** Position patient in the immobilization device on the simulator couch, ensuring comfort and reproducibility. Document setup parameters.
    *   3.4. **Motion Assessment Setup (If Applicable):** Place respiratory monitoring surrogates (external markers, pressure sensor) if motion management is anticipated.
    *   3.5. **Imaging Acquisition:**
        *   Acquire high-resolution CT scan with appropriate slice thickness (e.g., ≤ 1.5 mm for SRS, ≤ 3 mm for SBRT).
        *   Acquire 4D-CT if motion management is needed (lung, liver, upper abdomen).
        *   Administer IV contrast per protocol if required for target/OAR visualization.
        *   Acquire planning MRI (and/or PET) if required by protocol, ensuring compatibility for fusion.
    *   3.6. **Image Transfer:** Transfer all image sets to the Treatment Planning System (TPS).
    *   3.7. **Documentation:** Record all simulation parameters, device settings, patient position, and any deviations.

**4. Image Fusion and Contouring**
    *   4.1. **Image Registration (Fusion):** Fuse MRI/PET images with planning CT using approved registration algorithms (rigid/deformable). Verify fusion accuracy (physician/physicist approval, TG-132 principles).
    *   4.2. **Contouring (Physician):**
        *   Delineate Gross Tumor Volume (GTV) based on all available imaging.
        *   Delineate Clinical Target Volume (CTV) if applicable (often GTV=CTV for SRS/SBRT).
        *   Delineate Organs at Risk (OARs), including critical structures (e.g., spinal cord, brainstem, optic structures, bowel, heart).
        *   Delineate motion-inclusive volumes (e.g., ITV) if using that strategy, based on 4D-CT.
    *   4.3. **Contouring (Physics/Dosimetry):**
        *   Generate Planning Target Volume (PTV) by adding appropriate margin to GTV/CTV/ITV based on institutional protocols and characterized uncertainties.
        *   Generate Planning Risk Volumes (PRVs) for critical structures (e.g., Cord PRV) if required by protocol.
        *   Contour other structures needed for planning/evaluation (e.g., body outline, lungs).
    *   4.4. **Contour Review:** Physician approval of all contours.

**5. Treatment Planning**
    *   5.1. **Prescription:** Define dose per fraction, number of fractions, target coverage goals (e.g., PTV D95% = Rx Dose), and critical OAR constraints (based on site, fractionation, institutional/national protocols like TG-101).
    *   5.2. **Planning Technique Selection:** Choose appropriate delivery technique (e.g., 3D conformal arcs, VMAT, IMRT, static beams for GK/CK).
    *   5.3. **Beam Arrangement/Optimization:** Optimize beam angles, energies (FFF vs FF), collimation, and fluence patterns to achieve prescription goals while minimizing OAR dose.
    *   5.4. **Dose Calculation:** Use appropriate high-accuracy algorithm (e.g., Monte Carlo, Acuros/CCC) with adequate grid resolution (e.g., ≤ 2 mm).
    *   5.5. **Plan Evaluation:** Evaluate dose-volume histograms (DVHs), isodose distributions, conformity indices, gradient indices, and adherence to all target coverage goals and OAR constraints.
    *   5.6. **Plan Review and Approval:** Review by physicist and physician. Document approval.

**6. Pre-Treatment Quality Assurance (Physics)**
    *   6.1. **Independent Dose Calculation:** Perform secondary check of monitor units or absolute dose using independent software or method.
    *   6.2. **Patient-Specific Plan QA:**
        *   Deliver the approved plan to a suitable phantom (e.g., detector array, film in phantom).
        *   Measure the delivered dose distribution.
        *   Compare measured dose to planned dose using gamma analysis with appropriate criteria (e.g., 2%/2mm, 2%/1mm, or 3%/1mm depending on site/protocol).
        *   Investigate and resolve any discrepancies exceeding tolerance before treatment.
    *   6.3. **Machine QA:** Ensure all daily/weekly SRS/SBRT-specific machine QA (e.g., Winston-Lutz, output checks, imaging system checks) is completed and within tolerance on the day of treatment.

**7. Treatment Delivery (Therapist/Physics/Physician)**
    *   7.1. **Patient Setup:** Position patient on treatment couch using immobilization device and setup instructions from simulation. Align to external lasers/marks.
    *   7.2. **Image-Guided Localization (IGRT):**
        *   Acquire pre-treatment localization images (e.g., CBCT, kV orthogonal pair, ExacTrac).
        *   Register IGRT images to planning CT/DRRs using appropriate anatomy (bone, fiducials, soft tissue).
        *   Calculate required positional shifts (translational and rotational).
        *   Apply shifts using remote couch controls.
        *   **Verification:** Acquire verification image/perform check to confirm correct shifts were applied.
        *   Physician/physicist approval of final position before treatment.
    *   7.3. **Motion Management Application (If Applicable):**
        *   Activate gating system, verify respiratory signal and gate window.
        *   Instruct patient on breath-hold technique, verify reproducibility.
        *   Ensure tracking system is active and locked onto target/fiducials.
    *   7.4. **Beam Delivery:** Deliver treatment beams according to the approved plan. Monitor patient via CCTV and audio. Monitor motion management system function (gating duty cycle, tracking accuracy).
    *   7.5. **Intra-Fractional IGRT (If Applicable):** Acquire additional localization images during treatment delivery (e.g., between arcs/fields, or continuous tracking) if required by protocol or if significant motion is suspected. Apply corrections if necessary.
    *   7.6. **Treatment Completion:** Record delivered dose, treatment time, any deviations or interruptions.
    *   7.7. **Patient Release:** Assist patient off table, provide post-treatment instructions.

**8. Post-Treatment**
    *   8.1. **Documentation:** Complete all treatment records, QA checklists, and billing information.
    *   8.2. **Follow-Up Scheduling:** Ensure patient has appropriate clinical and imaging follow-up scheduled per protocol.
    *   8.3. **Physics Review:** Review treatment delivery records, IGRT shifts, and any issues encountered.

**9. Ongoing QA and Process Improvement**
    *   9.1. Regular review of SRS/SBRT procedures, protocols, and outcomes.
    *   9.2. Participation in incident learning systems.
    *   9.3. Regular end-to-end testing of the entire SRS/SBRT process.
    *   9.4. Staff training and competency assessment.

