# Section 4.3: Management of Inter- and Intra-fraction Variations - Assessment

**Instructions:** Answer the following questions to the best of your ability, drawing upon the concepts covered in this section.

## Part 1: Multiple Choice (Select the best answer)

1.  A patient undergoing SBRT for a liver lesion shows 2.0 cm SI motion on 4DCT. If an ITV-based approach is used, the primary purpose of the ITV is to:
    a) Account only for random setup errors.
    b) Define the region of microscopic disease spread.
    c) Encompass the full range of the GTV's motion during respiration.
    d) Compensate for the interplay effect during VMAT delivery.

2.  Which IGRT modality is generally preferred for daily localization of prostate cancer when fiducial markers are implanted?
    a) MV EPID imaging based on bony anatomy.
    b) kV CBCT registered to bony anatomy.
    c) kV CBCT registered to fiducial markers.
    d) Ultrasound based on soft tissue.

3.  Respiratory gating aims to reduce the impact of motion by:
    a) Physically restricting diaphragm movement.
    b) Delivering radiation only during specific phases of the breathing cycle.
    c) Dynamically moving the MLC leaves to follow the tumor.
    d) Having the patient hold their breath during beam-on time.

4.  According to TG-132, which is a critical step in the clinical use of any image registration software?
    a) Ensuring the software uses a Mutual Information metric.
    b) Relying solely on the automatic registration result without review.
    c) Performing patient-specific visual verification and approval of the registration result.
    d) Using only rigid registration for all clinical sites.

5.  Offline adaptive radiotherapy typically involves:
    a) Adjusting MLC positions in real-time during treatment delivery.
    b) Daily re-optimization of the plan based on CBCT acquired just before treatment.
    c) Acquiring a new planning CT and creating a new treatment plan part-way through the treatment course.
    d) Using larger PTV margins to account for all possible anatomical changes.

## Part 2: Short Answer

6.  Define the "interplay effect" in the context of IMRT/VMAT and respiratory motion. Why is it a concern?

7.  Describe two distinct methods recommended by TG-76 for quantifying respiratory motion during CT simulation.

8.  Explain the difference between rigid and deformable image registration. Provide one clinical scenario where each type is essential.

9.  According to TG-101, why is accurate dose calculation (using algorithms like Monte Carlo or Collapsed Cone) particularly important for lung SBRT compared to conventional lung RT?

10. What is the primary goal of standardizing nomenclature for OARs and target volumes, as recommended by TG-263?

## Part 3: Scenario Analysis

11. A patient is planned for pancreatic SBRT. A 4DCT shows 1.5 cm SI motion of the pancreas GTV, which is immediately adjacent to the duodenum. The institution has capabilities for 4DCT, CBCT, RPM gating, and abdominal compression, but not real-time tracking or MRI-Linac.
    a) Discuss the challenges of using a simple ITV approach for this patient.
    b) Propose a feasible motion management strategy using the available technology, justifying your choice and outlining the key implementation steps (including IGRT).

12. During daily CBCT for a prostate IMRT patient (with fiducials), the physicist notes that the fiducial match suggests a 1.2 cm anterior shift of the prostate relative to the planning CT, while the bony match suggests only a 0.2 cm anterior shift. The patient reports difficulty adhering to the rectal preparation protocol.
    a) Which registration result (bony or fiducial) should be used to guide the couch shift, and why?
    b) What potential dosimetric consequences could arise if the incorrect registration were used?
    c) What actions, beyond applying the daily shift, might be considered for this patient?

