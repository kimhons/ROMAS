# Section 4.4: Deep Dive - AAPM TG-219: Independent Calculation-Based Dose/MU Verification for IMRT

**Reference:** Zhu, T. C., Stathakis, S., Clark, J. R., Feng, W., Georg, D., Holmes, S. M., ... & Xiao, Y. (2021). Report of AAPM Task Group 219 on independent calculation-based dose/MU verification for IMRT. *Medical Physics*, *48*(10), e808-e829. https://doi.org/10.1002/mp.15069

## 1. Introduction: The Role of Independent MU/Dose Checks

Independent verification of Monitor Units (MU) or dose calculations has long been a cornerstone of radiation oncology QA, ensuring that the dose delivered to the patient aligns with the prescription. While measurement-based patient-specific IMRT QA (like that discussed in TG-218) verifies the *deliverability* of a plan and the overall dose distribution shape, independent calculation checks serve a complementary but distinct purpose: verifying the *correctness of the MU calculation* performed by the primary Treatment Planning System (TPS) for a given plan.

With the complexity of IMRT and Volumetric Modulated Arc Therapy (VMAT), simple hand calculations are insufficient. Various software tools and algorithms have been developed to perform these secondary checks. TG-219 was established to provide guidance on the use, commissioning, and QA of these calculation-based verification tools for IMRT/VMAT.

## 2. Purpose and Scope of Independent Calculation Checks

- **Goal:** To catch potential errors in the primary TPS MU calculation or data transfer that might not be detected by measurement-based QA alone.
- **Complementary, Not Replacement:** Independent calculation checks are intended to complement, not replace, measurement-based IMRT QA. They check different aspects of the process.
- **Scope:** Primarily focused on verifying the absolute dose or MU for the entire plan or specific points/volumes, rather than a detailed 3D dose distribution comparison (though some tools offer this).

## 3. Review of Calculation Algorithms Used in Secondary Check Software

TG-219 reviews various algorithms employed by commercial and institutional secondary check software, ranging in complexity and accuracy:

- **Factor-Based / Correction-Based Methods:** Simpler methods often based on modifying standard Clarkson or similar algorithms used for 3D CRT. They may use effective field sizes, segment weighting, or simplified scatter calculations. Accuracy can be limited, especially for complex modulation or heterogeneous media.
- **Point Dose Kernels / Superposition/Convolution (C/S):** More sophisticated algorithms similar to those used in primary TPS, involving calculation of primary and scatter dose components using dose kernels. Offer potentially higher accuracy but require more complex beam modeling and commissioning.
- **Monte Carlo (MC):** Considered the gold standard for accuracy but computationally intensive. Less common in routine secondary check software due to speed constraints, but becoming more feasible.
- **Grid-Based Boltzmann Solvers (GBBS):** Offer accuracy approaching MC with potentially faster computation times.

**Key Consideration:** The accuracy of any secondary check algorithm is fundamentally limited by the accuracy of its beam model and its ability to handle the complexities of modulated delivery and patient geometry.

## 4. Commissioning and Acceptance Testing

Thorough commissioning of secondary check software is crucial before clinical use.

- **Beam Modeling:** Requires acquiring and inputting beam data specific to the institution's linear accelerator(s). This may involve measuring profiles, PDDs, output factors, MLC transmission, DLG, etc., similar to primary TPS commissioning, although potentially simplified depending on the algorithm.
- **Algorithm Configuration:** Setting parameters specific to the chosen algorithm (e.g., calculation grid size, heterogeneity corrections).
- **Validation:** Testing the software against known standards and measurements:
    - **Benchmark Cases:** Using standardized phantom plans (e.g., from AAPM TG-119) or simpler geometric fields to compare secondary check results against measurements or primary TPS calculations (after primary TPS validation).
    - **Clinical Test Cases:** Evaluating performance on a range of representative clinical IMRT/VMAT plans previously verified with measurement-based QA.
    - **Point Dose Checks:** Comparing calculated point doses (e.g., at isocenter) with ion chamber measurements in phantom for various field sizes and modulations.
- **Vendor Documentation:** Reviewing vendor documentation regarding algorithm details, limitations, and recommended commissioning procedures.

## 5. Periodic Quality Assurance (QA)

Ongoing QA is necessary to ensure the continued accuracy and reliability of the secondary check software.

- **Frequency:** Recommendations align with general TPS QA principles (e.g., TG-53, TG-142).
    - **Annual QA:** Comprehensive review including beam model verification (checking against annual linac QA data), recalculation of benchmark/clinical test cases, verification of software settings.
    - **Routine Checks:** Incorporating secondary checks into patient-specific QA workflow.
- **Software Updates:** Re-commissioning or validation testing is required after software updates or changes to the primary TPS or linac that could affect the secondary check calculation (e.g., linac output recalibration, primary TPS beam model changes).

## 6. Clinical Implementation and Action Levels

- **Workflow Integration:** Integrating the secondary check into the clinical workflow, typically performed after plan approval but before treatment.
- **Point vs. Volumetric Checks:** Depending on the software, checks can be performed at single points (e.g., isocenter, high-dose/low-gradient PTV point), multiple points, or using 3D dose volume comparisons.
- **Tolerance/Action Levels:** TG-219 recommends establishing institutional action levels for agreement between the secondary check and the primary TPS.
    - **Factors Influencing Limits:** Choice of algorithm (simpler algorithms may require looser limits), plan complexity, clinical site, institutional experience.
    - **Recommended Action Levels (Example):** A common starting point might be a **5%** difference for point dose comparisons. Institutions should refine this based on commissioning data and clinical experience.
    - **Investigation:** Discrepancies exceeding the action level require investigation to determine the source (e.g., secondary check limitation, primary TPS error, data transfer issue).
- **Interpretation:** Understanding the limitations of the specific secondary check algorithm is crucial when interpreting results, especially for highly complex plans or regions near heterogeneities.

## 7. Limitations

- **Algorithm Accuracy:** Secondary check algorithms are often simpler than primary TPS algorithms and may have inherent limitations.
- **Beam Model Accuracy:** The accuracy is dependent on the quality of the beam model commissioning.
- **Not a Substitute for Measurement:** Calculation checks cannot detect errors in the actual machine delivery (e.g., MLC positional errors, output fluctuations) that measurement-based QA can identify.

## Conclusion

AAPM TG-219 emphasizes the value of independent calculation-based dose/MU verification as a complementary tool within a comprehensive IMRT/VMAT QA program. It provides essential guidance on selecting, commissioning, performing ongoing QA, and clinically implementing these secondary check systems. By understanding the algorithms, their limitations, and establishing appropriate, data-driven action levels, institutions can effectively use these tools to catch potential errors in primary TPS calculations or data transfer, further enhancing the safety and accuracy of complex radiotherapy treatments.

