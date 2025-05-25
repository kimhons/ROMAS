# Section 4.4: Solutions for Multiple Choice Questions - Treatment Planning System Safety and QA

**1. c) The medical physicist.**
   *Explanation: TG-53 explicitly states that the medical physicist has the primary responsibility for the technical aspects of TPS QA, including commissioning, routine checks, and ensuring overall system accuracy and safety, although it requires a team effort involving oncologists and therapists.*

**2. c) Comprehensive validation of dose calculation algorithm accuracy against measurements across various phantom geometries and beam configurations.**
   *Explanation: Comprehensive algorithm validation against measurements is a cornerstone of initial commissioning (TG-53). While routine QA verifies consistency (e.g., benchmark plan recalculation), it doesn't typically repeat the full suite of commissioning measurements.*

**3. c) Lateral electron transport and scatter across different densities.**
   *Explanation: Heterogeneities (like air cavities or bone within tissue) significantly perturb the electron transport path. Accurate modeling of how electrons scatter laterally and deposit dose across density interfaces is a key challenge tested by heterogeneous phantom measurements.*

**4. c) Failure Modes and Effects Analysis (FMEA).**
   *Explanation: TG-100 specifically details the application of FMEA and other prospective risk analysis methods (like process mapping) to identify potential failures before they occur and implement mitigation strategies.*

**5. c) Severity x Occurrence x Detectability**
   *Explanation: The Risk Priority Number (RPN) in FMEA is calculated by multiplying the scores assigned to the Severity of the failure's effect, the likelihood of its Occurrence, and the likelihood of Detecting the failure before it causes harm.*

**6. d) Exporting the approved plan data from the TPS to the Record & Verify system.**
   *Explanation: This step involves transferring complex data (MLC positions, MUs, gantry angles, etc.) between systems. Errors during this transfer (e.g., data corruption, incorrect mapping, network issues) can lead to the wrong plan being delivered, making it a critical control point.*

**7. d) Performing a significant subset of the original commissioning tests relevant to the changes.**
   *Explanation: TG-53 recommends that QA after software updates should be commensurate with the significance of the update. For major updates, this often involves repeating relevant commissioning tests to ensure the changes haven't negatively impacted calculations, data transfer, or other functionalities.*

**8. b) Beam data should be measured for each specific treatment machine and validated during commissioning.**
   *Explanation: TG-53 strongly emphasizes the need for machine-specific beam data measured by the physicist and rigorously validated during TPS commissioning. Using generic vendor data is not considered acceptable for clinical treatment planning.*

**9. c) Provide an independent verification that the plan is safe, accurate, consistent with the prescription, and correctly transferred for delivery.**
   *Explanation: The physics plan review serves as a crucial independent safety check, verifying multiple aspects of the plan's technical correctness and ensuring it aligns with the clinical intent before treatment begins.*

**10. b) Verifying the accuracy of Digitally Reconstructed Radiograph (DRR) generation against known phantom geometry.**
    *Explanation: DRR generation involves projecting the CT dataset based on beam geometry. Comparing the generated DRR of a phantom with known dimensions/markers to an actual portal image or expected projection directly tests the geometric accuracy of the TPS's coordinate systems and projection algorithms.*

