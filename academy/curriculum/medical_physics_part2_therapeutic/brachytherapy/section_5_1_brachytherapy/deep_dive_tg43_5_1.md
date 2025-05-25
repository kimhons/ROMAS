# Deep Dive: AAPM TG-43 Report Update (TG-43U1) - Brachytherapy Dosimetry Formalism

**Source:** Update of AAPM Task Group No. 43 Report: A revised AAPM protocol for brachytherapy dose calculations (Med. Phys. 31 (3), March 2004)

## 1. Introduction and Motivation for Update

*   **Background:** The original TG-43 report (1995) established a standardized dosimetry formalism for photon-emitting brachytherapy sources, moving away from older methods based on apparent activity and generic exposure-rate constants.
*   **Need for Update (TG-43U1, 2004):** Driven by several factors since 1995:
    *   Increased use of permanent LDR implants (especially prostate).
    *   Proliferation of new commercial source models (requiring standardized data).
    *   Introduction of a new primary standard for air-kerma strength ($S_K$) by NIST (National Institute of Standards and Technology) in 1999.
    *   Growth in brachytherapy dosimetry literature (improved methods and data).
    *   Need to clarify ambiguities and correct minor inconsistencies in the original protocol.
*   **Goal of TG-43U1:** Provide an updated, revised protocol incorporating these advances, including consensus datasets for available source models meeting AAPM dosimetric prerequisites.

## 2. Key Revisions and Clarifications in TG-43U1

*   **Revised Definition of Air-Kerma Strength ($S_K$):** Aligned with the NIST-1999 standard (Wide-Angle Free-Air Chamber - WAFAC), which improved accuracy for low-energy sources.
*   **Elimination of Apparent Activity ($A_{app}$):** Strongly recommended discontinuing the use of $A_{app}$ for source strength specification in favor of the directly measurable $S_K$.
*   **Elimination of Anisotropy Constant ($\phi_{an}$):** Replaced the single anisotropy constant with the distance-dependent 1D anisotropy function, $φ_{an}(r)$, providing a more accurate representation of anisotropy variations with distance.
*   **Guidance on Parameter Extrapolation:** Provided recommendations for extrapolating tabulated TG-43 parameters (radial dose function, anisotropy function) to distances beyond the tabulated range.
*   **Consistent Geometry Function Usage:** Clarified the application of point-source ($1/r^2$) vs. line-source geometry functions based on source dimensions and calculation distance.
*   **Unified Approach for Consensus Datasets:** Recommended a standardized methodology for comparing dose distributions from different investigators to develop single, critically evaluated consensus datasets for each source model.
*   **Guidelines for Future Studies:** Provided recommendations for performing and reporting future experimental or Monte Carlo dosimetry studies.

## 3. The TG-43U1 Dosimetry Formalism

*   **Core Principle:** Calculates dose rate in water around a brachytherapy source based on its measured Air Kerma Strength ($S_K$) and pre-determined, source-model-specific parameters derived from Monte Carlo simulations and/or experimental measurements.
*   **Coordinate System:** Polar coordinates $(r, \theta)$, where $r$ is the distance from the source center and $θ$ is the polar angle relative to the source long axis.
*   **General 2D Equation (for dose rate $\\\dot{D}(r, \theta)$):**
    $$ \\\dot{D}(r, \theta) = S_K \times \Lambda \times \frac{G_L(r, \theta)}{G_L(r_0, \theta_0)} \times g_X(r) \times F(r, \theta) $$ 
    *   **Note:** The subscript $X$ for $g_X(r)$ denotes either $L$ (line source) or $P$ (point source) depending on the geometry function used.
*   **Components:**
    *   **$S_K$ (Air Kerma Strength):** Source strength specification. Units: $U = µGy \cdot m^2 \cdot h^{-1}$.
    *   **$\Lambda$ (Dose Rate Constant):** Dose rate in water per unit $S_K$ at the reference point ($r_0$=1 cm, $θ_0$=90°). Units: $cGy \cdot h^{-1} \cdot U^{-1}$.
        $$ \Lambda = \frac{\\\\\dot{D}(r_0, \theta_0)}{S_K} $$ 
    *   **$G_X(r, \theta)$ (Geometry Function):** Accounts for dose variation due to source geometry (inverse square law effects). Normalized relative to the reference point $G_L(r_0, \theta_0)$.
        *   *Point Source Approximation ($X=P$):* $G_P(r, \theta) = r^{-2}$. Recommended when $r >> L$ (source active length).
        *   *Line Source Approximation ($X=L$):* $G_L(r, \theta) = \frac{\beta}{L \cdot r \cdot sin\theta}$, where $\beta$ is the angle subtended by the active source length $L$ at point $(r, \theta)$. Recommended when $r$ is comparable to $L$.
    *   **$g_X(r)$ (Radial Dose Function):** Accounts for radial dose fall-off due to absorption and scatter in the medium along the transverse axis ($θ_0$=90°), relative to the geometry function. Normalized to 1.0 at $r_0$=1 cm. Depends on whether point ($g_P(r)$) or line ($g_L(r)$) geometry function is used.
    *   **$F(r, \theta)$ (2D Anisotropy Function):** Accounts for dose variations with angle ($θ$) relative to the transverse axis ($θ_0$=90°) due to source self-filtration and oblique filtration/scatter. Normalized to 1.0 at $θ_0$=90° for all distances $r$.
*   **General 1D Equation (along transverse axis, $θ=90°$):**
    $$ \\\dot{D}(r, 90°) = S_K \times \Lambda \times \frac{G_X(r, 90°)}{G_X(r_0, 90°)} \times g_X(r) $$ 
    *   This uses the 1D anisotropy function $φ_{an}(r)$, which was defined in TG-43U1 as the ratio of the dose rate averaged over 4π solid angle to the dose rate on the transverse axis at distance r. However, the 2D formalism using $F(r, \theta)$ is generally preferred for 3D planning.

## 4. Consensus Datasets and Source Models

*   **Requirement:** TG-43U1 emphasized using consensus datasets derived from multiple independent studies (Monte Carlo and/or experimental) for the dosimetry parameters ($\Lambda$, $g_X(r)$, $F(r, \theta)$) for each specific source model.
*   **Included Sources (as of July 2001):** The report provided consensus datasets in Appendix A for:
    *   **I-125:** Amersham 6702, 6711; Best 2301; NASI MED3631-A/M; Bebig/Theragenics I25.S06; Imagyn isostar IS-12501.
    *   **Pd-103:** Theragenics 200; NASI MED3633.
*   **Subsequent Updates:** Since 2004, further updates and reports (e.g., TG-43U1S1, TG-43U1S2, specific publications) have provided consensus data for newer source models.
*   **Importance:** Using the correct, validated dataset for the specific source model being used clinically is critical for accurate dose calculation.

## 5. Recommended Methodology for Dosimetry Studies

*   TG-43U1 provided detailed guidance for researchers performing new dosimetry studies to ensure consistency and facilitate comparison:
    *   **Experimental Dosimetry:** Recommendations on detectors (TLDs, diodes, film, etc.), phantoms (water, solid water), measurement techniques, uncertainty analysis.
    *   **Monte Carlo Dosimetry:** Recommendations on codes (EGS, MCNP, GEANT), cross-section data, variance reduction techniques, detailed source geometry modeling, uncertainty analysis.
    *   **Data Reporting:** Standardized format for publishing $\Lambda$, $g_X(r)$, and $F(r, \theta)$ data, including detailed uncertainty budgets.

## 6. Clinical Implementation

*   **Adoption:** Recommended adoption by all clinical users for treatment planning.
*   **Potential Impact:** Adoption could change patient dose calculations compared to older methods or preliminary datasets. Physicists must evaluate these changes carefully with radiation oncologists before clinical implementation.
*   **TPS Commissioning:** Requires rigorous acceptance testing and commissioning of the brachytherapy TPS to ensure:
    *   Correct implementation of the TG-43U1 formalism.
    *   Accurate incorporation of the consensus datasets for all clinically used source models.
    *   Verification of dose calculation accuracy against benchmark cases or independent calculations.
*   **Source Calibration:** Emphasized the importance of using $S_K$ calibrations traceable to primary standards (like NIST) via an Accredited Dosimetry Calibration Laboratory (ADCL).

## 7. Practical Significance and Limitations

*   **Significance:** TG-43U1 provided a robust, standardized, and widely adopted framework for brachytherapy dose calculation, significantly improving consistency and accuracy compared to older methods.
*   **Limitations:**
    *   **Homogeneous Medium:** The formalism inherently assumes a homogeneous water medium, neglecting the impact of tissue heterogeneities (bone, air, lung) and applicator materials.
    *   **Accuracy Limits:** Accuracy can be limited by uncertainties in the consensus datasets, source calibration, and TPS implementation.
    *   **MBDCA:** The need to account for heterogeneities led to the development of Model-Based Dose Calculation Algorithms (MBDCA), addressed in later reports like TG-186.

## 8. Clinical Example Relevance

*   **HDR GYN Planning:** The formalism is used to calculate dose from the Ir-192 source dwell positions to the HR-CTV and OARs.
*   **LDR Prostate Planning:** Used to calculate dose from each I-125 or Pd-103 seed in both pre-planning and post-implant dosimetry.
*   **All Brachytherapy:** Forms the basis for dose calculation in virtually all clinical brachytherapy TPS using photon-emitting sources.


