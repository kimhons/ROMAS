# Deep Dive: AAPM TG-65 - Tissue Inhomogeneity Corrections for Megavoltage Photon Beams (2004)

**Source:** AAPM Report No. 85, Report of Task Group 65 (2004)

## 1. Introduction and Clinical Need

Published in 2004, TG-65 addressed the critical issue of accounting for tissue inhomogeneities (like lung, bone, air cavities) in megavoltage photon beam dose calculations. At the time, despite the availability of CT imaging providing 3D density information, the use of accurate inhomogeneity corrections was inconsistent across clinics. This inconsistency complicated dose reporting, comparison of clinical outcomes (especially in multi-center trials), and potentially compromised treatment effectiveness, particularly with the rise of conformal therapies and dose escalation.

**Key Motivations for TG-65:**

*   **Inconsistent Practice:** Many centers still used water-equivalent calculations or overly simplistic correction methods.
*   **Advancing Technology:** Improved 3D imaging (CT), more powerful computers, and the development of more sophisticated dose calculation algorithms made accurate corrections feasible.
*   **Conformal Therapy & Dose Escalation:** Techniques like 3D-CRT and early IMRT aimed to conform dose tightly to the target. This increased the importance of accurately predicting dose distributions, as small errors could lead to target underdosing or OAR overdosing, especially with escalated doses where complication risks are higher.
*   **Geographic Misses:** Inaccurate dose calculation in heterogeneous regions could lead to incorrect isodose line placement, potentially causing a geographic miss of the target volume.

**Objectives of TG-65:**

1.  Review the clinical need for inhomogeneity corrections.
2.  Review the available algorithms for photon beam inhomogeneity corrections.
3.  Assess the advantages and disadvantages of each algorithm category.
4.  Provide recommendations on the use and verification of these corrections in the clinic.

The report aimed to provide physicists with the understanding needed to evaluate their TPS capabilities, advise oncologists on dose accuracy, and make informed decisions when purchasing new systems.

## 2. Required Dose Accuracy

TG-65 delves into the complex question of *how accurate* dose calculations need to be, particularly concerning inhomogeneity corrections. It reviews factors influencing this:

*   **Dose-Response Slopes:** Steeper dose-response curves for tumor control (TCP) and normal tissue complications (NTCP) imply that small dose variations can have significant clinical consequences. While often cited figures suggest a 5% dose change can alter TCP by 10-20% and NTCP by 20-30%, these are generalizations.
*   **Clinically Detectable Differences:** Studies suggest clinicians might struggle to reliably detect dose differences below 5-7% based on outcomes alone due to biological variability and other confounding factors.
*   **Clinical Trial Needs:** For reliable clinical trial data comparison, higher accuracy and consistency are desirable.
*   **Achievable Accuracy:** Considers the entire chain of uncertainties (calibration, setup, machine output, planning). ICRU reports historically aimed for an overall accuracy of ±5%.

**TG-65 Recommendation on Accuracy:**

While acknowledging the ±5% overall goal, TG-65 argues that the accuracy requirement for the *inhomogeneity correction component itself* should likely be tighter, perhaps in the range of **2-3%**, especially in critical regions (e.g., near interfaces, within small targets, near critical OARs). This is because the inhomogeneity correction is just one part of the overall dose calculation uncertainty.

*Street Wisdom:* The 5% overall accuracy goal is a benchmark, but striving for better accuracy in the calculation component, especially in challenging heterogeneous regions, is crucial for high-precision radiotherapy like SBRT or IMRT.

## 3. Relevant Radiation Physics

TG-65 provides a detailed review of the physics underlying dose deposition in heterogeneous media, forming the basis for understanding different algorithm approaches.

*   **Photon Interactions (TERMA):** The first step involves primary photons interacting with the medium, transferring energy to secondary charged particles (electrons and positrons). The key quantity is **TERMA (Total Energy Released per unit MAss)**, $\Psi_{TERMA}$. This depends on the photon energy fluence ($\\Phi_E$) and the mass energy absorption coefficient ($(\mu_{en}/\rho)$) of the medium.
    $$ \Psi_{TERMA}(\vec{r}) = \int_E \Phi_E(\vec{r}) \left( \frac{\mu_{en}(E)}{\rho} \right) dE $$
*   **Charged Particle Transport (DOSE):** The secondary electrons travel finite distances, scattering and depositing energy. This energy deposition determines the absorbed **DOSE**. The spatial distribution of this energy deposition relative to the initial interaction site is described by a **dose deposition kernel**, $K(\vec{r}, \vec{r}\')$.
*   **Superposition/Convolution Principle:** The total dose at a point $\vec{r}$ is the superposition (integral) of dose contributions from energy released (TERMA) at all surrounding points $\vec{r}\'$, weighted by the dose kernel:
    $$ D(\vec{r}) = \int_{V} \Psi_{TERMA}(\vec{r}\') K(\vec{r}, \vec{r}\') dV\\' $$
    This forms the basis of Category 4 algorithms.
*   **Charged Particle Equilibrium (CPE):**
    *   **Concept:** CPE exists if, within a small volume, the energy carried away by electrons leaving the volume is exactly balanced by the energy carried in by electrons originating outside the volume. Under CPE, Dose = Collision Kerma.
    *   **Transient CPE (TCPE):** A state approached deep within a uniform medium irradiated by photons, where electron fluence becomes relatively constant with depth. Dose is proportional to collision kerma here.
    *   **Lateral CPE:** Equilibrium in the direction perpendicular to the beam. Lost near field edges and interfaces.
    *   **Relevance:** CPE rarely exists perfectly in clinical situations, especially near the surface (buildup region), field edges, and interfaces between different density materials. Algorithms must account for the *lack* of CPE.
*   **Influence of Density ($\\rho$) and Atomic Number (Z):**
    *   **Density Scaling:** Many algorithms approximate heterogeneous media by scaling the water kernel based on relative electron density ($\\rho_e$). This assumes interaction probabilities scale primarily with electron density. This works reasonably well for tissues like lung and soft tissue where $Z_{eff}$ is close to water.
        *   Radiological Path Length: Used in density scaling, $\int \rho_e(l) dl$.
    *   **Atomic Number Effects:** For materials with $Z_{eff}$ significantly different from water (e.g., bone, contrast agents, metal implants), density scaling alone is insufficient. Photon interaction cross-sections (especially photoelectric effect at lower MV energies, pair production at higher MV energies) and electron stopping powers depend on Z. Accurate algorithms (MC, some advanced convolution) need to account for material composition, not just density.
*   **Primary and Scatter Components:** Dose can be separated into contributions from primary photons and scattered photons. Simpler algorithms often handle these components differently.

*Street Wisdom:* Understanding the breakdown of CPE near interfaces is key to grasping why simple algorithms fail. Electrons scattering out of dense material into low-density material (or vice-versa) create dose perturbations that require explicit electron transport modeling.




## 4. Inhomogeneity Correction Methods (Algorithm Categories)

TG-65 categorizes algorithms based on two main features: **density sampling** (1D vs. 3D) and **modeling of electron transport** (implicit/none vs. explicit).

### Category 1: Local Energy Deposition (No Electron Transport); 1D Density Sampling

*   **Concept:** These methods apply corrections based on radiological path length along straight lines (rays) from the source to the calculation point. They assume electrons deposit energy locally (at the site of the photon interaction) and ignore lateral scatter and electron transport effects.
*   **Methods:**
    *   **Linear Attenuation:** Simplest; scales dose based only on primary beam attenuation.
    *   **Effective Attenuation Coefficient:** Uses an average attenuation coefficient.
    *   **Ratio of Tissue-Air Ratios (RTAR):** Uses TARs scaled by radiological depth.
    *   **Power Law (Batho Method):** Scales dose based on TARs raised to a power related to electron densities along the ray path. $D_{het} = D_{wat} \times \left( \frac{TAR(d\\'_1, w)}{TAR(d, w)} \right)^{\rho_{e1}-1} \times \left( \frac{TAR(d\\'_2, w)}{TAR(d\\]_1, w)} \right)^{\rho_{e2}-1} ...$
*   **Limitations:** Highly inaccurate, especially near interfaces, in buildup regions, and laterally. Fails to predict dose perturbations due to electron transport changes. Should not be used for modern clinical planning.

### Category 2: Local Energy Deposition (No Electron Transport); 3D Density Sampling

*   **Concept:** These methods account for the 3D distribution of tissue densities when calculating scatter contribution but still assume local energy deposition by electrons.
*   **Methods:**
    *   **Equivalent Tissue-Air Ratio (ETAR - Sontag & Cunningham):** Calculates dose as the sum of primary and scatter components. Scatter is calculated by integrating contributions from surrounding voxels, weighted by their electron density relative to water, using scaled TARs. Accounts for 3D scatter geometry but not electron transport.
    *   **Differential Scatter-Air Ratio (dSAR):** Similar principle to ETAR but uses dSARs.
    *   **Delta Volume (DVOL):** Another method considering 3D scatter.
    *   **Differential Tissue-Air Ratio (dTAR):** Uses dTARs.
    *   **3D Beam Subtraction:** Models scatter using subtraction methods.
*   **Limitations:** Better than Category 1 as they account for 3D scatter, but still inaccurate near interfaces due to the lack of electron transport modeling. ETAR was widely used but has known limitations (e.g., underdosing distal to low-density regions).

### Category 3: Non-Local Energy Deposition (Electron Transport); 1D Density Sampling

*   **Concept:** Early attempts at modeling electron transport using convolution, but often simplified the density information to 1D (along ray lines or laterally invariant layers).
*   **Methods:**
    *   **Convolution Techniques:** Applied kernels representing electron spread.
    *   **Fast Fourier Transform (FFT) Convolution:** Used FFTs for computational efficiency but typically required 1D density assumption.
*   **Limitations:** An improvement over Cat 1/2, but the 1D density assumption limits accuracy in truly 3D heterogeneous geometries.

### Category 4: Non-Local Energy Deposition (Electron Transport); 3D Density Sampling

*   **Concept:** The most sophisticated analytical algorithms, explicitly modeling electron transport based on the 3D patient density map derived from CT.
*   **Methods:**
    *   **Superposition-Convolution Methods:** Implement the principle $D = TERMA \otimes Kernel$. They calculate the 3D TERMA distribution and convolve it with a spatially variant dose kernel representing electron transport. Kernels are often pre-calculated using Monte Carlo in water and then scaled based on local density.
        *   Examples: Collapsed Cone Convolution (CCC), Adaptive Convolution, Pencil Beam Recomposition.
        *   **CCC:** Efficient implementation using polyenergetic kernels transported along discrete cone directions. Offers a good balance of accuracy and speed.
    *   **Monte Carlo (MC) Method:** Direct simulation of millions/billions of particle histories (photons and electrons) through detailed models of the linac head and patient geometry. Considered the gold standard for accuracy.
        *   Inherently handles all transport effects in 3D heterogeneous media.
        *   Requires significant computational time (though improving) and careful commissioning (TG-105).
    *   **Linear Boltzmann Transport Equation (LBTE) Solvers:** Deterministic methods that solve the fundamental transport equation directly (e.g., Acuros XB). Offer accuracy comparable to MC without statistical noise.
*   **Advantages:** Provide the most accurate dose predictions, especially near interfaces, in buildup regions, and for complex techniques like IMRT/VMAT.

*Street Wisdom:* For curative radiotherapy, especially involving complex plans or significant inhomogeneities, only Category 4 algorithms (Convolution/Superposition, MC, LBTE solvers) should be considered clinically acceptable today. Understanding the specific implementation and limitations of your TPS's Cat 4 algorithm is crucial.

## 5. Data Comparison of Dose in Inhomogeneous Media

TG-65 presents numerous comparisons of calculations from different algorithm categories against experimental measurements in phantoms containing air, lung-equivalent material, and bone.

*   **Air Cavities:** Simpler algorithms significantly overestimate dose downstream from air cavities due to neglecting the loss of electron buildup.
*   **Lung:**
    *   **Within Lung:** Cat 1/2 algorithms often overestimate dose.
    *   **Interface Effects:** Significant dose reduction occurs just inside the lung, and dose enhancement occurs just beyond the lung (in tissue). Cat 1/2 algorithms fail to predict these effects accurately. Cat 4 algorithms show much better agreement with measurements.
*   **Bone:**
    *   **Within Bone:** Dose can be higher due to increased electron production and lower electron ranges. Density scaling alone may not capture Z effects accurately.
    *   **Interface Effects:** Dose reduction occurs in tissue just beyond bone due to absorption/scattering in bone. Cat 4 algorithms are needed for accuracy.
*   **CT Number Influence:** The accuracy of *all* heterogeneity corrections depends critically on the accuracy of the CT number to electron density (and potentially material) conversion curve used by the TPS.
*   **Small Fields/Radiosurgery:** Inhomogeneity effects can be particularly pronounced for small fields where lateral electronic equilibrium is already lost.
*   **Benchmark Data:** The report provides references to measured datasets that can be used for commissioning and verifying algorithm accuracy.

## 6. The Effect of Inhomogeneity in IMRT

IMRT presents unique challenges and further emphasizes the need for accurate (Category 4) algorithms:

*   **Small Beamlets:** IMRT plans consist of many small, intensity-modulated beamlets.
*   **Steep Gradients:** Plans often feature very steep dose gradients near targets and OARs.
*   **Fluence Perturbations:** Small beamlets passing through heterogeneous regions experience significant fluence perturbations and electron transport effects.
*   **Cumulative Effect:** Errors in calculating dose for individual beamlets can accumulate, leading to significant deviations in the final composite dose distribution.

TG-65 concludes that the use of accurate inhomogeneity corrections (Cat 4) is **particularly important** for IMRT planning to ensure target coverage and OAR sparing are correctly predicted.

## 7. Summary and Recommendations

*   **Clinical Need:** Accurate inhomogeneity corrections are essential for modern radiotherapy, especially with conformal techniques, dose escalation, and IMRT/VMAT.
*   **Algorithm Choice:** **Strongly recommends** using algorithms that account for 3D density variations and explicitly model electron transport (Category 4: Superposition/Convolution, Monte Carlo, or equivalent LBTE solvers).
*   **Commissioning:** Emphasizes the critical need for **thorough commissioning and validation** of the chosen algorithm against measured data in relevant heterogeneous phantoms before clinical use. Physicists must understand the algorithm's capabilities and limitations.
*   **CT Calibration:** Accurate CT number-to-density/material conversion is paramount.
*   **Communication:** Physicists should communicate the potential inaccuracies or limitations of the TPS algorithm to radiation oncologists to inform clinical decision-making.
*   **Future:** Anticipated increased use of MC and other advanced algorithms as computational power grows.

*Street Wisdom:* TG-65 firmly established the need to move beyond simplistic inhomogeneity corrections. If your clinic still relies on Category 1 or 2 algorithms for definitive treatments, upgrading or restricting their use to palliative cases should be a high priority.


