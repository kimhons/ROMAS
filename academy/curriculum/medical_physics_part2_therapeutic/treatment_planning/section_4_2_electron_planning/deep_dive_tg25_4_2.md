# Deep Dive: AAPM TG-25 - Clinical Electron-Beam Dosimetry (Section 4.2)

**Report:** AAPM Report No. 39, Task Group 25 (TG-25), "Clinical Electron-Beam Dosimetry" (Supplement to TG-21), published in Medical Physics, Vol. 18, No. 1, Jan/Feb 1991.

**Disclaimer:** This document provides a detailed interpretation and practical guidance based on AAPM TG-25. It is intended for educational purposes within the Radiation Oncology Academy curriculum and should not substitute the original report or professional judgment. Always refer to the official AAPM publications and institutional protocols for clinical practice.

**Context:** Published in 1991, TG-25 was a landmark document providing the first comprehensive guidance specifically for clinical electron beam dosimetry in North America. It served as a supplement to the then-current absolute dosimetry protocol, TG-21. While TG-21 (and TG-25's absolute dosimetry references) has been superseded by TG-51, the principles and practical guidance within TG-25 regarding electron beam characteristics, relative dosimetry measurements, and clinical considerations remain foundational and offer crucial insights for practitioners.

## 1. Introduction and Scope: Why Was TG-25 Needed?

Prior to TG-25, electron dosimetry practices varied significantly. TG-21 provided the framework for absolute dose calibration but lacked specific details pertinent to the unique behavior of electron beams. Electrons interact very differently with matter compared to photons, exhibiting significant scattering, a defined range, and complex interactions near inhomogeneities. TG-25 aimed to:

*   **Standardize Terminology:** Define key parameters for characterizing electron beams ($E_{p,0}$, $E_0$, $R_p$, $R_{50}$, etc.).
*   **Recommend Measurement Techniques:** Provide practical guidance on using ionization chambers (cylindrical vs. parallel-plate), diodes, and film for relative dosimetry.
*   **Specify Data Requirements:** Outline the necessary beam data (PDDs, profiles, output factors) for accurate treatment planning.
*   **Address Clinical Considerations:** Discuss energy selection, field shaping, bolus use, and the challenges of inhomogeneities and field matching.

**Practical Implication:** Understanding TG-25 helps appreciate the evolution of electron dosimetry and provides context for current practices outlined in TG-51 and TG-70. It highlights the fundamental physics and measurement challenges specific to electrons.

## 2. Electron Beam Characteristics: Defining the Beam

TG-25 meticulously defined parameters to characterize the energy and spatial distribution of clinical electron beams. Accurate characterization is paramount for selecting the appropriate beam for treatment and for commissioning treatment planning systems (TPS).

**2.1. Energy Specification:** Electrons lose energy rapidly and non-linearly as they penetrate tissue. Therefore, specifying energy is more complex than for photons.

*   **Most Probable Energy at Surface ($E_{p,0}$):**
    *   **Definition:** Represents the peak energy of the electron spectrum as the beam enters the phantom. It's closely related to the accelerator's nominal energy setting.
    *   **Determination:** Measured indirectly via the **Practical Range ($R_p$)** in water. $R_p$ is the depth where the tangent to the steepest part of the depth dose curve intersects the extrapolated Bremsstrahlung background. The relationship is empirical:
        $$ E_{p,0} ("MeV") \approx C_1 + C_2 R_p + C_3 R_p^2 $$
        (TG-25 provided constants, e.g., $C_1=0.22, C_2=1.98, C_3=0.0025$ for $R_p$ in cm). Note: These specific constants might be slightly refined in later literature, but the principle holds.
    *   **Practical Use:** Primarily used for relating the beam to the accelerator setting and as a parameter in some older TPS models. It's less critical for modern dosimetry protocols (like TG-51) which rely on $R_{50}$.
    *   **Clinical Relevance:** Higher $E_{p,0}$ means deeper penetration.

*   **Mean Energy at Surface ($E_0$):**
    *   **Definition:** Represents the average energy of the electron spectrum at the phantom surface.
    *   **Determination:** Related empirically to the **Half-Value Depth ($R_{50}$)**, the depth beyond $d_{max}$ where the dose falls to 50% of the maximum.
        $$ E_0 ("MeV") \approx C_4 R_{50} ("cm") $$
        where $C_4$ is approximately 2.33 MeV/cm for water.
    *   **Practical Use:** Crucial parameter for modern dosimetry. $R_{50}$ is the beam quality specifier (Q) used in the TG-51 protocol to determine the $k_Q$ factor.
    *   **Clinical Relevance:** $E_0$ provides a better representation of the beam's average penetration capability than $E_{p,0}$.

*   **Mean Energy at Depth z ($E_z$):**
    *   **Definition:** The average energy of the electron spectrum decreases with depth due to energy loss.
    *   **Estimation:** Approximated by a linear decrease:
        $$ E_z \approx E_0 (1 - z/R_p) $$
    *   **Practical Use:** Important for understanding detector response variations with depth (stopping power ratios change with energy) and for some older heterogeneity correction methods.
    *   **Clinical Relevance:** Explains why the beam's characteristics (scattering, stopping power) change significantly with depth.

**Measurement Considerations:** Accurate determination of $R_p$ and $R_{50}$ requires careful measurement of the Percent Depth Dose (PDD) curve using appropriate detectors and scanning techniques (discussed below).

**2.2. Depth Dose Characteristics:** The PDD curve is the fingerprint of an electron beam's penetration.

*   **Surface Dose ($D_s$):**
    *   **Definition:** Dose at depth z=0. For electrons, this is *not* zero and increases with energy (typically 75-95% of $D_{max}$).
    *   **Measurement Challenge:** Accurate measurement requires detectors with minimal window thickness and perturbation, ideally parallel-plate chambers extrapolated to zero cavity thickness or radiochromic film.
    *   **Clinical Relevance:** Important for treating superficial targets and assessing skin dose. Bolus may be needed to increase surface dose.
*   **Depth of Maximum Dose ($d_{max}$ or $R_{100}$):**
    *   **Definition:** Depth where absorbed dose is highest. Occurs due to the build-up of secondary electrons (delta rays) and increasing electron fluence initially.
    *   **Energy Dependence:** $d_{max}$ increases with energy (roughly $E("MeV")/4$ to $E("MeV")/3$ cm).
    *   **Clinical Relevance:** The region between the surface and $d_{max}$ is the build-up region.
*   **Therapeutic Range ($R_{90}, R_{85}, R_{80}$):**
    *   **Definition:** Depths at which the dose falls to 90%, 85%, 80% of $D_{max}$ on the distal side.
    *   **Practical Use:** Used for selecting the appropriate beam energy to cover a target volume. For example, the distal edge of the target might be placed at or near the $R_{85}$ or $R_{90}$ depth.
    *   **Rule of Thumb:** $R_{90} \approx E("MeV")/3.2$ cm; $R_{80} \approx E("MeV")/2.8$ cm (These are approximate and vary slightly).
*   **Half-Value Depth ($R_{50}$):**
    *   **Definition:** Depth beyond $d_{max}$ where dose is 50% of $D_{max}$.
    *   **Practical Use:** Key parameter for beam quality specification (Q) in TG-51 and related to $E_0$.
*   **Practical Range ($R_p$):**
    *   **Definition:** Maximum penetration depth of primary electrons, found by extrapolation.
    *   **Practical Use:** Related to $E_{p,0}$.
    *   **Rule of Thumb:** $R_p \approx E("MeV")/2$ cm.
*   **Bremsstrahlung Tail:**
    *   **Definition:** Low-dose region beyond $R_p$ due to X-rays produced as electrons decelerate in the phantom, collimator, and applicator.
    *   **Energy Dependence:** The relative contribution increases with electron energy.
    *   **Clinical Relevance:** Represents dose deposited beyond the electron range, which can be important for critical structures distal to the target.

**2.3. Beam Profiles (Flatness & Symmetry):** Describes dose uniformity across the beam.

*   **Definition:** Dose variation measured perpendicular to the beam axis at a specific depth.
*   **Parameters:** Flatness (variation within the central 80% of the field width) and Symmetry (difference between corresponding points on opposite sides of the central axis).
*   **Measurement:** Typically measured using ionization chambers, diodes, or film in a water phantom.
*   **TG-25 Recommendation:** Check profiles at multiple depths (e.g., $d_{max}$, $R_{50}$) as electron scattering causes profiles to change significantly with depth (penumbra widens, flatness degrades).
*   **Clinical Relevance:** Ensures uniform dose delivery across the target volume. Deviations can indicate issues with the accelerator's scattering foils or beam steering.

**2.4. Output Factors:** Relate dose delivered per Monitor Unit (MU) under different conditions.

*   **Definition:** Ratio of dose rate (cGy/MU) under specific conditions (field size, applicator, SSD) to the dose rate under reference conditions.
*   **Dependence:** Output varies significantly with applicator size and any custom cutouts due to changes in electron scattering from the collimation system.
*   **Measurement:** Must be measured for all clinically used applicators and representative cutout sizes.
*   **Clinical Relevance:** Essential for calculating the correct MUs needed to deliver the prescribed dose.

## 3. Dosimetry Equipment and Measurement Techniques: Tools of the Trade

TG-25 provided crucial guidance on selecting and using dosimetry equipment for electrons.

*   **Phantoms:**
    *   **Water:** The standard and recommended phantom material due to its tissue equivalence for electrons and well-defined properties.
    *   **Solid Phantoms (Polystyrene, Acrylic, Solid Water™):** Can be used for convenience, especially for routine QA. However, TG-25 stressed the need for careful corrections:
        *   **Depth Scaling:** Scale depths by the electron density relative to water.
        *   **Fluence Correction:** Account for differences in scattering properties.
        *   **Stopping Power Correction:** Account for differences in energy loss characteristics when converting ionization measurements to dose.
    *   **Practical Guidance:** Water is preferred for commissioning and high-accuracy measurements. If solid phantoms are used, scaling factors must be carefully determined and validated, often specific to the phantom material and electron energy.

*   **Detectors:** Detector choice significantly impacts measurement accuracy.
    *   **Ionization Chambers:**
        *   **Cylindrical (Farmer-type):** Readily available and well-characterized for photon dosimetry. However, in electron beams:
            *   **Perturbation:** The air cavity and chamber materials perturb the electron field, requiring correction factors ($P_{wall}$, $P_{fl}$). TG-21/TG-25 provided methods, largely superseded by $k_Q$ in TG-51.
            *   **Gradient Effects:** In the steep dose fall-off region, the dose gradient across the chamber volume leads to measurement errors. TG-25 recommended applying an **Effective Point of Measurement (EPOM)** correction, shifting the measurement point **upstream** (towards the source) by approximately **$0.5 r_{cav}$** (where $r_{cav}$ is the cavity radius). This remains relevant when using cylindrical chambers for relative electron dosimetry.
        *   **Parallel-Plate Chambers:** TG-25 strongly recommended these for electron dosimetry, especially for PDD measurements.
            *   **Advantages:** Minimal perturbation (especially well-guarded designs), well-defined EPOM (at the inner surface of the proximal electrode), accurate measurements in high-gradient regions and build-up region.
            *   **Types:** Markus, Roos, NACP chambers are common examples.
            *   **Considerations:** Potential for polarity effects ($P_{pol}$) and ion recombination ($P_{ion}$) which must be measured and corrected, especially at high dose rates or pulsed beams.
    *   **Diodes (Silicon):**
        *   **Advantages:** Small size (high spatial resolution), high sensitivity, real-time readout.
        *   **Disadvantages:** Energy dependence (response changes with electron energy/depth), dose rate dependence, temperature dependence, radiation damage over time.
        *   **Practical Use:** Useful for relative dosimetry (profiles, output factors) *if* corrections are applied or if energy dependence is minimal over the measurement range. Specific electron diodes are designed to minimize energy dependence.
    *   **Film (Radiographic/Radiochromic):**
        *   **Advantages:** High spatial resolution (2D dosimetry), tissue equivalence (especially radiochromic film like Gafchromic™).
        *   **Disadvantages:** Requires careful calibration, handling, and scanning procedures. Energy dependence can be an issue for radiographic film.
        *   **Practical Use:** Excellent for measuring profiles, flatness/symmetry, especially for small fields, complex cutout shapes, or assessing field matching.

*   **Measurement Geometry:**
    *   **Vertical Beam:** Recommended setup with the beam incident perpendicularly on the phantom surface.
    *   **Waterproof Sleeves:** Required for non-waterproof chambers.
    *   **Scanning Systems:** Automated water tanks are essential for efficient and accurate acquisition of PDDs and profiles.

*   **Corrections (TG-21/TG-25 context, adapted for TG-51):**
    *   **Temperature/Pressure ($P_{TP}$):** Corrects for air density changes in vented ion chambers.
    *   **Ion Recombination ($P_{ion}$):** Corrects for incomplete charge collection, typically measured using the two-voltage technique. More significant in pulsed beams and high dose-rate beams.
    *   **Polarity Effect ($P_{pol}$):** Corrects for differences in reading when positive and negative polarizing voltages are applied. Measured by reversing polarity.
    *   **Electrometer Calibration:** Ensure electrometer is calibrated.
    *   **Chamber Calibration Factor ($N_{gas}$/ $N_D$ / $N_{D,w}^{Co-60}$):** Traceable to a standards laboratory.
    *   **Quality Conversion ($k_Q$) / Stopping Power Ratios ($L/\rho$):** Account for differences between calibration quality (e.g., Co-60) and user's electron beam quality. Handled by $k_Q$ in TG-51.
    *   **Perturbation Factors ($P_{repl}$, $P_{wall}$, $P_{fl}$):** Account for how the chamber itself affects the electron field. Handled implicitly within $k_Q$ in TG-51.
    *   **Gradient Correction ($P_{gr}^Q$):** Specific to TG-51 for cylindrical chambers at $d_{ref}$.

**Practical Workflow:** For PDDs, use a parallel-plate chamber scanned vertically in water. For profiles, use a diode, film, or small ion chamber scanned horizontally. For output factors, use a well-characterized ion chamber (parallel-plate preferred) at $d_{max}$ for each field size/cutout.

## 4. Relative Dosimetry Data Acquisition: Building the TPS Model

TG-25 outlined the essential dataset needed for clinical treatment planning, forming the basis for TPS beam modeling.

*   **PDDs:** Measure for all clinical energies using a range of applicators/field sizes (e.g., 6x6, 10x10, 15x15, 20x20, 25x25 cm²). Use a parallel-plate chamber in water.
*   **Profiles:** Measure for representative energies and field sizes at multiple depths (e.g., surface, $d_{max}$, $R_{90}$, $R_{50}$). This captures the changing penumbra and flatness with depth.
*   **Output Factors (Relative to Reference Field):**
    *   **Applicator Factors:** Measure for all standard applicators.
    *   **Field Size Factors:** Measure for representative square field sizes within applicators.
    *   **Cutout Factors:** Measure for a range of representative custom cutout shapes (squares, rectangles, circles) and sizes relative to the open applicator. This is crucial as scattering from the cutout edges significantly affects output.
*   **SSD Dependence (Inverse Square):** Measure dose variation with distance (e.g., at 90, 100, 110 cm SSD) for representative fields to determine the **virtual or effective SSD ($SSD_{eff}$)**. Electrons do not follow a simple geometric inverse square law due to scattering in the air and collimation system. $SSD_{eff}$ is the apparent source position that best fits the measured data for inverse square corrections. It is typically shorter than the nominal SSD and varies with energy and field size.
    $$ Dose(SSD_2) = Dose(SSD_1) \times \left( \frac{SSD_{eff} + d_{max}}{SSD_1 + d_{max}} \right) \times \left( \frac{SSD_1 + z}{SSD_2 + z} \right) \times \left( \frac{SSD_{eff} + SSD_1}{SSD_{eff} + SSD_2} \right)^2 $$ (Simplified inverse square factor using $SSD_{eff}$ is often used: $ISq = \left( \frac{SSD_{eff} + d_{max}}{SSD_{eff} + d_{max} + gap} \right)^2$ where gap = $SSD_2 - SSD_1$)

**Data Quality:** Consistency, accuracy, and comprehensive coverage of clinical conditions are vital for reliable TPS calculations.

## 5. Treatment Planning Considerations: Clinical Application

TG-25 provided guidance on using electron beams clinically:

*   **Energy Selection:** Choose the lowest energy that provides adequate coverage of the target volume, typically ensuring the 80% or 90% isodose line encompasses the distal target margin, while minimizing dose to deeper tissues.
*   **Field Shaping:** Use standard cones/applicators. Custom blocking (Cerrobend/lead) is essential for conforming the field to the target. Minimum block thickness requirements depend on energy (e.g., $E("MeV")/2 + 1$ mm lead equivalent was a common rule).
*   **Bolus:** Use tissue-equivalent material placed on the skin to:
    *   Increase surface dose.
    *   Conform dose distributions to irregular surfaces.
    *   Decrease the depth of penetration.
    *   *Caution:* Air gaps under bolus can significantly alter dose distribution and must be avoided.
*   **Heterogeneities (Bone, Lung, Air):** TG-25 acknowledged these significantly perturb electron dose distributions due to changes in scattering and stopping power. Simple 1D corrections (like Coefficient of Equivalent Thickness, CET) were known to be inaccurate, especially near interfaces. TG-25 recommended caution, potential use of measurements in phantoms, or applying large margins, reflecting the limitations of algorithms available at the time.
*   **Field Matching:** Matching electron fields to photon fields or other electron fields is challenging due to the broader penumbra of electron beams and the rapid dose fall-off. Techniques like using spoilers, small overlaps/gaps, or specific gantry/collimator angles were discussed, but achieving perfect matches is difficult and requires careful verification.

## 6. Conclusion and Legacy

TG-25 was a pivotal report that established standardized methods and terminology for clinical electron beam dosimetry. While parts related to absolute dosimetry are superseded by TG-51, its detailed discussion of:

*   Electron beam physics and characteristics.
*   Relative dosimetry measurement techniques (especially detector choice and EPOM).
*   Required data for treatment planning.
*   Fundamental clinical considerations.

...remains highly relevant. It provides the essential foundation upon which later reports like TG-70 and MPPG 5.b have built, offering more refined protocols and specific guidance for modern technology. A thorough understanding of TG-25 is invaluable for any physicist working with electron beams.

