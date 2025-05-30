# Section 4.4: Clinical Scenarios - Treatment Planning System Safety and QA

**Instructions:** Analyze the following scenarios related to Treatment Planning System (TPS) safety and quality assurance. Consider the principles outlined in TG-53, TG-100, and other relevant guidelines. Discuss potential risks, necessary QA steps, and appropriate actions.

## Scenario 1: New TPS Commissioning

A radiation oncology department is commissioning a new TPS from a different vendor than their previous system. The physics team has imported the beam data for their primary Linac (measured according to TG-51 and TG-106 protocols) and configured the dose calculation algorithm (a Collapsed Cone Convolution Superposition type). They are now ready to begin clinical use.

**Discussion Points:**
1.  **Is the department ready for clinical use?** Based on TG-53 principles, what critical commissioning steps are missing or need explicit verification before treating patients?
2.  **Beam Data Import:** What specific checks should be performed to ensure the imported beam data (PDDs, profiles, output factors) accurately represents the measured data and is correctly interpreted by the new TPS?
3.  **Algorithm Validation:** Outline a minimum set of test cases (geometries, phantom types, clinical conditions) that should be used to validate the accuracy of the dose calculation algorithm against measurements. What are typical acceptance criteria?
4.  **End-to-End Testing:** Describe an appropriate end-to-end test for this new TPS. What parameters should be verified during this test?
5.  **Risk Assessment (TG-100):** Identify at least three potential failure modes specific to commissioning a *new* TPS vendor system. For one of these failure modes, suggest a mitigation strategy.

## Scenario 2: IMRT Plan Verification Discrepancy

During routine patient-specific IMRT QA for a head and neck plan, the measured dose distribution (using a 2D diode array) shows a gamma analysis passing rate of only 85% using 3%/3mm criteria (global normalization, 10% threshold). The TPS calculation predicted a much higher passing rate.

**Discussion Points:**
1.  **Initial Investigation:** What are the immediate steps the physicist should take to investigate this discrepancy?
2.  **Potential Causes (TPS-related):** List potential TPS-related factors that could contribute to this disagreement (consider algorithm limitations, beam modeling, data transfer).
3.  **Potential Causes (Measurement-related):** List potential measurement-related factors (detector setup, calibration, phantom issues).
4.  **Potential Causes (Delivery-related):** List potential Linac delivery-related factors (MLC accuracy, gantry/collimator issues).
5.  **Resolution:** If the discrepancy is traced back to the TPS beam model (e.g., inaccurate modeling of MLC transmission or tongue-and-groove), what actions should be taken according to TPS QA principles (TG-53)? Can the patient be treated before resolution?

## Scenario 3: Software Update Anomaly

The TPS vendor releases a mandatory software update that includes bug fixes and a minor enhancement to the optimization algorithm. The update is installed by the physics team over a weekend. On Monday morning, routine TPS QA checks (e.g., recalculating a standard benchmark plan) show no significant deviations.

**Discussion Points:**
1.  **Adequacy of QA:** Are the routine QA checks performed sufficient after a software update, even if benchmark plans pass? Why or why not?
2.  **TG-53 Recommendations:** What level of QA does TG-53 recommend after software updates? What specific tests might be warranted beyond simple benchmark plan recalculation?
3.  **Risk Assessment:** What new potential failure modes might be introduced by a software update, even one intended only for bug fixes?
4.  **Clinical Impact:** Later that week, a therapist notes that the DRRs generated for a prostate patient look slightly different (blurrier) than usual, although the plan parameters seem correct. How should this observation be handled? Could it be related to the update? What specific TPS QA checks might investigate this?

## Scenario 4: Implementing Risk Analysis (TG-100)

A clinic wants to implement the TG-100 methodology for their treatment planning process. They have mapped out the major steps: CT Simulation -> Image Import -> Contouring -> Planning -> Plan Evaluation -> Physics Review -> Data Export -> R&V System.

**Discussion Points:**
1.  **FMEA Process:** Choose one specific step in the process map (e.g., Contouring or Physics Review). Identify two potential failure modes for that step.
2.  **Risk Scoring:** For one of the failure modes identified above, assign hypothetical scores (1-10) for Severity (S), Occurrence (O), and Detectability (D). Calculate the Risk Priority Number (RPN = S x O x D).
3.  **Mitigation:** Based on the hypothetical RPN, suggest a specific action or check that could be implemented to reduce the risk associated with that failure mode (i.e., reduce O or increase D).
4.  **Challenges:** What are some practical challenges a clinic might face when implementing a formal FMEA process for the entire radiotherapy workflow?

