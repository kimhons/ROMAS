# Section 4.4: Deep Dive - AAPM TG-100: Application of Risk Analysis Methods to Radiation Therapy Quality Management

**Reference:** Huq, M. S., Fraass, B. A., Dunscombe, P. B., Gibbons Jr, J. P., Ibbott, G. S., Mundt, A. J., ... & Yorke, E. D. (2016). The report of Task Group 100 of the AAPM: Application of risk analysis methods to radiation therapy quality management. *Medical Physics*, *43*(7), 4209-4262. https://doi.org/10.1118/1.4947547

## 1. Introduction: The Need for a New QM Paradigm

AAPM Task Group 100 (TG-100) addresses the limitations of traditional, prescriptive quality management (QM) approaches in radiation therapy, particularly in the face of increasing treatment complexity (e.g., IMRT, VMAT, SBRT). Traditional methods, often focused on equipment functional performance checks against set tolerances (like TG-40 or TG-142), may not adequately address errors arising from failures in workflow and process, which are significant contributors to incidents.

TG-100 proposes a shift towards **prospective, risk-based QM**. Instead of solely relying on generic checklists and tolerance tables, this approach involves systematically analyzing clinical processes to identify potential failure modes *before* they occur, assessing their likelihood and clinical impact, and prioritizing QM efforts on the highest-risk areas.
The goal is to design more effective and efficient QM programs tailored to specific clinical processes and environments, ultimately enhancing patient safety and treatment quality.

## 2. Core Methodologies

TG-100 introduces and demonstrates several tools borrowed from industrial quality management and safety engineering:

**2.1. Process Mapping:**
- **Purpose:** To visually represent a clinical workflow as a sequence of steps and sub-steps.
- **Method:** Creating a detailed flowchart that outlines the entire process from patient consultation through treatment completion and follow-up. This requires input from all team members involved (physicians, physicists, dosimetrists, therapists).
- **Benefit:** Provides a clear, shared understanding of the process, identifies interfaces and handoffs, and serves as the foundation for subsequent risk analysis.

**2.2. Failure Modes and Effects Analysis (FMEA):**
- **Purpose:** A systematic, proactive method to identify potential failures in a process and assess their potential impact.
- **Method:**
    1.  **Identify Failure Modes (FMs):** For each step in the process map, brainstorm ways it could potentially fail or go wrong.
    2.  **Identify Potential Effects:** Determine the consequences of each failure mode occurring (ranging from minor inconvenience to catastrophic patient harm).
    3.  **Identify Potential Causes:** Determine the root causes that could lead to the failure mode.
    4.  **Assess Current Controls:** Identify existing checks or procedures designed to prevent or detect the failure.
    5.  **Score Risk:** Assign numerical scores (typically 1-10) for:
        - **Severity (S):** How serious are the effects if the failure occurs?
        - **Occurrence (O):** How likely is the failure mode to occur (considering current controls)?
        - **Detectability (D):** How likely is the failure to be detected before causing harm (considering current controls)? (Note: Higher score means *less* likely to be detected).
    6.  **Calculate Risk Priority Number (RPN):** RPN = S x O x D.
    7.  **Prioritize & Mitigate:** Rank failure modes by RPN (and often also by Severity alone). Develop and implement action plans (new controls, process changes, training) to reduce the risk associated with high-priority FMs, typically by reducing Occurrence or increasing Detectability.
- **Benefit:** Provides a structured way to prioritize QM resources on the areas posing the greatest risk.

**2.3. Fault Tree Analysis (FTA):**
- **Purpose:** A top-down deductive analysis used to identify the potential causes of a specific undesired event (e.g., a significant dosimetric error).
- **Method:** Starts with the top event (the failure) and branches down to identify the prerequisite events (component failures, human errors, environmental factors) using logical gates (AND, OR) until basic, initiating causes are reached.
- **Benefit:** Helps understand the complex interplay of factors that can lead to a specific failure, identifies critical components or steps, and can guide the placement of effective QM interventions (e.g., redundant checks).

## 3. Designing Risk-Based QM Programs

TG-100 outlines a methodology for using these tools to design a QM program:
1.  **Establish Goals:** Define the objectives of the QM program (e.g., prevent specific types of errors, ensure dosimetric accuracy within X%).
2.  **Perform Risk Analysis:** Conduct process mapping and FMEA for the relevant clinical process (e.g., IMRT planning and delivery).
3.  **Prioritize:** Identify the highest-risk failure modes based on RPN and Severity scores.
4.  **Analyze Causes (using FTA if helpful):** Understand the pathways leading to high-risk failures.
5.  **Select QM Interventions:** Strategically place QM checks or controls within the process map/fault tree to mitigate the prioritized risks. Focus on interventions that reduce Occurrence or increase Detectability.
6.  **Choose QM Tools:** Select appropriate tools for the interventions (e.g., checklists, independent calculations, automated scripts, phantom measurements, peer review).
7.  **Define Tolerances & Frequencies:** Determine appropriate action levels and testing frequencies for the chosen QM checks, potentially informed by the risk analysis (higher risk may warrant tighter tolerances or more frequent checks).
8.  **Implement & Monitor:** Put the QM program into practice, document results, and periodically review its effectiveness, updating the risk analysis and QM plan as needed (continuous quality improvement).

## 4. IMRT Example Application

The report provides a detailed example applying this methodology to a generic IMRT process. Key findings from their sample FMEA included:
- **High-Risk Areas:** Often involve data transfer, complex calculations, manual procedures, and communication handoffs.
- **Top Failure Modes (Example):** Included errors like incorrect MU calculation/transfer, incorrect patient/plan association, Linac output calibration errors, incorrect beam modeling in TPS, contouring errors.
- **QM Program Design:** The analysis guided the placement and type of QM checks, emphasizing independent verification at critical points (e.g., physics plan review, patient-specific IMRT QA, machine QA focused on high-impact parameters).
- **Informing Traditional QA:** The risk analysis can help justify or modify traditional QA tests and frequencies. For example, the analysis might support focusing machine QA on parameters with high RPNs (like output constancy) while potentially reducing the frequency of checks on parameters found to have lower risk impact.

## 5. Recommendations and Guidance

- **Clinic-Specific Analysis:** TG-100 stresses that while their example is illustrative, each clinic **must** perform its own process mapping and risk analysis, as workflows, equipment, software, and staffing vary significantly.
The provided FMEA tables should *not* be adopted directly but used as a guide and starting point.
- **Team Effort:** Risk analysis requires input from the entire radiation oncology team.
- **Living Document:** The risk analysis and resulting QM program should be periodically reviewed and updated based on experience, incident learning, and changes in technology or procedures.
- **Resource Allocation:** Risk analysis helps justify and optimize the allocation of limited QM resources.
- **Beyond Equipment QA:** Emphasizes the critical need for process-oriented QA.
- **Role of Professional Organizations:** Suggests that organizations like AAPM can facilitate the use of these methods by providing training, tools, and potentially libraries of common failure modes (while cautioning against generic adoption).
- **Regulators:** Encourages regulators to recognize and support risk-based QM approaches rather than relying solely on prescriptive regulations.

## Conclusion

TG-100 represents a significant paradigm shift in radiotherapy quality management, moving from a purely prescriptive, equipment-focused model towards a proactive, process-oriented, risk-based approach. By systematically analyzing clinical workflows using tools like process mapping and FMEA, clinics can identify their unique vulnerabilities, prioritize QM efforts effectively, and design more efficient and robust safety programs. While requiring an initial investment of time and effort, this methodology offers a powerful framework for improving patient safety and treatment quality in the increasingly complex environment of modern radiation therapy.

