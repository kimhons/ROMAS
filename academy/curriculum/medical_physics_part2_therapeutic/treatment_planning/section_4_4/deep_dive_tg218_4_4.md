# Section 4.4: Deep Dive - AAPM TG-218: Tolerance Limits and Methodologies for IMRT Measurement-Based Verification QA

**Reference:** Miften, M., Olch, A., Mihailidis, D., Moran, J., Pawlicki, T., Molineu, A., ... & Low, D. A. (2018). Tolerance limits and methodologies for IMRT measurement-based verification QA: Recommendations of AAPM Task Group No. 218. *Medical Physics*, *45*(4), e53-e83. https://doi.org/10.1002/mp.12810

## 1. Introduction: The Need for Standardized IMRT QA

Patient-specific Intensity Modulated Radiation Therapy (IMRT) Quality Assurance (QA) measurements are a critical component of ensuring the accuracy and safety of complex radiation treatments. They aim to verify that the dose delivered matches the dose calculated by the Treatment Planning System (TPS).

However, significant variability exists across institutions regarding:
- Measurement methodologies (phantoms, detectors, setup).
- Analysis metrics (Dose Difference, Distance-to-Agreement (DTA), Gamma (γ) index).
- Parameter choices within metrics (dose thresholds, normalization, γ criteria).
- Tolerance and action limits for passing/failing QA results.

This lack of standardization makes it difficult to compare results, understand the true sensitivity of QA processes to potential errors, and ensure consistent quality of care. TG-218 was formed to address these issues and provide recommendations for improving the consistency and effectiveness of measurement-based IMRT QA.

## 2. Dose Comparison Metrics

TG-218 reviews the common metrics used for comparing measured and calculated dose distributions:

- **Dose Difference (%DD):** Compares dose values at corresponding points. Sensitive to overall dose scaling errors but performs poorly in high dose gradient regions.
- **Distance-to-Agreement (DTA):** Measures the distance between a point in one distribution and the nearest point with the same dose value in the other distribution. Performs well in high gradient regions but is insensitive to overall dose errors in flat regions.
- **Gamma (γ) Index:** A composite metric combining both %DD and DTA criteria. A point passes if *any* point within the DTA distance in the comparison distribution has a dose difference less than the %DD criterion. It provides a single metric sensitive to errors in both low and high gradient regions.
    - **Calculation:** γ(r_m) = min{ Γ(r_m, r_c) } for all r_c, where Γ(r_m, r_c) = sqrt[ ( |r_m - r_c|^2 / DTA^2 ) + ( (D(r_m) - D(r_c))^2 / %DD^2 ) ]. A point passes if γ ≤ 1.
    - **Global vs. Local %DD:**
        - *Global %DD:* Dose difference normalized to the maximum dose in the reference distribution (often the calculation). Less sensitive to errors in low-dose regions.
        - *Local %DD:* Dose difference normalized to the dose value at the point of evaluation in the reference distribution. More sensitive to errors in low-dose regions, but can be overly sensitive where dose is very low.
        - **Recommendation:** TG-218 generally recommends using **global %DD** for γ analysis, but acknowledges local %DD can be useful for specific investigations.
- **Passing Rate:** The percentage of evaluated points that pass the chosen criteria (e.g., % points with γ ≤ 1).

## 3. Practical Considerations for γ Analysis

- **Normalization:** How the measured and calculated distributions are scaled relative to each other significantly impacts results. Normalizing the measurement to the calculation based on the maximum dose or a point dose in a low-gradient region is common. TG-218 discusses various methods and their implications.
- **Spatial Resolution:** The resolution of both the measurement device and the calculation grid affects the γ result. Measurements should ideally have comparable or higher resolution than the calculation.
- **Dose Threshold:** Points below a certain dose threshold (e.g., 10% of maximum dose) are often excluded from the γ analysis to avoid noise and uncertainties in very low dose regions dominating the results.
- **Interpolation:** Interpolation is necessary when comparing distributions with different spatial resolutions. The method used can influence results.
- **Vendor Implementations:** TG-218 found significant variability in how different commercial software packages implement the γ analysis (normalization, interpolation, thresholding, edge handling), leading to different results even with the same input data and criteria. They recommend users understand their specific software's implementation.

## 4. Measurement Methods and Absolute Dose Verification

- **Measurement Setups:**
    - *True Composite (TC):* All beams delivered with actual gantry/couch angles to a phantom.
    - *Perpendicular Field-by-Field (PFF):* Each beam delivered perpendicularly to the detector.
    - *Perpendicular Composite (PC):* All beams delivered perpendicularly to the detector.
    - **Recommendation:** Methods delivering beams perpendicularly (PFF, PC) are generally preferred for planar detector arrays due to simpler setup and avoidance of angular dependencies, but TC may better represent clinical delivery for some detectors/phantoms.
- **Absolute Dose Verification:** Verifying the absolute dose scaling (not just relative distribution shape) is crucial.
    - *Single Point:* Using an ion chamber at a specific point (often isocenter or high-dose/low-gradient region).
    - *2D/3D Methods:* Using calibrated detector arrays (e.g., ArcCHECK, MapCHECK, Delta4, EPID) capable of providing absolute dose information across the measurement plane/volume.
    - **Recommendation:** Absolute dose verification should be part of the IMRT QA process.

## 5. Review of Reported Agreement and Recommendations

TG-218 reviewed extensive published data and clinical experience to establish achievable levels of agreement and recommend tolerance/action limits.

- **Key Findings:**
    - Passing rates are highly dependent on the chosen criteria (%DD, DTA), normalization, threshold, delivery system, detector, and TPS accuracy.
    - Stricter criteria (e.g., 2%/2mm) yield lower passing rates than looser criteria (e.g., 3%/3mm).
    - Complex plans (e.g., SBRT, head & neck) often show lower passing rates than simpler plans (e.g., prostate).
    - Different delivery systems (Linac, TomoTherapy) and detectors have different inherent uncertainties.

- **Recommendations for Tolerance/Action Limits (using γ index with global %DD, 10% dose threshold):**
    - **Tolerance Limit (Institutional Goal):** Aim for a high percentage of plans to meet this level (e.g., 95% pass rate with 3%/2mm).
    - **Action Limit (Investigate):** Plans falling below this level require investigation (e.g., 90% pass rate with 3%/2mm).
    - **Specific Criteria:** The report suggests specific γ criteria based on plan complexity/site:
        - *Simpler plans (e.g., prostate):* Consider criteria like 3%/2mm.
        - *Complex plans (e.g., H&N SBRT):* May require slightly relaxed criteria like 3%/3mm or 4%/2mm, but investigation is still needed if action limits are not met.
    - **Absolute Dose:** Point dose agreement (e.g., ion chamber) should generally be within +/- 3-5%.
    - **Emphasis:** These are *recommendations*, and institutions should establish their own specific limits based on their equipment, processes, and clinical experience, informed by TG-218's analysis.

## 6. Investigating Failed QA

When a plan fails to meet the action limits, a systematic investigation is required:
1.  **Check Measurement Setup:** Verify phantom setup, detector calibration/correction, beam delivery parameters.
2.  **Check QA Software:** Verify analysis parameters (normalization, threshold, criteria), software version, calculation import.
3.  **Check Delivery System:** Review MLC performance logs, machine output, relevant machine QA results.
4.  **Check TPS:** Verify beam model, calculation algorithm, plan parameters, CT data.
5.  **Re-measure/Re-calculate:** If necessary, repeat the measurement or recalculate the plan.

## Conclusion

AAPM TG-218 provides crucial guidance for standardizing and improving the effectiveness of measurement-based IMRT QA. It offers a detailed analysis of comparison metrics (especially the γ index), practical considerations for analysis, reviews measurement methods, and, importantly, provides data-driven recommendations for tolerance and action limits. By promoting a better understanding of the tools and establishing more consistent criteria, TG-218 aims to enhance the ability of IMRT QA to detect clinically relevant errors and ensure patient safety.

