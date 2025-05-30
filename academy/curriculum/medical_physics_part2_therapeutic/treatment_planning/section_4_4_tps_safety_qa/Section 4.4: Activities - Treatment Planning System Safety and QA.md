# Section 4.4: Activities - Treatment Planning System Safety and QA

**Instructions:** Complete the following activities to reinforce your understanding of TPS safety and quality assurance principles.

## Activity 1: TPS Commissioning Test Design (TG-53)

**Objective:** To design specific test cases for commissioning a TPS dose calculation algorithm.

**Task:**
1.  Select **one** specific clinical scenario where TPS dose calculation accuracy is critical (e.g., lung SBRT near low-density tissue, IMRT field junction, electron cutout field, wedged tangential breast field).
2.  Describe the phantom setup you would use to measure the dose distribution for this scenario (phantom type, detector type, setup details).
3.  Describe how you would model this scenario in the TPS.
4.  Specify the key dosimetric parameters or comparisons you would make between the TPS calculation and the measurement (e.g., point doses at specific locations, profile comparisons, PDD comparisons, gamma analysis criteria).
5.  State a reasonable acceptance criterion for this test, justifying your choice based on clinical relevance and guidelines (e.g., TG-53).

**Deliverable:** A brief report (1-2 paragraphs per task point) outlining your test design.

## Activity 2: Basic FMEA for a Planning Step (TG-100)

**Objective:** To apply the basic principles of Failure Modes and Effects Analysis (FMEA) to a specific step in the treatment planning process.

**Task:**
1.  Consider the treatment planning step: **"Exporting the approved plan from the TPS to the Record & Verify (R&V) system."**
2.  Identify **three** potential failure modes for this specific step.
3.  For **one** of these failure modes:
    a) Describe the potential **effect(s)** on the patient or treatment delivery.
    b) Suggest a possible **cause(s)**.
    c) Assign hypothetical scores (1-10) for **Severity (S)**, **Occurrence (O)**, and **Detectability (D)**, briefly justifying each score.
    d) Calculate the **Risk Priority Number (RPN)**.
    e) Propose a specific **mitigation strategy** (a check, procedure, or technology) that could reduce the RPN (by lowering O or increasing D).

**Deliverable:** A structured summary presenting the failure modes, FMEA analysis for one mode, and the proposed mitigation strategy.

## Activity 3: Interpreting IMRT QA Results

**Objective:** To analyze hypothetical IMRT QA results and determine appropriate actions.

**Scenario Data:**
- Plan: Prostate VMAT
- Measurement Device: ArcCHECK cylindrical diode array
- Analysis Software: SNC Patient
- Gamma Criteria: 3% (Global) / 3 mm
- Dose Threshold: 10%
- Result: Gamma passing rate = 92.5%
- Observation: Most failing points are clustered in a low-dose gradient region anterior to the PTV.

**Task:**
1.  Does this result meet typical action levels (e.g., based on TG-218 recommendations, often >95% for 3%/3mm)?
2.  Given the passing rate and the location of failing points, what is the likely clinical significance of this discrepancy? Justify your reasoning.
3.  What further investigation steps would you take?
4.  If the investigation points towards a minor systematic setup error of the QA phantom/detector, what would be the appropriate course of action regarding the patient treatment?
5.  If the investigation points towards an issue with the TPS beam model in low-dose regions, what would be the appropriate course of action?

**Deliverable:** Answers to the five task points, providing clear justifications.

## Activity 4: Designing a Routine TPS QA Check

**Objective:** To design a simple, effective routine QA check for a specific TPS function.

**Task:**
1.  Choose **one** specific function or aspect of the TPS that requires routine verification (e.g., CT-density curve stability, DRR generation accuracy, MU calculation consistency for a simple field, basic DVH calculation accuracy).
2.  Design a quick test procedure (runnable monthly or quarterly) to check this function.
3.  Specify the expected result or baseline value.
4.  Define clear action levels or tolerances for this check.
5.  Describe the documentation required for this routine check.

**Deliverable:** A concise description of the routine QA check procedure.

