# AAPM TG-61 Kilovoltage Dosimetry

## Historical Context and Purpose

The American Association of Physicists in Medicine (AAPM) Task Group 61 (TG-61) was formed to address the need for standardized dosimetry protocols for kilovoltage (40-300 kV) x-ray beams used in radiotherapy. Prior to the publication of the TG-61 report in 2001, there was significant variability in dosimetry practices for these beams, leading to inconsistencies in dose delivery across institutions.

The primary purposes of TG-61 were to:
1. Establish a comprehensive dosimetry protocol for kilovoltage x-ray beams
2. Provide a consistent methodology for determining absorbed dose to water
3. Standardize measurement techniques and correction factors
4. Address the unique challenges of kilovoltage beam dosimetry

Kilovoltage x-ray beams have historically been used for treating superficial lesions and continue to play an important role in modern radiotherapy for specific applications such as skin cancer treatment, intraoperative radiotherapy, and certain benign conditions. The TG-61 protocol remains the standard for kilovoltage dosimetry in North America, though it has been supplemented by international protocols such as IAEA TRS-398.

## Kilovoltage X-ray Beam Characteristics

### Beam Quality Specification

Kilovoltage x-ray beams are characterized by their beam quality, which is specified differently than for megavoltage beams:

1. **Half-Value Layer (HVL)**: The primary beam quality specifier for kilovoltage beams is the half-value layer, defined as the thickness of a specified material (typically aluminum or copper) required to reduce the air kerma rate to 50% of its original value. HVL is expressed in mm Al or mm Cu.

2. **Generating Potential**: The tube potential in kilovolts (kV) is also used to categorize beams:
   - Grenz rays: 10-20 kV
   - Contact therapy: 40-50 kV
   - Superficial therapy: 50-150 kV
   - Orthovoltage therapy: 150-300 kV

3. **Beam Quality Index Relationship**: The relationship between HVL and generating potential is complex and depends on:
   - Inherent filtration of the x-ray tube
   - Added filtration
   - Target material and angle
   - Tube design

### Energy Spectrum

The energy spectrum of kilovoltage x-ray beams differs significantly from megavoltage beams:

1. **Continuous Bremsstrahlung Spectrum**: The primary component is a continuous spectrum with maximum energy equal to the generating potential (kVp).

2. **Characteristic Radiation**: Discrete energy peaks corresponding to characteristic x-rays from the target material (typically tungsten).

3. **Filtration Effects**: 
   - Inherent filtration (tube window, oil, etc.) typically 0.5-1.0 mm Al equivalent
   - Added filtration (Al, Cu, Sn, etc.) shapes the beam spectrum
   - Total filtration increases the effective energy and HVL

4. **Beam Hardening**: As the beam penetrates tissue, lower energy photons are preferentially absorbed, increasing the effective energy with depth.

### Depth Dose Characteristics

Kilovoltage beams exhibit distinct depth dose characteristics:

1. **Rapid Dose Fall-off**: Dose decreases rapidly with depth due to the predominance of photoelectric absorption.

2. **Surface Dose**: Very high surface dose (80-100% of maximum) compared to megavoltage beams.

3. **Depth of Maximum Dose (d<sub>max</sub>)**:
   - For lower energies (<100 kV): At or very near the surface
   - For higher energies (150-300 kV): Typically 1-5 mm below the surface

4. **Percentage Depth Dose (PDD)**: Varies significantly with:
   - Beam quality (HVL)
   - Field size
   - Source-to-surface distance (SSD)
   - Measurement medium

5. **Backscatter Contribution**: Significant contribution to dose from backscattered radiation, which is highly dependent on field size and beam energy.

## Dosimetry Formalisms

### In-Air Method

The in-air method determines absorbed dose to water by measuring air kerma free-in-air and applying appropriate conversion factors:

1. **Measurement Setup**:
   - Chamber positioned free-in-air at the reference point
   - Buildup cap may be used to provide electronic equilibrium
   - Minimal scatter from surroundings

2. **Formalism**:
   $D_{w,z=0} = M \times N_K \times B_w \times \left[ \frac{\bar{\mu}_{en}}{\rho} \right]_{air}^{water} \times P_{stem,air} \times P_{chamber}$

   Where:
   - $D_{w,z=0}$ is the absorbed dose to water at the surface
   - $M$ is the corrected chamber reading
   - $N_K$ is the air kerma calibration factor
   - $B_w$ is the backscatter factor
   - $\left[ \frac{\bar{\mu}_{en}}{\rho} \right]_{air}^{water}$ is the ratio of mass energy absorption coefficients
   - $P_{stem,air}$ is the stem correction factor
   - $P_{chamber}$ accounts for chamber-specific corrections

3. **Advantages**:
   - Simpler setup
   - Less sensitive to positioning errors
   - Directly traceable to air kerma standards

4. **Limitations**:
   - Requires accurate backscatter factors
   - Chamber stem effects can be significant
   - Buildup cap considerations for higher energies

### In-Phantom Method

The in-phantom method determines absorbed dose to water by measuring with the chamber in a water or water-equivalent phantom:

1. **Measurement Setup**:
   - Chamber positioned in water or water-equivalent phantom
   - Reference depth typically 2 cm for orthovoltage beams
   - Chamber must be waterproof or in a waterproof sleeve

2. **Formalism**:
   $D_{w,z=z_{ref}} = M \times N_{K} \times P_{sheath} \times P_{chamber} \times \left[ \frac{\bar{\mu}_{en}}{\rho} \right]_{air}^{water} \times P_{displacement} \times P_{gr}$

   Where:
   - $D_{w,z=z_{ref}}$ is the absorbed dose to water at the reference depth
   - $M$ is the corrected chamber reading
   - $N_K$ is the air kerma calibration factor
   - $P_{sheath}$ accounts for the waterproofing sleeve
   - $P_{chamber}$ accounts for chamber-specific corrections
   - $\left[ \frac{\bar{\mu}_{en}}{\rho} \right]_{air}^{water}$ is the ratio of mass energy absorption coefficients
   - $P_{displacement}$ accounts for the displacement of water by the chamber
   - $P_{gr}$ accounts for gradient effects

3. **Advantages**:
   - More direct measurement of dose in phantom
   - No need for backscatter factors
   - More representative of clinical setup

4. **Limitations**:
   - More sensitive to positioning errors
   - Requires waterproofing
   - Chamber perturbation effects can be significant

### Correction Factors

Several correction factors are required for accurate kilovoltage dosimetry:

1. **Temperature and Pressure Correction ($P_{TP}$)**:
   $P_{TP} = \frac{273.15 + T}{293.15} \times \frac{101.325}{P}$
   
   Where T is in °C and P is in kPa.

2. **Ion Recombination Correction ($P_{ion}$)**:
   Typically small for kilovoltage beams (within 0.5%) but should be verified.

3. **Polarity Correction ($P_{pol}$)**:
   $P_{pol} = \frac{|M_+| + |M_-|}{2|M|}$
   
   Where $M_+$ and $M_-$ are readings with positive and negative polarity.

4. **Humidity Correction**:
   Typically negligible if chamber is calibrated and used between 20-80% relative humidity.

5. **Stem Effect Correction ($P_{stem,air}$)**:
   Accounts for irradiation of the chamber stem in air measurements.

6. **Chamber Correction ($P_{chamber}$)**:
   Accounts for differences between the user's chamber and the reference chamber.

7. **Displacement Correction ($P_{displacement}$)**:
   Accounts for the displacement of water by the air cavity of the chamber.

8. **Gradient Correction ($P_{gr}$)**:
   Accounts for the dose gradient across the chamber volume.

## Chamber Selection and Calibration

### Chamber Types for Kilovoltage Dosimetry

The choice of ionization chamber is critical for accurate kilovoltage dosimetry:

1. **Parallel-Plate Chambers**:
   - Recommended for low-energy beams (<100 kV)
   - Minimal energy dependence when properly designed
   - Examples: Exradin A11, PTW 23342, Markus chamber

2. **Cylindrical Chambers**:
   - Suitable for medium to high-energy kilovoltage beams (>100 kV)
   - Farmer-type chambers generally acceptable
   - Examples: Exradin A12, PTW 30013, NE 2571

3. **Chamber Characteristics to Consider**:
   - Wall material and thickness
   - Energy response
   - Collection volume
   - Stem design
   - Leakage current
   - Stability

### Calibration Requirements

Proper chamber calibration is essential:

1. **Calibration Beam Qualities**:
   - Ideally, calibration at multiple beam qualities spanning the clinical range
   - Minimum: calibration at qualities close to clinical beams
   - Interpolation between calibration points when necessary

2. **Calibration Coefficients**:
   - Air kerma calibration factor ($N_K$)
   - Calibration traceable to primary standards laboratory
   - Calibration valid for specific chamber model and serial number

3. **Calibration Frequency**:
   - Recommended: Every 2 years
   - After repair or suspected damage
   - After significant environmental changes

4. **Cross-Calibration**:
   - When direct calibration is not available
   - Requires reference chamber with known calibration
   - Same beam quality and measurement conditions

## Measurement Procedures

### Equipment Requirements

Proper equipment is necessary for accurate kilovoltage dosimetry:

1. **Ionization Chamber**:
   - Appropriate for beam energy range
   - Recent calibration
   - Stable response

2. **Electrometer**:
   - Capable of measuring low currents (pA range)
   - Stable bias voltage supply
   - Recent calibration

3. **Phantoms**:
   - Water phantom (preferred)
   - Solid water-equivalent phantom (acceptable alternative)
   - PMMA (not recommended due to density differences)

4. **Ancillary Equipment**:
   - Thermometer (±0.5°C accuracy)
   - Barometer (±0.5 kPa accuracy)
   - Hygrometer (if humidity corrections applied)
   - Positioning system (±0.5 mm accuracy)

### In-Air Measurement Procedure

Step-by-step procedure for the in-air method:

1. **Chamber Setup**:
   - Position chamber at reference point in air
   - For E > 100 kV, use appropriate buildup cap
   - Align chamber axis perpendicular to beam axis
   - Ensure minimal scatter from surroundings

2. **Reference Conditions**:
   - 100 cm SSD (or clinical SSD)
   - Reference field size (typically 10×10 cm²)
   - Chamber at central axis

3. **Measurement Process**:
   - Record temperature and pressure
   - Apply appropriate bias voltage
   - Allow stabilization (≥ 5 minutes)
   - Take multiple readings (≥ 3)
   - Measure leakage and subtract if significant
   - Measure with both polarities if necessary

4. **Data Analysis**:
   - Apply all correction factors
   - Calculate absorbed dose using in-air formalism
   - Estimate measurement uncertainty

### In-Phantom Measurement Procedure

Step-by-step procedure for the in-phantom method:

1. **Phantom Setup**:
   - Water phantom or solid water phantom
   - Minimum dimensions: 30×30×30 cm³
   - Level and aligned with beam

2. **Chamber Setup**:
   - Waterproof chamber or sleeve
   - Position at reference depth (typically 2 cm)
   - Align chamber axis perpendicular to beam axis
   - Ensure proper buildup and backscatter

3. **Reference Conditions**:
   - 100 cm SSD (or clinical SSD)
   - Reference field size (typically 10×10 cm²)
   - Chamber at central axis

4. **Measurement Process**:
   - Record temperature and pressure
   - Apply appropriate bias voltage
   - Allow stabilization (≥ 5 minutes)
   - Take multiple readings (≥ 3)
   - Measure leakage and subtract if significant
   - Measure with both polarities if necessary

5. **Data Analysis**:
   - Apply all correction factors
   - Calculate absorbed dose using in-phantom formalism
   - Estimate measurement uncertainty

## Backscatter Factors and Mass Energy Absorption Coefficients

### Backscatter Factors ($B_w$)

Backscatter factors are critical for the in-air method:

1. **Definition**:
   - Ratio of dose at the surface of a phantom to dose at the same point in free space
   - Accounts for radiation scattered back from the phantom

2. **Dependencies**:
   - Beam quality (HVL)
   - Field size
   - Field shape
   - SSD (minor effect)

3. **Tabulated Values**:
   - TG-61 provides tables for various HVLs and field sizes
   - Interpolation required for intermediate values
   - Extrapolation not recommended

4. **Measurement**:
   - When tabulated values not available
   - Requires in-air and surface measurements
   - Careful setup to minimize uncertainties

### Mass Energy Absorption Coefficients

Mass energy absorption coefficients convert air kerma to absorbed dose:

1. **Definition**:
   - $\left[ \frac{\bar{\mu}_{en}}{\rho} \right]_{air}^{water}$ is the ratio of mass energy absorption coefficients averaged over the photon spectrum

2. **Dependencies**:
   - Beam quality (HVL)
   - Depth in phantom (for in-phantom method)
   - Field size (minor effect)

3. **Tabulated Values**:
   - TG-61 provides tables for various HVLs
   - Separate tables for in-air and in-phantom methods
   - Interpolation required for intermediate values

4. **Calculation**:
   - Requires knowledge of photon spectrum
   - Monte Carlo simulations for complex geometries
   - Published data for standard conditions

## Clinical Implementation

### Beam Calibration Workflow

A systematic approach to clinical implementation:

1. **Initial Setup**:
   - Determine beam qualities (HVL measurement)
   - Select appropriate chamber
   - Choose dosimetry method (in-air or in-phantom)

2. **Reference Dosimetry**:
   - Perform calibration at reference conditions
   - Calculate absorbed dose to water
   - Establish baseline output factors

3. **Relative Dosimetry**:
   - Measure PDD curves
   - Determine output factors for clinical field sizes
   - Create isodose distributions

4. **Treatment Planning**:
   - Implement beam data in treatment planning system
   - Validate dose calculations
   - Establish QA procedures

### Output Calibration

Establishing the output calibration for clinical use:

1. **Calibration Point**:
   - Surface for most kilovoltage treatments
   - Reference depth for deeper treatments

2. **Output Specification**:
   - Gy/min at reference conditions
   - Gy/MU for newer units with monitor chambers
   - Conversion to clinical setup

3. **Monitor Unit Calculation**:
   - $MU = \frac{Prescribed\,Dose}{Dose\,Rate} \times \frac{1}{PDD} \times \frac{1}{OF} \times \frac{1}{CF}$
   
   Where:
   - PDD is the percentage depth dose
   - OF is the output factor
   - CF includes other correction factors

4. **Documentation**:
   - Detailed record of calibration procedure
   - All correction factors applied
   - Estimated uncertainty
   - Calibration date and validity period

### Clinical Applications

Major clinical applications of kilovoltage x-ray therapy:

1. **Superficial Treatments**:
   - Skin cancers (basal cell, squamous cell)
   - Keloids
   - Benign skin conditions

2. **Orthovoltage Treatments**:
   - Skin cancers with deeper invasion
   - Palliative treatment of bone metastases
   - Certain benign conditions (plantar fasciitis, etc.)

3. **Intraoperative Radiotherapy**:
   - Specialized kilovoltage units (e.g., INTRABEAM)
   - Breast cancer applications
   - Requires specific dosimetry procedures

4. **Total Skin Electron Therapy Boost**:
   - Supplemental treatment for mycosis fungoides
   - Treatment of specific lesions

### Treatment Planning Considerations

Special considerations for kilovoltage treatment planning:

1. **Dose Calculation Algorithms**:
   - Simple calculation methods often used
   - Correction-based algorithms
   - Monte Carlo for complex situations

2. **Heterogeneity Corrections**:
   - Critical due to photoelectric effect dependence on atomic number
   - Bone interfaces (dose enhancement)
   - Air cavities (dose reduction)
   - Metal implants (significant dose perturbation)

3. **Field Shaping**:
   - Lead cutouts
   - Custom shielding
   - Accounting for penumbra

4. **Treatment Verification**:
   - Portal imaging options limited
   - Surfac
(Content truncated due to size limit. Use line ranges to read in chunks)