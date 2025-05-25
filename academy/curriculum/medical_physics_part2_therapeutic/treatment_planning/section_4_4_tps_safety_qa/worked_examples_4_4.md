# Section 4.4: Worked Examples for Activities - Treatment Planning System Safety and QA

**Note:** These are illustrative examples. Specific details, measurements, and criteria would vary based on institutional equipment, software, and policies.

## Worked Example for Activity 1: TPS Commissioning Test Design (Lung SBRT)

**1. Clinical Scenario:** Lung SBRT, specifically validating dose calculation accuracy in a low-density medium near a small, high-density target, simulating a tumor surrounded by lung tissue.

**2. Phantom Setup:**
   - **Phantom:** Anthropomorphic thorax phantom (e.g., CIRS Model 008A) containing lung-equivalent material, bone-equivalent structures, and inserts for detectors. A small, high-density insert (e.g., 1-2 cm diameter, GTV density) would be placed within the lung volume.
   - **Detector:** High-resolution film (e.g., Gafchromic EBT3) placed in the coronal or sagittal plane bisecting the target insert. Alternatively, a small volume ion chamber (e.g., microchamber) could be placed within the target insert or at specific points nearby if the phantom allows.
   - **Setup:** Phantom positioned on CT couch, scanned using the clinical SBRT protocol. Phantom then set up on Linac using the same immobilization and alignment marks.

**3. TPS Modeling:**
   - Import the phantom CT scan into the TPS.
   - Contour the external phantom, lung material, bone structures, and the high-density target insert.
   - Assign correct electron densities to each structure based on the validated CT-density curve.
   - Create a simple SBRT plan targeting the insert (e.g., 3-4 non-opposed coplanar or non-coplanar static fields, or a single VMAT arc).
   - Calculate dose using the algorithm being commissioned (e.g., CCCS) with a fine grid resolution (e.g., 2 mm).

**4. Key Comparisons:**
   - **Point Doses:** Compare calculated point doses with ion chamber measurements (if used) at the center of the target, edge of the target, and in the lung tissue immediately adjacent to the target.
   - **Profile Comparison:** Extract dose profiles from the calculated dose distribution (e.g., in-plane and cross-plane through the target center) and compare them to profiles measured from the film dosimetry.
   - **Gamma Analysis:** Perform 2D gamma analysis comparing the calculated dose plane to the measured film dose plane. Use tight criteria appropriate for commissioning, e.g., 2%/2mm (local normalization, 10% threshold).

**5. Acceptance Criterion:**
   - **Point Doses:** Agreement within +/- 2% in the high-dose target region, +/- 3% in the adjacent lung (allowing for challenges in low-density regions).
   - **Gamma Analysis:** Passing rate > 95% for 2%/2mm criteria.
   - **Justification:** Lung SBRT requires high accuracy due to steep gradients and heterogeneity. These criteria (tighter than typical IMRT QA) ensure the algorithm accurately models dose deposition in challenging low-density/high-gradient situations, aligning with TG-101 principles for SBRT accuracy.

## Worked Example for Activity 2: Basic FMEA for Plan Export

**Step:** Exporting the approved plan from the TPS to the Record & Verify (R&V) system.

**1. Potential Failure Modes:**
   a) Data corruption during network transfer.
   b) Incorrect patient selected in R&V system during import/association.
   c) Incorrect plan version/status exported from TPS (e.g., an unapproved plan).

**2. FMEA Analysis (Failure Mode b: Incorrect patient selected in R&V):**
   a) **Effect(s):** Catastrophic. The wrong patient could receive radiation intended for someone else, or the correct patient could receive a plan intended for another, leading to severe overdose/underdose and potential harm or death.
   b) **Cause(s):** Human error (therapist/physicist selects wrong patient from list), similar patient names, inadequate patient identification checks in R&V interface, workflow interruption.
   c) **Hypothetical Scores:**
      - **Severity (S): 10** (Catastrophic patient harm/death)
      - **Occurrence (O): 3** (Assumes some checks exist, but human error is possible, especially with similar names or high workload; might occur rarely)
      - **Detectability (D): 4** (May be detected by pre-treatment checks like image comparison or chart rounds, but detection is not guaranteed if initial checks fail or are bypassed)
   d) **RPN:** S x O x D = 10 x 3 x 4 = **120** (This RPN value suggests a moderate-to-high risk requiring attention, primarily driven by the extreme severity).
   e) **Mitigation Strategy:** Implement a mandatory two-person verification check (e.g., therapist + second therapist or physicist) of patient name, ID number, and plan details within the R&V system immediately after import and before any treatment fields are enabled. Enhance R&V system interface to require explicit confirmation of patient identifiers and display prominent patient photos. Implement barcode scanning for patient identification at the console linked to the R&V selection.

## Worked Example for Activity 3: Interpreting IMRT QA Results

**Scenario:** Prostate VMAT, ArcCHECK, 3%/3mm (Global), 10% threshold, Result = 92.5% passing, failures in low-gradient region anterior to PTV.

**1. Meets Action Levels?** No. A common institutional action level for 3%/3mm (global) is often >=95%. A result of 92.5% falls below this typical threshold and warrants investigation.

**2. Clinical Significance:** Likely **low** clinical significance. Failing points clustered in a *low-dose gradient region* outside the PTV suggest that the dose discrepancies are occurring where the dose is changing slowly and is already relatively low. Small errors here are less likely to impact target coverage or significantly overdose nearby critical structures compared to failures in high-dose, high-gradient regions near the target edge or OARs.

**3. Further Investigation:**
   - **Verify QA Setup:** Double-check phantom setup, detector array calibration, and ensure the correct plan was delivered to the phantom.
   - **Review Analysis:** Examine the gamma map, dose profiles, and individual failing points in the analysis software. Confirm the location (low gradient) and magnitude of the discrepancies.
   - **Check TPS Calculation:** Review the plan calculation in the TPS, focusing on the anterior region. Check for any unusual optimization artifacts or grid size issues.
   - **Review Delivery:** Check Linac logs for any anomalies during the QA delivery (though less likely if failures are systematic in one region).
   - **Repeat QA:** If setup error is suspected, repeat the measurement carefully.

**4. Action (If QA Setup Error):** If the discrepancy is confirmed to be due to a minor, correctable QA setup error (e.g., phantom slightly shifted, array not perfectly centered), and a repeat measurement passes (>95%), the patient plan can likely proceed to treatment after documenting the investigation and resolution.

**5. Action (If TPS Beam Model Issue):** If the investigation suggests a systematic inaccuracy in the TPS beam model for low-dose peripheral regions (less common but possible), this requires more significant action. The specific beam model parameter might need adjustment and re-validation (potentially requiring physicist consultation with the vendor). Treating the patient should be **halted** until the issue is understood and resolved, or the plan is modified/recalculated in a way that avoids the problematic region or uses settings known to be accurate. The issue should be documented and addressed as part of the ongoing TPS QA program.

## Worked Example for Activity 4: Designing a Routine TPS QA Check (CT-Density Curve)

**1. Function:** CT Number to Electron Density (or Physical Density) curve stability.

**2. Test Procedure (Monthly):**
   a) Obtain a standard CT scan of the electron density phantom used for commissioning (e.g., CIRS 062M, Gammex 467) acquired using the clinical protocol.
   b) Import this CT scan into the TPS.
   c) Using TPS tools, measure the average CT number (HU) within ROI placed in the center of each known density plug (e.g., lung inhale, lung exhale, adipose, breast, water, muscle, liver, bone densities).
   d) Record the measured HU values for each plug.
   e) Compare the measured HU values to the baseline values established during the last CT-density curve validation/commissioning.
   f) Verify that the currently active CT-density curve in the TPS is the correct one for the scanner used.

**3. Expected Result/Baseline:** The measured HU values for each density plug should match the baseline values established during commissioning or the last validation.

**4. Action Levels/Tolerances:**
   - **Tolerance:** +/- 20 HU deviation from baseline for any individual plug.
   - **Action Level 1:** If any plug deviates by > 20 HU but < 40 HU, investigate potential causes (e.g., CT scanner drift, phantom positioning). Re-scan phantom and repeat check. Inform CT QA team.
   - **Action Level 2:** If any plug deviates by >= 40 HU, or if multiple plugs deviate significantly, halt clinical planning using that CT scanner protocol. Perform a full re-validation of the CT-density curve, potentially requiring re-measurement and update in the TPS. Re-commissioning tests related to heterogeneity corrections may be required.

**5. Documentation:** Record the date, phantom used, CT scan ID, measured HU values for each plug, comparison to baseline, confirmation of active curve, pass/fail status, and any actions taken in the monthly TPS QA log.

