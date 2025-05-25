## Deep Dive: IAEA TRS 398 - Absorbed Dose Determination in External Beam Radiotherapy (Detailed Bullet Points)

### Introduction: The Global Standard for Radiotherapy Dosimetry

*   **Purpose and Significance:**
    *   The International Atomic Energy Agency's Technical Reports Series No. 398 (IAEA TRS 398) provides an internationally harmonized and rigorous framework for accurately measuring absorbed dose in external beam radiotherapy.
    *   It serves as the global standard Code of Practice (CoP), adopted worldwide to ensure consistency and accuracy in dosimetry, which is fundamental for effective and safe cancer treatment.
    *   First published in 2000 and subsequently revised (latest revision in 2024 referenced here), it addresses the need for a unified approach.
*   **Core Concept: Absorbed Dose to Water ($D_w$) Calibration:**
    *   TRS 398 represents a paradigm shift from older protocols based on air-kerma calibration coefficients ($N_K$, $N_{gas}$).
    *   It utilizes ionization chambers calibrated directly in terms of absorbed dose to water ($N_{D,w}$), traceable to Primary Standards Dosimetry Laboratories (PSDLs).
    *   This approach significantly reduces uncertainties in dose determination, especially for high-energy photon and electron beams.
*   **Motivation for Development:**
    *   Driven by the availability of $D_w$ calibration standards from PSDLs.
    *   Aimed to harmonize existing national/international protocols (e.g., AAPM TG-21, DIN 6800-2) which often yielded slightly different results due to varying formalisms and data.
*   **Benefits of Harmonization:**
    *   Facilitates international consistency in dose delivery.
    *   Enables more reliable comparison of clinical trial results across different centers and countries.
    *   Ensures patients receive the prescribed dose accurately, irrespective of treatment location.
*   **Broad Applicability:**
    *   Covers a wide range of radiation beam types used in external beam radiotherapy:
        *   High-energy photons (Linacs, Cobalt-60)
        *   High-energy electrons (Linacs)
        *   Low- and medium-energy kilovoltage x-rays
        *   Proton beams
        *   Heavy-ion beams (e.g., Carbon ions)
    *   Makes it a versatile and essential tool for clinical medical physicists.
*   **Focus of this Deep Dive:**
    *   To provide a detailed, practical, and self-contained guide to understanding and implementing TRS 398.
    *   To explore the underlying formalism, specific procedures, required equipment, beam quality specification, correction factors, and uncertainty analysis.
    *   Emphasis on practical application in the clinical setting, explaining the rationale behind procedures and offering insights for daily practice.
    *   Detailed examination of core equations and practical steps for accurate reference dosimetry.


### Scope and Applicability

*   **Broad Coverage:**
    *   TRS 398 provides a comprehensive framework applicable to a wide range of external beam radiotherapy modalities.
    *   It details procedures for determining absorbed dose to water under specific reference conditions.
*   **Beam Types Covered:**
    *   High-energy photon beams (Linacs $\ge$ 4 MV, Cobalt-60).
    *   High-energy electron beams (Linacs, typically 4 MeV to 50 MeV).
    *   Low-energy kilovoltage x-ray beams (typically 40 kV to 100 kV).
    *   Medium-energy kilovoltage x-ray beams (typically 100 kV to 300 kV).
    *   Proton beams (clinical range).
    *   Heavy-ion beams (e.g., Carbon ions, clinical range).
*   **Reference Conditions:**
    *   Crucial for ensuring consistency and comparability of dose measurements globally.
    *   **High-Energy Photons:**
        *   Phantom: Water (minimum size 30x30x30 cm$^3$).
        *   Field Size: 10 cm x 10 cm defined at the reference distance (SSD or SAD).
        *   Reference Depth ($z_{ref}$): 10 g/cm$^2$ (equivalent to 10 cm water depth).
        *   Reference Distance: Typically SSD = 100 cm or SAD = 100 cm.
    *   **High-Energy Electrons:**
        *   Phantom: Water.
        *   Field Size: Usually 10 cm x 10 cm at the phantom surface (SSD=100 cm), though larger fields (e.g., 20x20 cm$^2$) may be used for low energies.
        *   Reference Depth ($z_{ref}$): $z_{ref} = 0.6 R_{50} - 0.1$ cm (where $R_{50}$ is the half-value depth in water).
        *   Reference Distance: Typically SSD = 100 cm.
    *   **Kilovoltage X-rays:**
        *   Reference conditions vary based on energy (low vs. medium) and include measurement free-in-air or at the surface/depth in a phantom.
    *   **Protons/Heavy Ions:**
        *   Specific reference conditions defined, often involving measurement at the center of a spread-out Bragg peak (SOBP) or specific points on the depth dose curve.
*   **Focus on Reference Dosimetry:**
    *   Primary goal is the accurate determination of absorbed dose under these tightly controlled reference conditions.
    *   This establishes the baseline output calibration of the treatment machine (dose per monitor unit or dose per minute).
*   **Foundation for Relative Dosimetry:**
    *   While not explicitly detailing relative dosimetry procedures (PDDs, profiles, output factors), the absolute dose determined via TRS 398 serves as the essential anchor point.
    *   All relative measurements and TPS calculations are normalized to this reference dose value.
*   **Clinical Application:**
    *   Intended for use by qualified medical physicists in clinical settings.
    *   Applies to initial machine commissioning, beam data acquisition for TPS, and periodic absolute dose verification as part of the QA program.

### Formalism Based on Absorbed Dose to Water Calibration ($N_{D,w}$)

*   **Fundamental Shift:**
    *   Moves away from air-kerma based calibration ($N_K$, $N_{gas}$) used in older protocols (e.g., TG-21).
    *   Based on calibration coefficients in terms of absorbed dose to water ($N_{D,w}$). This coefficient ($N_{D,w,Q_0}$) is obtained for a reference beam quality $Q_0$ (usually $^{60}$Co gamma rays) from a PSDL or accredited SSDL.
    *   $N_{D,w,Q_0}$ directly relates the chamber reading (corrected for influence quantities) to the absorbed dose to water under reference conditions in the reference beam.
*   **Core Equation:**
    *   The absorbed dose to water in the user's beam of quality $Q$, $D_{w,Q}$, is determined using:
        $$ D_{w,Q} = M_Q \cdot N_{D,w,Q_0} \cdot k_{Q,Q_0} $$
    *   **$M_Q$**: The fully corrected reading of the ionization chamber in the user's beam $Q$.
        *   $M_Q = M_{raw} \cdot k_{TP} \cdot k_{elec} \cdot k_{pol} \cdot k_s$
        *   $M_{raw}$: Raw chamber reading (charge or current).
        *   $k_{TP}$: Correction for temperature and pressure.
        *   $k_{elec}$: Correction for electrometer calibration (if calibrated separately).
        *   $k_{pol}$: Correction for polarity effect.
        *   $k_s$: Correction for ion recombination.
    *   **$N_{D,w,Q_0}$**: The absorbed dose to water calibration coefficient for the reference quality $Q_0$ (from calibration certificate).
    *   **$k_{Q,Q_0}$**: The crucial beam quality correction factor.
        *   Corrects for the difference in chamber response between the reference beam quality $Q_0$ and the user's beam quality $Q$.
        *   Accounts for variations in chamber construction, materials, and energy response in water.
*   **Beam Quality Correction Factor ($k_{Q,Q_0}$):**
    *   Central to the TRS 398 formalism.
    *   Can be determined experimentally (at standards labs) or calculated theoretically (Monte Carlo, analytical methods).
    *   TRS 398 provides tabulated values of $k_{Q,Q_0}$ for numerous common ionization chamber types and a wide range of beam qualities $Q$.
    *   Accurate determination of the user's beam quality $Q$ is essential to select the correct $k_{Q,Q_0}$.
*   **Advantages of the Formalism:**
    *   Simplifies the dosimetry process compared to air-kerma protocols.
    *   Eliminates the need for several intermediate conversion factors (e.g., stopping power ratios, perturbation factors) previously required.
    *   Reduces the overall uncertainty in the final absorbed dose determination.



### Beam Quality Specification

*   **Importance:**
    *   Accurately determining the user's beam quality ($Q$) is essential for selecting the correct beam quality correction factor $k_{Q,Q_0}$ from TRS 398 tables.
    *   The protocol specifies different practical indices for different beam types that correlate well with the chamber's energy response.
*   **High-Energy Photon Beams (including $^{60}$Co):**
    *   **Index:** Tissue-phantom ratio, $TPR_{20,10}$.
    *   **Definition:** Ratio of absorbed doses measured at depths of 20 cm and 10 cm in a water phantom ($D_{20}/D_{10}$).
    *   **Measurement Conditions:** Constant source-detector distance (SDD), 10 cm x 10 cm field size at the detector plane.
    *   **Rationale:** $TPR_{20,10}$ is sensitive to the mean energy of the photon spectrum and relatively independent of electron contamination.
    *   **Practical Measurement:** Use an ionization chamber, considering its effective point of measurement ($P_{eff}$), especially at 20 cm depth due to potential dose gradients.
    *   **TRS 398 Data:** Provides $k_{Q,Q_0}$ values tabulated as a function of $TPR_{20,10}$ for various cylindrical and parallel-plate chambers.
*   **High-Energy Electron Beams:**
    *   **Index:** Half-value depth in water, $R_{50}$.
    *   **Definition:** Depth in water (in cm or g/cm$^2$) at which the absorbed dose falls to 50% of its maximum value along the central axis depth dose curve.
    *   **Relationship to Energy:** $R_{50}$ is directly related to the mean energy of the electrons at the phantom surface ($E_0 \approx 2.33 \cdot R_{50}$ MeV is a common approximation).
    *   **Measurement:** Determined from a measured percentage depth dose (PDD) curve in a water phantom using an appropriate detector (parallel-plate chamber preferred, diode acceptable).
    *   **Reference Conditions for PDD:** Typically 10 cm x 10 cm field size at SSD=100 cm (though larger fields may be needed for low energies to achieve lateral scatter equilibrium).
    *   **TRS 398 Data:** Provides $k_{Q,Q_0}$ (often denoted $k_Q$ for electrons) values tabulated as a function of $R_{50}$ for different chamber types.
*   **Kilovoltage X-ray Beams:**
    *   **Index:** Half-value layer (HVL) measured in aluminum (Al) for low-energy beams or copper (Cu) for medium-energy beams.
    *   **Additional Specifier:** Peak generating potential (kVp) is also required.
    *   **Measurement:** HVL is determined experimentally by measuring beam attenuation through known thicknesses of Al or Cu filters under narrow beam geometry.
*   **Proton and Heavy-Ion Beams:**
    *   **Index:** Often the residual range ($R_{res}$) in water.
    *   **Definition:** $R_{res} = R_p - z$, where $R_p$ is the practical range and $z$ is the measurement depth.
    *   Alternatively, $R_{p}$ itself or parameters related to the Spread-Out Bragg Peak (SOBP) width might be used.

### Correction Factors: Accounting for Influence Quantities

*   **Purpose:** To correct the raw chamber reading ($M_{raw}$) for influences unrelated to absorbed dose, ensuring the corrected reading ($M_Q$) accurately reflects charge collected under reference conditions.
*   **Temperature and Pressure Correction ($k_{TP}$):**
    *   **Reason:** Corrects for variations in the mass of air in the chamber's sensitive volume due to deviations from reference temperature ($T_0$) and pressure ($P_0$).
    *   **Formula:**
        $$ k_{TP} = \frac{(273.15 + T)}{(273.15 + T_0)} \cdot \frac{P_0}{P} $$
    *   $T, P$: Ambient temperature ($^\circ$C) and pressure (kPa or mbar) during measurement.
    *   $T_0, P_0$: Reference temperature and pressure from the calibration certificate (e.g., $20^\circ$C or $22^\circ$C, $101.325$ kPa).
    *   **Requirement:** Accurate, calibrated thermometer and barometer are essential.
*   **Polarity Effect Correction ($k_{pol}$):**
    *   **Reason:** Corrects for potential small differences in chamber reading depending on the polarity (+ or -) of the collecting voltage.
    *   **Measurement:** Measure readings with both positive ($M_+$) and negative ($M_-$) polarizing voltages (using absolute magnitudes).
    *   **Formula:**
        $$ k_{pol} = \frac{|M_+| + |M_-|}{2 \cdot M} $$
    *   $M$: Reading obtained with the polarity routinely used (must match calibration polarity).
    *   **Significance:** Usually close to 1.000, but should be measured during commissioning and checked periodically, especially for parallel-plate chambers in electron beams.
*   **Ion Recombination Correction ($k_s$):**
    *   **Reason:** Corrects for incomplete collection of ions due to recombination at high dose rates or dose-per-pulse.
    *   **Dependence:** Varies with dose rate/dose-per-pulse, chamber geometry, and applied voltage.
    *   **Determination (Two-Voltage Method):**
        *   Measure readings at normal voltage $V_1$ ($M_1$) and a lower voltage $V_2$ ($M_2$).
        *   **Pulsed Beams (Linacs):**
            $$ k_s = a_0 + a_1 \left( \frac{M_1}{M_2} \right) + a_2 \left( \frac{M_1}{M_2} \right)^2 $$
            (Coefficients $a_0, a_1, a_2$ depend on $V_1/V_2$ ratio, provided in TRS 398).
        *   **Continuous Beams ($^{60}$Co):**
            $$ k_s = \frac{(V_1/V_2)^2 - 1}{(V_1/V_2)^2 - (M_1/M_2)} $$
            (Assumes linear voltage dependence in the near-saturation region).
    *   **Importance:** Crucial for high dose-per-pulse beams (e.g., FFF) and electron beams. Should be determined at the highest relevant dose rate.
*   **Electrometer Calibration Factor ($k_{elec}$):**
    *   **Reason:** Corrects for any deviation of the electrometer reading from the true charge or current.
    *   **Applicability:** Only needed if the electrometer is calibrated separately from the ionization chamber.
    *   **Common Practice:** Often, the chamber and electrometer are calibrated together as a system, making $k_{elec} = 1.000$ as it's implicitly included in $N_{D,w,Q_0}$.



### Reference Dosimetry Procedures: Practical Steps

*   **General Workflow:**
    *   Set up reference conditions (phantom, field size, distance, depth).
    *   Measure the appropriate beam quality index ($TPR_{20,10}$ or $R_{50}$).
    *   Select the appropriate calibrated ionization chamber.
    *   Position the chamber correctly at the reference depth, considering $P_{eff}$.
    *   Take raw readings ($M_{raw}$).
    *   Apply all necessary correction factors ($k_{TP}, k_{pol}, k_s, k_{elec}$) to get $M_Q$.
    *   Select the correct $N_{D,w,Q_0}$ from the calibration certificate.
    *   Select the correct $k_{Q,Q_0}$ from TRS 398 tables based on beam quality and chamber type.
    *   Calculate the absorbed dose to water $D_{w,Q}$ using the core equation.
*   **High-Energy Photon Beams (e.g., Linac MV beams, $^{60}$Co):**
    *   **Setup:** Water phantom (>=30x30x30 cm$^3$), 10x10 cm$^2$ field at SAD/SSD=100 cm, $z_{ref}$=10 cm depth.
    *   **Beam Quality:** Measure $TPR_{20,10}$.
    *   **Chamber:** Calibrated cylindrical chamber (e.g., Farmer type) recommended.
    *   **Positioning:** Place chamber with its effective point of measurement ($P_{eff}$, typically shifted 0.6 * radius upstream) at $z_{ref}$=10 cm.
    *   **Measurement:** Obtain corrected reading $M_Q$.
    *   **Factors:** Use $N_{D,w,^{60}Co}$ and $k_{Q,^{60}Co}$ based on measured $TPR_{20,10}$.
    *   **Calculation:** $D_{w,Q} = M_Q \cdot N_{D,w,^{60}Co} \cdot k_{Q,^{60}Co}$. This gives dose rate (cGy/MU or cGy/min) at 10 cm depth.
*   **High-Energy Electron Beams:**
    *   **Setup:** Water phantom, typically 10x10 cm$^2$ field at SSD=100 cm (larger fields for low E possible).
    *   **Beam Quality:** Measure PDD curve to determine $R_{50}$.
    *   **Chamber:** Parallel-plate chamber preferred (especially low E); cylindrical usable with appropriate $P_{eff}$ and $k_{Q,Q_0}$.
    *   **Reference Depth:** $z_{ref} = 0.6 R_{50} - 0.1$ cm.
    *   **Positioning:** Place chamber with its effective point of measurement ($P_{eff}$, typically front surface for PP chambers) at $z_{ref}$.
    *   **Measurement:** Obtain corrected reading $M_Q$.
    *   **Factors:** Use $N_{D,w,^{60}Co}$ and $k_{Q}$ (electron beam quality correction factor, often relative to $^{60}$Co) based on measured $R_{50}$.
    *   **Calculation:** $D_{w,Q}(z_{ref}) = M_Q \cdot N_{D,w,^{60}Co} \cdot k_{Q}$.
    *   **Dose at $z_{max}$:** If dose at maximum depth ($z_{max}$) is needed, use the measured PDD curve to transfer the dose: $D_{w,Q}(z_{max}) = D_{w,Q}(z_{ref}) / (\%DD(z_{ref})/100)$.
*   **Kilovoltage X-rays, Protons, Heavy Ions:**
    *   Follow specific procedures detailed in TRS 398 for these modalities, involving different reference conditions, beam quality indices (HVL, $R_{res}$), chamber types (often parallel-plate), and specific $k_{Q,Q_0}$ data.

### Calibration Traceability and the Role of Standards Laboratories

*   **Foundation of Accuracy:** The entire TRS 398 system relies on the accuracy and traceability of the $N_{D,w,Q_0}$ calibration coefficient.
*   **Hierarchy of Laboratories:**
    *   **Primary Standards Dosimetry Laboratories (PSDLs):**
        *   Maintain primary standards for absorbed dose (e.g., water calorimetry, Fricke dosimetry) with lowest uncertainties.
        *   Examples: NIST (USA), NPL (UK), PTB (Germany), BIPM (International).
        *   Provide direct $N_{D,w,Q_0}$ calibrations for reference chambers.
    *   **Secondary Standards Dosimetry Laboratories (SSDLs):**
        *   Maintain secondary standard dosimeters calibrated against primary standards at a PSDL.
        *   Provide traceable $N_{D,w,Q_0}$ calibrations for user/field instruments in hospitals.
        *   Often operate at national/regional level.
        *   IAEA/WHO Network of SSDLs ensures global consistency and access, especially where PSDLs are unavailable.
*   **Traceability Chain:** User Chamber $\rightarrow$ SSDL $\rightarrow$ PSDL $\rightarrow$ International Measurement System.
*   **Calibration Certificate:**
    *   Provides the $N_{D,w,Q_0}$ value for a specific chamber/electrometer system at quality $Q_0$ (usually $^{60}$Co) under stated reference conditions (T, P).
    *   Includes the uncertainty associated with the calibration factor.
    *   Crucial to use the chamber with the specified electrometer (or apply $k_{elec}$) and under consistent conditions.
*   **Recalibration:**
    *   Essential to maintain traceability and long-term accuracy.
    *   Typical frequency: Every 2 years.
    *   Required sooner if chamber is repaired, damaged, or shows inconsistent behavior in QA checks.

### Uncertainty Analysis in TRS 398 Dosimetry

*   **Advantage of TRS 398:** Significantly reduces overall uncertainty compared to older air-kerma protocols by eliminating intermediate conversion factors.
*   **Framework:** Follows ISO Guide to the Expression of Uncertainty in Measurement (GUM).
*   **Uncertainty Types:**
    *   **Type A:** Evaluated by statistical methods (e.g., standard deviation of repeated measurements).
    *   **Type B:** Evaluated by other means (e.g., calibration certificates, specifications, scientific judgment).
*   **Combined Standard Uncertainty ($u_c$):** Calculated by combining individual uncertainty components in quadrature (square root of sum of squares). Represents k=1 or ~68% confidence level.
*   **Major Uncertainty Components in $D_{w,Q} = M_Q \cdot N_{D,w,Q_0} \cdot k_{Q,Q_0}$:**
    *   **$N_{D,w,Q_0}$:** Uncertainty from the calibration certificate (Type B, typically 0.5-0.7%).
    *   **$k_{Q,Q_0}$:** Uncertainty in the tabulated beam quality correction factor (Type B, depends on chamber/beam, typically 0.5-1.0%). Derived from uncertainties in underlying data/calculations.
    *   **$M_Q$ (Corrected Reading):** Combined uncertainty from multiple sources:
        *   Long-term stability of chamber/electrometer (Type B).
        *   Measurement repeatability (charge collection) (Type A).
        *   Chamber positioning accuracy (Type A/B).
        *   Phantom setup (Type B).
        *   $k_{TP}$ (uncertainty in T and P measurements) (Type A/B).
        *   $k_{pol}$ (measurement uncertainty) (Type A).
        *   $k_s$ (measurement uncertainty, model accuracy) (Type A/B).
        *   Beam quality determination ($TPR_{20,10}$ or $R_{50}$) (Type A/B).
*   **Typical Combined Standard Uncertainties (k=1):**
    *   High-Energy Photons: ~1.0%
    *   Electrons: ~1.2%
    *   (Note: Expanded uncertainty (k=2, ~95% confidence) is roughly double these values).
*   **Achieving Low Uncertainty:** Requires meticulous technique, calibrated equipment, adherence to protocol, and qualified personnel.

### Integration into the Clinical Workflow

*   **Foundation, Not Isolation:** TRS 398 reference dosimetry is the cornerstone of the entire clinical dosimetry workflow.
*   **Treatment Planning System (TPS) Calibration:**
    *   The accurately determined reference dose rate (cGy/MU or cGy/min) from TRS 398 is the primary input for TPS beam calibration.
    *   All relative dose distributions (PDDs, profiles, output factors) measured during commissioning are normalized to this absolute dose value at the reference point.
    *   Errors in reference dosimetry lead to systematic errors in TPS calculations and patient doses.
*   **Machine Commissioning:**
    *   TRS 398 dosimetry is performed for all beams/energies during linac commissioning to establish baseline output.
    *   These absolute dose values, along with relative dose data, are used to configure and validate the TPS beam model.
*   **Routine Quality Assurance (QA):**
    *   TRS 398 provides the traceable standard for routine QA output checks (daily, monthly, annual).
    *   QA devices (e.g., daily check devices, monthly QA phantoms/chambers) are typically cross-calibrated against the reference chamber calibrated via TRS 398.
    *   Ensures long-term stability and consistency of machine output relative to the initial TRS 398 calibration.
    *   Deviations beyond tolerance levels (e.g., +/- 2% monthly/annually) trigger investigation and potential recalibration using the full TRS 398 protocol.
*   **Overall Impact:** Ensures accuracy and consistency from initial calibration through treatment planning to ongoing delivery verification.

### Practical Considerations and Recommendations

*   **Chamber Selection:**
    *   Use appropriate chamber type for the beam modality (cylindrical for MV photons/high-E electrons; parallel-plate for electrons (esp. low E) / kV X-rays).
    *   Ensure chamber is well-guarded.
    *   Must have a valid, traceable $N_{D,w,Q_0}$ calibration certificate.
    *   Check chamber condition (no damage, stable response).
*   **Phantom Setup:**
    *   Use a water phantom of sufficient size (>= 5 cm margin beyond field edges).
    *   Ensure water purity and temperature stability (measure T accurately).
    *   Use waterproof sleeve for chamber; check for air gaps/bubbles.
    *   Precise positioning using phantom markings and linac lasers is critical.
*   **Chamber Positioning:**
    *   Accurately position the chamber at the reference depth ($z_{ref}$).
    *   Crucially, position the *effective point of measurement* ($P_{eff}$) at $z_{ref}$.
        *   Photons (cylindrical): $P_{eff}$ shifted upstream by 0.6 * radius.
        *   Electrons (cylindrical): $P_{eff}$ shifted upstream by 0.5 * radius.
        *   Electrons (parallel-plate): $P_{eff}$ typically at the center of the inner surface of the entrance window.
*   **Measurement Procedures:**
    *   Allow adequate warm-up time for chamber and electrometer.
    *   Check electrometer leakage and chamber leakage (if applicable).
    *   Pre-irradiate the chamber according to recommendations.
    *   Measure $k_{pol}$ and $k_s$ under relevant conditions (esp. commissioning).
    *   Use calibrated thermometer and barometer for $k_{TP}$.
    *   Take multiple readings to assess stability and average.
*   **Cross-Calibration:**
    *   Establish procedures for cross-calibrating routine QA instruments against the TRS 398 calibrated reference chamber.
    *   Perform cross-calibration in a stable reference beam (e.g., $^{60}$Co or high-energy photon beam).
*   **Documentation:**
    *   Maintain meticulous records of all measurements, setup conditions, correction factors, calculations, results, and uncertainties.
    *   Essential for traceability, QA, troubleshooting, and regulatory compliance.

### Conclusion: The Gold Standard for Clinical Dosimetry

*   **Status:** IAEA TRS 398 is the international gold standard for reference dosimetry in external beam radiotherapy.
*   **Core Strength:** Formalism based on absorbed dose to water calibration ($N_{D,w}$) provides a direct, robust, and accurate method.
*   **Accuracy:** Reduces uncertainties compared to older protocols, achieving typical combined standard uncertainties (k=1) of ~1.0% (photons) and ~1.2% (electrons).
*   **Comprehensiveness:** Covers all common radiotherapy beam modalities with clear procedures and internationally consistent data ($k_{Q,Q_0}$).
*   **Implementation:** Requires meticulous technique, calibrated equipment, and qualified medical physicists.
*   **Clinical Role:** Indispensable foundation for accurate TPS commissioning, dose calculation, and ongoing delivery QA, ensuring patient safety and treatment efficacy.
