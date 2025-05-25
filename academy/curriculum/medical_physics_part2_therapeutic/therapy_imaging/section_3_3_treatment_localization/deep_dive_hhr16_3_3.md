## Deep Dive: IAEA HHR 16 - Introduction of Image Guided Radiotherapy into Clinical Practice (Detailed Bullet Points)

### Introduction: The Evolution Towards Adaptive Radiotherapy

*   **Context:** Image Guided Radiotherapy (IGRT) represents a significant advancement in radiation therapy, enabling visualization of the tumor and surrounding normal tissues immediately before or during treatment delivery. This allows for verification and correction of patient positioning errors and potentially adaptation of the treatment plan based on anatomical changes.
*   **Purpose of HHR 16:**
    *   To provide practical guidance on the clinical implementation of IGRT technologies.
    *   To outline the necessary steps for introducing IGRT safely and effectively into routine practice, focusing on technical, clinical, and organizational aspects.
    *   To complement existing IAEA guidance on QA and safety in radiotherapy (e.g., TRS reports, Safety Guides).
*   **Target Audience:** Primarily aimed at radiotherapy departments (medical physicists, radiation oncologists, radiation therapists/technologists, administrators) planning to implement or optimize IGRT practices.
*   **Key Benefit of IGRT:** Allows for reduction in planning target volume (PTV) margins, potentially enabling dose escalation to the tumor and/or better sparing of organs at risk (OARs), leading to improved therapeutic ratio.

### IGRT Technologies and Systems

HHR 16 provides an overview of common IGRT modalities:

*   **Planar kV Imaging:**
    *   Uses orthogonal kV X-ray images (similar to simulation) acquired on the treatment machine.
    *   Compares digitally reconstructed radiographs (DRRs) from the planning CT with acquired kV images.
    *   Allows for 2D or 3D correction based on bony anatomy or implanted fiducial markers.
    *   Examples: Electronic Portal Imaging Devices (EPIDs) used in kV mode, separate kV imagers mounted on the linac gantry.
*   **Cone Beam CT (CBCT):**
    *   Acquires a volumetric dataset using a kV source and flat-panel detector mounted on the linac gantry, rotating around the patient.
    *   Provides 3D soft tissue visualization at the time of treatment.
    *   Allows for 3D/3D registration with the planning CT based on bony anatomy or soft tissue structures.
    *   Most common form of volumetric IGRT.
*   **MV Imaging (EPID):**
    *   Uses the treatment beam (MV photons) and an Electronic Portal Imaging Device (EPID) to acquire planar images or MV CBCT.
    *   Pros: Directly uses the treatment beam geometry.
    *   Cons: Lower image quality (especially soft tissue contrast) compared to kV imaging due to Compton scatter dominance; higher imaging dose per projection.
    *   Useful for verifying beam aperture, MLC position, and patient position based on bony anatomy or high-contrast markers.
*   **In-Room CT:**
    *   A diagnostic-quality CT scanner located within or adjacent to the treatment room (e.g., CT-on-rails).
    *   Provides high-quality volumetric images immediately before treatment.
    *   Requires patient transfer between imaging and treatment positions (potential for introducing errors).
*   **MRI-Guided Radiotherapy (MRgRT):**
    *   Integrates an MRI scanner with a linear accelerator.
    *   Provides superior soft tissue visualization without additional ionizing radiation dose.
    *   Enables real-time tracking and gating/adaptation based on soft tissue motion.
    *   Technically complex and expensive.
*   **Ultrasound Guidance:**
    *   Uses ultrasound probes to visualize certain targets/organs (e.g., prostate).
    *   Non-ionizing, real-time capable.
    *   Operator dependent, limited penetration/field of view.
*   **Surface Guidance (SGRT - Surface Guided Radiation Therapy):**
    *   Uses optical/laser scanning systems to monitor the patient's external surface.
    *   Provides real-time, non-ionizing monitoring of patient position and motion.
    *   Useful for initial setup verification and intra-fraction motion monitoring, especially for techniques like Deep Inspiration Breath Hold (DIBH).
    *   Relies on correlation between external surface and internal target position.
*   **Fiducial Markers:**
    *   Small, inert markers (e.g., gold seeds) implanted in or near the target.
    *   Provide high-contrast reference points for image registration across different modalities (CT, kV, MV, CBCT).
    *   Essential for accurate localization when target/soft tissue contrast is poor or bony anatomy is not a reliable surrogate.

### Clinical Implementation Steps

HHR 16 outlines a structured approach:

*   **1. Needs Assessment and Planning:**
    *   Define clinical goals for IGRT (e.g., reduce margins, manage motion, enable specific techniques like SBRT).
    *   Evaluate available technologies based on clinical needs, resources, and existing infrastructure.
    *   Form a multidisciplinary implementation team (oncologist, physicist, therapist, administrator).
    *   Develop a project plan with timelines, budget, and responsibilities.
*   **2. Procurement and Site Preparation:**
    *   Develop technical specifications for the chosen IGRT system.
    *   Consider vendor selection, installation requirements, shielding modifications, network integration.
*   **3. Acceptance Testing and Commissioning:**
    *   **Acceptance Testing:** Verify that the installed system meets manufacturer specifications and contractual agreements (performed by physicist, often with vendor support).
    *   **Commissioning:** Characterize the system's performance comprehensively, establish baseline values, and acquire data needed for clinical use and QA (performed by physicist).
        *   Geometric accuracy tests (imaging vs. radiation isocenter coincidence, spatial resolution, scaling, distortion).
        *   Image quality assessment (contrast, noise, uniformity, spatial resolution, HU accuracy for CBCT).
        *   Imaging dose measurements.
        *   Registration software validation.
        *   Workflow testing.
*   **4. Development of Clinical Protocols and Procedures:**
    *   Define site-specific IGRT protocols:
        *   Imaging modality and frequency (daily, weekly, etc.).
        *   Imaging parameters (kVp, mAs, scan length/angle for CBCT).
        *   Reference images (planning CT, DRRs).
        *   Registration methods (bony anatomy, soft tissue, fiducials).
        *   Action thresholds for position correction (e.g., correct if > 3 mm).
        *   Documentation requirements.
    *   Develop clear procedures for therapists performing IGRT acquisition and registration.
    *   Establish roles and responsibilities for image review and correction approval (therapist, physicist, oncologist).
*   **5. Training:**
    *   Comprehensive training for all staff involved (physicists, oncologists, therapists) covering:
        *   Principles of IGRT.
        *   System operation.
        *   Image interpretation and registration.
        *   Clinical protocols and procedures.
        *   QA procedures.
        *   Radiation safety aspects (imaging dose).
*   **6. Clinical Go-Live and Initial Monitoring:**
    *   Start with a pilot phase, potentially on simpler cases or phantoms.
    *   Intensive monitoring and supervision during initial clinical use.
    *   Collect data on workflow efficiency, setup accuracy, imaging dose, and clinical outcomes.
*   **7. Ongoing Quality Assurance (QA):**
    *   Develop and implement a robust QA program specifically for the IGRT system, integrated with the overall linac QA (following guidelines like AAPM TG-179, TG-142, TG-104).
    *   QA tests should cover geometric accuracy, image quality, imaging dose, and registration software functionality.
    *   Define frequencies (daily, monthly, annual) and tolerance/action levels.

### Key Considerations for Safe and Effective IGRT

*   **Imaging Dose:**
    *   All ionizing radiation-based IGRT modalities add dose to the patient.
    *   Imaging dose should be considered as part of the overall exposure and optimized (ALARA principle applied to imaging protocols).
    *   Particularly important for paediatric patients and frequent imaging schedules (e.g., daily CBCT).
    *   Need for methods to estimate and potentially record cumulative imaging dose.
*   **Workflow Efficiency:**
    *   IGRT adds time to each treatment fraction.
    *   Workflow needs to be optimized to minimize impact on patient throughput and machine availability.
    *   Clear procedures, efficient software, and adequate staffing are crucial.
*   **Defining Action Thresholds:**
    *   The decision on when and how much to correct based on IGRT findings requires careful consideration.
    *   Thresholds should be based on clinical goals, PTV margins used, and estimated uncertainties in the IGRT process itself.
    *   Overly tight thresholds might lead to chasing random errors, while overly loose thresholds negate the benefit of IGRT.
*   **Registration Accuracy:**
    *   Accuracy depends on image quality, registration algorithm, and the anatomical features used (bone vs. soft tissue vs. fiducials).
    *   Manual adjustments by therapists require training and consistency checks.
    *   Understanding the limitations of the registration process is essential.
*   **Moving Towards Adaptive Radiotherapy (ART):**
    *   IGRT provides the necessary information to enable ART, where treatment plans are modified during the course based on observed anatomical changes (e.g., tumor shrinkage, weight loss, organ motion).
    *   Implementing ART requires additional resources, specialized software, and robust validation processes beyond standard IGRT.

### Conclusion: Integrating Imaging into Treatment Delivery

*   **Essential Tool:** IGRT is now considered an essential component of modern high-precision radiotherapy.
*   **Implementation Pathway:** HHR 16 provides a valuable roadmap for clinics embarking on IGRT implementation, emphasizing a structured, multidisciplinary approach.
*   **Focus on QA and Safety:** Successful IGRT requires rigorous commissioning, ongoing QA, well-defined clinical protocols, comprehensive training, and attention to imaging dose.
*   **Foundation for Advancement:** Provides the geometric accuracy necessary for techniques like margin reduction, dose escalation, SBRT, and forms the basis for future adaptive radiotherapy strategies.
