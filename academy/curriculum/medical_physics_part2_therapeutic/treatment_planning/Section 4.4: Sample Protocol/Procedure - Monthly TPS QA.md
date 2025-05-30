# Section 4.4: Sample Protocol/Procedure - Monthly TPS QA

**Title:** Monthly Quality Assurance for Treatment Planning System (TPS)

**Policy:** A set of quality assurance checks shall be performed monthly on the clinical Treatment Planning System(s) to ensure continued accuracy, stability, and safety, consistent with AAPM TG-53 recommendations and institutional risk assessments (TG-100).

**Responsibility:** Qualified Medical Physicist or designee under physicist supervision.

**Frequency:** Monthly (+/- 1 week)

**Equipment:**
- TPS Workstation(s)
- Standardized Digital Phantom Datasets (e.g., CT scan of geometric phantom, CT scan of electron density phantom)
- Baseline QA Plan files
- Monthly TPS QA Log Sheet (Digital or Physical)

**Procedure:**

**1. System and Data Integrity Checks:**
   a.  **Log Review:** Review system logs (if available) for any critical errors or warnings since the last check.
   b.  **Disk Space:** Verify adequate free disk space on server/workstations for operation and data storage (>20% free recommended).
   c.  **Backup Verification:** Confirm that automated system backups completed successfully since the last check (verify logs or perform test restore if indicated by policy).
   d.  **Antivirus Status:** Ensure antivirus software is up-to-date and functioning.
   e.  **User Accounts:** Review active user accounts; disable any unauthorized or unused accounts.

**2. Input Device Checks:**
   a.  **Digitizer/Scanner (if used):** Digitize a test pattern of known dimensions. Verify scaling and spatial accuracy in TPS (+/- 1 mm).
   b.  **Keyboard/Mouse:** Verify proper function.

**3. Output Device Checks:**
   a.  **Monitor Display:** Display standard grayscale and color test patterns (e.g., SMPTE pattern). Verify contrast, brightness, and geometric linearity. Check for dead pixels.
   b.  **Hardcopy Output (Printer/Plotter):** Print a test plan or image with known dimensions (e.g., field size, distance scale). Measure printed output and verify scaling accuracy (+/- 1 mm).

**4. Geometric Accuracy Checks:**
   a.  **Load Geometric Phantom CT:** Import the standard geometric phantom CT dataset.
   b.  **Distance Measurement:** Use TPS tools to measure known distances within the phantom (e.g., between fiducials, phantom dimensions). Verify agreement with known values (+/- 1 mm).
   c.  **DRR Generation:** Generate DRRs (AP/LAT) for a defined isocenter within the phantom. Verify correct anatomical representation and overlay with reference images if available.

**5. CT Number / Density Check:**
   a.  **Load Density Phantom CT:** Import the standard electron density phantom CT dataset.
   b.  **Measure HU:** Draw ROIs within each known density plug. Record the mean HU value for each plug.
   c.  **Compare to Baseline:** Compare measured HU values to the established baseline values for that phantom/scanner.
      - *Tolerance:* +/- 20 HU from baseline.
      - *Action:* See Worked Example for Activity 4.
   d.  **Verify Active Curve:** Confirm the correct CT-to-Density curve is active in the TPS.

**6. Dose Calculation Consistency Checks:**
   a.  **Load Benchmark Plan(s):** Load pre-defined baseline QA plan(s) (e.g., simple 10x10 open field, wedged field, standard IMRT/VMAT plan).
   b.  **Recalculate Dose:** Recalculate the dose distribution for each benchmark plan using the standard clinical algorithm.
   c.  **Compare to Baseline:** Compare key dosimetric parameters to the baseline values established during commissioning:
      - **Point Dose:** Compare dose at isocenter or other defined points (+/- 2% of baseline).
      - **MU:** Compare calculated Monitor Units (+/- 1-2% of baseline, depending on complexity).
      - **DVH Parameters:** Compare key DVH metrics for target/OARs (+/- 2-3% or within established tolerance).
      - **Visual Comparison:** Visually compare isodose distributions to baseline images.
      - *Action:* If any parameter exceeds tolerance, investigate thoroughly (check beam data, algorithm settings, software updates). Do not use affected functionality clinically until resolved.

**7. Data Transfer Checks:**
   a.  **Test Patient Export:** Create a simple test plan. Export the plan data via the standard clinical pathway (e.g., DICOM RT Plan to R&V system).
   b.  **R&V System Import:** Import the test plan into the R&V system.
   c.  **Parameter Verification:** In the R&V system, verify critical parameters match the TPS plan: Patient Name/ID, Plan Name, Field Size, Gantry/Coll/Couch Angles, MUs, MLC positions (spot check), Energy, Modality.
      - *Tolerance:* Exact match required for all parameters.
      - *Action:* If discrepancies found, investigate TPS export settings, network connectivity, R&V import configuration. Halt clinical plan transfers until resolved.

**8. Documentation:**
   a.  Record all results, measurements, and comparisons on the Monthly TPS QA Log Sheet.
   b.  Note any deviations from baseline and actions taken.
   c.  Sign and date the log sheet.
   d.  Report any unresolved issues or actions exceeding tolerance to the Lead Physicist immediately.

**References:**
- AAPM Task Group 53 Report
- Institutional TPS QA Policy
- TPS Vendor Documentation

**Review:** This procedure shall be reviewed annually by the Lead Medical Physicist and updated as necessary based on system changes, software updates, incident learning, and evolving guidelines.

