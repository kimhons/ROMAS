# Section 3.5: Computing and IT - Key Points

This document summarizes key concepts and information extracted from relevant guidance documents and standards for developing Section 3.5 of the curriculum.




## Key Points from TG-262: Electronic Charting

*   **Scope:** Provides guidelines for safe and effective use of Radiation Oncology Electronic Medical Records (RO-EMR), covering implementation, training, acceptance testing, QA, workflow management, information repository use, brachytherapy/nonstandard treatments, and IT considerations.
*   **Importance:** Addresses the lack of consensus guidelines despite widespread RO-EMR adoption.
*   **Implementation & Training:** Requires a dedicated committee, defined goals/milestones, project timelines, protected time, a test environment, and a pilot/transition period. Training is crucial.
*   **Acceptance Testing & QA:** Essential to verify functionality, data integrity, and security. Includes commissioning, ongoing management, and handling software upgrades.
*   **Information Management:** Focuses on user rights, document design/storage (FIESTA: Format, Input, Efficacy, Scope, Traceability, Accessibility), repositories, consistent data entry, electronic signatures, and handling free-text notes.
*   **Workflow Management:** RO-EMR should manage clinical workflows by connecting tasks, linking documents, handling orders (simulation, prescription), capturing charges, formalizing release, allowing refinement, and ensuring clear communication/handoffs.
*   **Brachytherapy & Nonstandard Devices:** Addresses specific challenges related to connectivity (standalone, limited, full), written directives, electronic signatures, and documentation for these treatments.
*   **IT Infrastructure & Data Management:**
    *   **Team:** Requires collaboration between clinical staff and IT professionals familiar with RO-EMR concepts.
    *   **Hardware/Deployment:** Consider clinical needs, institutional constraints, deployment models (local, cloud, hybrid).
    *   **Database:** Critical aspects include disaster recovery (DR), high availability (HA), mobile connectivity, storage capacity, security threats, test environments, and managing database queries on production systems.
    *   **Security:** Emphasizes the need for robust security measures, considering HIPAA and other regulations.
*   **Challenges & Future Improvements:** Calls for continued automation, better checklist functionality, granular approvals, vendor sandboxes, flexible document structures, stronger communication tools, improved workflow efficiency, handshake functionality, concurrent workspace use, better H-EMR connectivity, standardized database access (API), and optional interfaces for nonstandard systems.




## Key Points from TG-132: Image Registration and Fusion (IT Aspects)

*   **Ubiquity:** Image registration/fusion algorithms are integral components of most radiotherapy software systems (TPS, delivery systems, R&V).
*   **Data Flow & Use Cases:** These algorithms handle multimodality and time-series image data, facilitating:
    *   Target/OAR delineation (using atlases or prior images).
    *   Patient positioning (planning vs. in-room images).
    *   Dose assessment and accumulation over time.
    *   Adaptive radiotherapy (propagating contours, accumulating dose).
*   **Data Integrity & Uncertainty:**
    *   The output of registration is input for subsequent critical processes (planning, delivery).
    *   Understanding and communicating uncertainty associated with registration software and specific results is crucial.
    *   Lack of standard formalism for uncertainty quantification in complex clinical scenarios.
    *   Commercial systems often lack documentation ('black-box' issue), complicating validation.
*   **QA & Commissioning:**
    *   Recommends a formal QA program for image registration, managed by the QAC.
    *   Program should cover: validation/QA at planning, delivery, adaptation, response assessment; software commissioning; defining roles/workflow/tolerances; patient-specific verification.
    *   Commissioning involves: software-specific validation, system end-to-end tests (physical/digital phantoms), and example clinical data tests.
    *   QA processes are needed at both treatment planning and delivery stages.
*   **Clinical Integration & Workflow:**
    *   Registration tools are embedded within clinical workflows for planning, delivery, and adaptation.
    *   Accuracy requirements and time constraints vary depending on the application (e.g., planning vs. IGRT).
    *   Errors in registration can propagate significantly (planning errors affect entire course, delivery errors may affect single fraction unless systematic).
*   **IT Considerations:** While not explicitly an IT report, TG-132 highlights the critical dependence on complex software algorithms, the need for rigorous validation/QA processes akin to other critical software, and the management of image data across different systems and time points, all of which have significant IT implications regarding data storage, transfer, integrity, and system performance.




## Key Points from DICOM Standard (WG-07 Radiotherapy Focus)

*   **Scope (WG-07):** Develops and maintains radiotherapy objects (RT Image, RT Structure Set, RT Dose, RT Plan, RT Treatment Record) and related functionality in the DICOM Standard.
*   **Goal:** Ensure interoperability, precise geometric definitions for safe treatment delivery, and integration of imaging within the radiotherapy process.
*   **Key Objects:**
    *   **RT Image:** Stores images used in radiotherapy (e.g., DRRs, portal images).
    *   **RT Structure Set:** Defines contoured structures (targets, OARs) referenced to an image series.
    *   **RT Dose:** Represents spatial dose distributions, often linked to an RT Plan and/or RT Structure Set.
    *   **RT Plan:** Contains geometric and dosimetric information for external beam or brachytherapy treatments (beam parameters, MLC settings, MU, source positions, etc.).
    *   **RT Treatment Record:** Records the actual delivery details of treatment sessions, including beam delivery, patient setup verification, and deviations from the plan.
*   **Modernization:** Ongoing efforts to modernize RT objects (e.g., 2nd Generation RT Plan, Treatment Record) to accommodate newer technologies (e.g., C-arm RT, Tomotherapy, Robotic RT, Ion Therapy) and improve workflow.
*   **Interoperability:** DICOM enables data exchange between different systems (TPS, R&V/OIS, Linacs, Imaging devices) from various vendors.
*   **Workflow Integration:** Supports radiotherapy workflows through mechanisms like Worklists (Supplements 74, 96).
*   **Data Integrity:** Standardized format helps maintain data consistency and integrity throughout the treatment process.
*   **Geometric Precision:** Emphasizes well-defined geometric concepts (Frame of Reference UID, coordinate systems) crucial for accurate targeting and dose delivery.
*   **RDSR (Radiation Dose Structured Report):** Standard for recording dose details from imaging procedures (CT, fluoro, etc.), relevant for cumulative dose tracking.




## Key Points from HHS Cybersecurity Framework Implementation Guide (NIST/HIPAA Focus)

*   **Purpose:** Guide Health Care and Public Health (HPH) sector organizations in implementing the NIST Cybersecurity Framework to manage cyber risk, improve resiliency, and align with regulations like HIPAA.
*   **Problem:** Increasing cyberattacks exploit healthcare vulnerabilities (fragmented infrastructure, legacy systems, connected devices), impacting patient care, operations, data privacy, and compliance. Risk analysis and management are often inadequate (citing OCR audit findings).
*   **NIST Cybersecurity Framework:** Provides a common language and structure for managing cybersecurity risk across an organization. It is voluntary but highly recommended.
    *   **Core Functions:**
        *   **Identify:** Understand cybersecurity risks to systems, assets, data, and capabilities. Includes asset management, risk assessment, governance.
        *   **Protect:** Implement safeguards to ensure delivery of critical services. Includes access control, awareness/training, data security, protective technology.
        *   **Detect:** Implement activities to identify the occurrence of a cybersecurity event. Includes monitoring, detection processes.
        *   **Respond:** Implement activities to take action regarding a detected cybersecurity event. Includes response planning, communications, analysis, mitigation, improvements.
        *   **Recover:** Implement activities to maintain resilience and restore capabilities impaired by an event. Includes recovery planning, improvements, communications.
    *   **Implementation Tiers:** Describe the degree to which an organization's cybersecurity risk management practices exhibit characteristics defined in the Framework (Partial, Risk Informed, Repeatable, Adaptive).
    *   **Profiles:** Represent the alignment of Core Functions/Categories/Subcategories with business requirements, risk tolerance, and resources (Current Profile vs. Target Profile).
*   **Implementation Process (7 Steps):**
    1.  Prioritize and Scope
    2.  Orient (Identify systems, assets, regulatory requirements)
    3.  Create a Target Profile
    4.  Conduct a Risk Assessment
    5.  Create a Current Profile
    6.  Perform Gap Analysis (Current vs. Target)
    7.  Implement Action Plan
*   **HIPAA Alignment:** The guide (and other resources like HICP) provides mappings between NIST Cybersecurity Framework subcategories and HIPAA Security Rule standards/implementation specifications. Implementing the Framework helps organizations meet HIPAA requirements, particularly around risk analysis and risk management.
*   **Risk Management:** Emphasizes integrating cybersecurity into overall Enterprise Risk Management (ERM). Cybersecurity is not just an IT issue but an enterprise-wide risk.
*   **Cyber-Physical Systems (CPS) / Internet of Things (IoT):** Recognizes the importance of securing connected medical devices and other CPS/IoT elements critical to healthcare operations and patient safety.
*   **HICP (Health Industry Cybersecurity Practices):** Complements the Framework by focusing on the top 5 threats and 10 mitigating practices specific to healthcare, mapping these back to the NIST Framework and HIPAA.


