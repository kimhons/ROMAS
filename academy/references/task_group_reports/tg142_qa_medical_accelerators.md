# AAPM TG-142: Quality Assurance of Medical Accelerators

## Introduction and Historical Context

### Purpose and Scope of TG-142

The American Association of Physicists in Medicine (AAPM) Task Group 142 (TG-142) report provides comprehensive recommendations for quality assurance (QA) of medical linear accelerators (linacs). Published in 2009 as an update to the earlier TG-40 report, TG-142 addresses the evolution of linac technology and the increasing complexity of modern radiotherapy techniques.

The primary objectives of TG-142 are to:

1. Establish a comprehensive framework for linac QA programs
2. Define appropriate test frequencies and tolerance limits
3. Address QA requirements for advanced treatment techniques
4. Provide guidance for maintaining safe and accurate treatment delivery

TG-142 recognizes that different treatment techniques have different accuracy requirements. Therefore, the report establishes three distinct categories of linacs based on their clinical use:
- Standard linacs (non-IMRT, non-stereotactic)
- IMRT-capable linacs
- Stereotactic-capable linacs (SRS/SBRT)

### Evolution from TG-40 to TG-142

The progression from TG-40 (published in 1994) to TG-142 reflects significant technological advancements in radiation therapy:

1. **Technological Advancements**:
   - Introduction of multileaf collimators (MLCs)
   - Development of intensity-modulated radiation therapy (IMRT)
   - Implementation of image-guided radiation therapy (IGRT)
   - Adoption of stereotactic radiosurgery/radiotherapy (SRS/SBRT)
   - Integration of volumetric imaging (CBCT, MV-CT)

2. **Key Differences from TG-40**:
   - More comprehensive test recommendations
   - Technique-specific tolerance tables
   - Expanded MLC QA requirements
   - Addition of imaging device QA
   - Increased emphasis on geometric accuracy
   - Introduction of process-based QA concepts

3. **Regulatory Context**:
   - Increased regulatory scrutiny following high-profile accidents
   - Greater emphasis on patient safety
   - Development of more stringent accreditation requirements
   - Integration with broader quality management systems

## Quality Assurance Framework

### Fundamental Principles

TG-142 is built upon several fundamental principles of quality assurance:

1. **Safety First**: Ensuring patient and staff safety is the primary objective
2. **Risk-Based Approach**: Test frequencies and tolerances based on potential impact of failures
3. **Consistency**: Standardized procedures to ensure reproducible results
4. **Documentation**: Comprehensive record-keeping of all QA activities
5. **Continuous Improvement**: Regular review and refinement of QA processes

### QA Program Structure

A comprehensive QA program following TG-142 guidelines includes:

1. **Hierarchical Testing Schedule**:
   - Daily QA: Basic safety and performance checks
   - Monthly QA: More detailed mechanical and dosimetric tests
   - Annual QA: Comprehensive evaluation of all parameters
   - Patient-specific QA: Verification of individual treatment plans

2. **Documentation Requirements**:
   - Baseline values established at commissioning
   - Written procedures for all tests
   - Records of all QA activities
   - Investigation and resolution of out-of-tolerance results
   - Regular review of QA program effectiveness

3. **Personnel Responsibilities**:
   - Medical physicists: Overall program design and oversight
   - Medical dosimetrists: Plan-specific QA
   - Radiation therapists: Daily QA
   - Service engineers: Preventive maintenance and repairs
   - Radiation oncologists: Clinical decision-making based on QA results

4. **Equipment Requirements**:
   - Calibrated dosimetry equipment
   - Mechanical test tools
   - Phantoms for imaging and dosimetry
   - Analysis software
   - Record-keeping systems

## Dosimetric Quality Assurance

### Output Constancy

Output constancy is the cornerstone of linac QA, ensuring consistent dose delivery:

1. **Daily Output Checks**:
   - Purpose: Verify consistent beam output
   - Equipment: Ionization chamber in solid phantom or dedicated QA device
   - Procedure: Measure reference field output at standard setup
   - Tolerance: ±3% for non-SRS/SBRT, ±2% for SRS/SBRT
   - Action Level: Investigate deviations >1%, recalibrate if >2%

2. **Monthly Output Calibration**:
   - Purpose: Verify absolute dose calibration
   - Equipment: Calibrated ionization chamber and electrometer
   - Procedure: Measure dose under reference conditions following TG-51 protocol
   - Tolerance: ±2% for all machines
   - Mathematical Formulation:
     $$D_w = M \times N_D \times k_Q \times k_{TP} \times k_{ion} \times k_{pol}$$
     where:
     - $D_w$ is the absorbed dose to water
     - $M$ is the corrected electrometer reading
     - $N_D$ is the chamber calibration factor
     - $k_Q$ is the beam quality correction factor
     - $k_{TP}$ is the temperature-pressure correction
     - $k_{ion}$ is the ion recombination correction
     - $k_{pol}$ is the polarity correction

3. **Annual TG-51 Calibration**:
   - Purpose: Comprehensive output calibration
   - Equipment: Calibrated ionization chamber with ADCL calibration
   - Procedure: Full implementation of TG-51 protocol
   - Tolerance: ±1% from baseline
   - Documentation: Detailed worksheet with all correction factors

### Beam Energy Constancy

Beam energy verification ensures consistent penetration characteristics:

1. **Daily Energy Checks**:
   - Purpose: Verify consistent beam energy
   - Equipment: Multi-layer phantom or dedicated QA device
   - Procedure: Measure ratio of ionization at two depths
   - Tolerance: ±2% for photons, ±2% for electrons

2. **Monthly Energy Verification**:
   - Purpose: More detailed energy assessment
   - Equipment: Water phantom or solid water phantom
   - Procedure: Measure PDD or TPR at specified depths
   - Tolerance: ±1% for photon PDD(10), ±2mm for electron R50
   - Mathematical Formulation for photon beam quality:
     $$TPR_{20,10} = \frac{D_{20cm}}{D_{10cm}}$$
     where $D_{20cm}$ and $D_{10cm}$ are doses at 20cm and 10cm depths

3. **Annual Beam Quality Assessment**:
   - Purpose: Comprehensive energy verification
   - Equipment: Water scanning system
   - Procedure: Measure complete PDD curves and beam profiles
   - Tolerance: ±1% for photon PDD(10), ±1mm for electron R50
   - Analysis: Compare with commissioning data

### Flatness and Symmetry

Beam profile characteristics ensure uniform dose distribution:

1. **Daily Flatness/Symmetry Checks**:
   - Purpose: Verify consistent beam profiles
   - Equipment: Multi-detector array or dedicated QA device
   - Procedure: Measure profiles in principal axes
   - Tolerance: ±2% for symmetry, ±2% for flatness

2. **Monthly Profile Verification**:
   - Purpose: More detailed profile assessment
   - Equipment: 2D detector array or water phantom
   - Procedure: Measure profiles at multiple depths
   - Tolerance: ±1% for symmetry, ±2% for flatness
   - Mathematical Formulation for symmetry:
     $$Symmetry = \frac{D_{left} - D_{right}}{D_{central}} \times 100\%$$
     where $D_{left}$, $D_{right}$, and $D_{central}$ are doses at symmetric points

3. **Annual Profile Analysis**:
   - Purpose: Comprehensive profile verification
   - Equipment: Water scanning system
   - Procedure: Measure complete profiles at multiple depths
   - Tolerance: ±1% for symmetry, ±2% for flatness
   - Analysis: Compare with commissioning data

## Mechanical Quality Assurance

### Geometric Accuracy

Geometric accuracy ensures precise alignment of mechanical components:

1. **Daily Geometric Checks**:
   - Purpose: Verify basic alignment
   - Equipment: Front pointer, optical distance indicator
   - Procedure: Check coincidence of light field, crosshair, and isocenter
   - Tolerance: ±2mm for non-SRS/SBRT, ±1mm for SRS/SBRT

2. **Monthly Geometric Verification**:
   - Purpose: More detailed alignment assessment
   - Equipment: Graph paper, ruler, level
   - Procedure: Check light field size, crosshair centering, and collimator rotation
   - Tolerance: ±2mm for field size, ±1mm for crosshair centering
   - Mathematical Formulation for field size accuracy:
     $$Error = Measured_{size} - Indicated_{size}$$

3. **Annual Geometric Assessment**:
   - Purpose: Comprehensive geometric verification
   - Equipment: Specialized alignment tools
   - Procedure: Check all geometric parameters
   - Tolerance: ±1mm for field size, ±0.5° for angular indicators
   - Analysis: Compare with commissioning data

### Isocenter Accuracy

Isocenter verification ensures accurate treatment delivery point:

1. **Monthly Isocenter Checks**:
   - Purpose: Verify isocenter stability
   - Equipment: Pointer, graph paper, or specialized tools
   - Procedure: Check coincidence of gantry, collimator, and couch rotations
   - Tolerance: ±2mm diameter for non-SRS/SBRT, ±1mm for SRS/SBRT

2. **Annual Winston-Lutz Test**:
   - Purpose: Comprehensive isocenter verification
   - Equipment: Ball bearing phantom, film or EPID
   - Procedure: Image ball bearing at multiple gantry, collimator, and couch angles
   - Tolerance: ±1mm diameter for non-SRS/SBRT, ±0.5mm for SRS/SBRT
   - Mathematical Formulation:
     $$Isocenter~Deviation = \sqrt{(x_{max} - x_{min})^2 + (y_{max} - y_{min})^2}$$
     where $x_{max}$, $x_{min}$, $y_{max}$, and $y_{min}$ are the extreme positions of the radiation field center relative to the ball bearing

3. **Spoke Shot Test**:
   - Purpose: Alternative isocenter verification
   - Equipment: Film in phantom
   - Procedure: Expose narrow fields at multiple gantry angles
   - Tolerance: ±1mm diameter for non-SRS/SBRT, ±0.5mm for SRS/SBRT
   - Analysis: Measure maximum distance between radiation fields

### Collimation Systems

Verification of collimation systems ensures accurate field shaping:

1. **Monthly Jaw Position Checks**:
   - Purpose: Verify jaw position accuracy
   - Equipment: Graph paper, ruler
   - Procedure: Measure light field dimensions at multiple field sizes
   - Tolerance: ±2mm for non-SRS/SBRT, ±1mm for SRS/SBRT

2. **Monthly MLC Position Checks**:
   - Purpose: Verify MLC position accuracy
   - Equipment: Graph paper, film, or EPID
   - Procedure: Measure leaf positions at multiple configurations
   - Tolerance: ±1mm for non-SRS/SBRT, ±0.5mm for SRS/SBRT
   - Mathematical Formulation for leaf position error:
     $$Error_i = Measured_{position,i} - Expected_{position,i}$$
     where $i$ represents each leaf

3. **Annual Comprehensive MLC QA**:
   - Purpose: Detailed MLC performance verification
   - Equipment: Film, EPID, or dedicated MLC QA device
   - Procedure: Test leaf position accuracy, reproducibility, and speed
   - Tolerance: ±1mm for position, ±0.2mm for reproducibility
   - Analysis: Compare with commissioning data

## Image Guidance Quality Assurance

### On-Board Imaging Systems

Verification of on-board imaging systems ensures accurate patient positioning:

1. **Daily Imaging Checks**:
   - Purpose: Verify basic imaging functionality
   - Equipment: Phantom with fiducial markers
   - Procedure: Acquire and evaluate image quality
   - Tolerance: Visible fiducials, acceptable contrast

2. **Monthly Geometric Calibration**:
   - Purpose: Verify imaging geometry
   - Equipment: Calibration phantom
   - Procedure: Measure imaging isocenter coincidence with radiation isocenter
   - Tolerance: ±2mm for non-SRS/SBRT, ±1mm for SRS/SBRT
   - Mathematical Formulation:
     $$Coincidence~Error = \sqrt{(x_{img} - x_{rad})^2 + (y_{img} - y_{rad})^2 + (z_{img} - z_{rad})^2}$$
     where $(x_{img}, y_{img}, z_{img})$ is the imaging isocenter and $(x_{rad}, y_{rad}, z_{rad})$ is the radiation isocenter

3. **Annual Comprehensive Imaging QA**:
   - Purpose: Detailed imaging performance verification
   - Equipment: Specialized phantoms
   - Procedure: Test geometric accuracy, image quality, and dose
   - Tolerance: ±1mm for geometry, baseline ±20% for image quality metrics
   - Analysis: Compare with commissioning data

### CBCT Quality Assurance

Cone-beam CT systems require specific quality assurance:

1. **Monthly CBCT Image Quality**:
   - Purpose: Verify CBCT image quality
   - Equipment: CBCT phantom with various inserts
   - Procedure: Evaluate contrast, noise, uniformity, and spatial resolution
   - Tolerance: Baseline ±10% for HU values, baseline ±20% for noise
   - Mathematical Formulation for contrast-to-noise ratio:
     $$CNR = \frac{|HU_{ROI} - HU_{background}|}{\sigma_{background}}$$
     where $HU_{ROI}$ is the mean HU in the region of interest, $HU_{background}$ is the mean HU in the background, and $\sigma_{background}$ is the standard deviation in the background

2. **Monthly CBCT Geometric Accuracy**:
   - Purpose: Verify CBCT geometric accuracy
   - Equipment: Phantom with known dimensions
   - Procedure: Measure distances and volumes in CBCT images
   - Tolerance: ±1mm for distances, ±2% for volumes

3. **Annual CBCT Dose Assessment**:
   - Purpose: Monitor imaging dose
   - Equipment: CT dose phantom and ion chamber
   - Procedure: Measure CTDI for all protocols
   - Tolerance: Baseline ±20%
   - Mathematical Formulation for weighted CTDI:
     $$CTDI_w = \frac{1}{3}CTDI_{center} + \frac{2}{3}CTDI_{periphery}$$
     where $CTDI_{center}$ is measured at the center and $CTDI_{periphery}$ is the average of measurements at peripheral locations

### Planar Imaging Quality Assurance

kV and MV planar imaging systems require specific quality assurance:

1. **Monthly Planar Image Quality**:
   - Purpose: Verify planar image quality
   - Equipment: Phantom with contrast inserts
   - Procedure: Evaluate contrast, noise, and spatial resolution
   - Tolerance: Baseline ±20% for contrast-to-noise ratio

2. **Monthly Geometric Accuracy**:
   - Purpose: Verify imaging geometry
   - Equipment: Phantom with fiducial markers
   - Procedure: Measure distances between markers
   - Tolerance: ±1mm for distances

3. **Annual Imaging Dose Assessment**:
   - Purpose: Monitor imaging dose
   - Equipment: Phantom and ion chamber
   - Procedure: Measure entrance dose for all protocols
   - Tolerance: Baseline ±20%
   - Mathematical Formulation for entrance skin exposure:
     $$ESE = M \times N_k \times BSF \times k_{TP}$$
     where $M$ is the chamber reading, $N_k$ is the calibration factor, $BSF$ is the backscatter factor, and $k_{TP}$ is the temperature-pressure correction

## Advanced Technology Quality Assurance

### IMRT-Specific Quality Assurance

IMRT delivery requires additional quality assurance:

1. **Monthly MLC Performance**:
   - Purpose: Verify MLC performance for IMRT
   - Equipment: Film, EPID, or 2D array
   - Procedure: Deliver test patterns and dynamic sequences
   - Tolerance: ±2% for dose accuracy, ±1mm for position accuracy
   - Mathematical Formulation for leaf position impact on dose:
     $$\Delta D \approx \frac{\Delta x}{w} \times 100\%$$
     where $\Delta D$ is the percent dose change, $\Delta x$ is the leaf position error, and $w$ is the field width

2. **Monthly Dynamic Dose Delivery**:
   - Purpose: Verify accurate dynamic dose delivery
   - Equipment: Ion chamber and phantom
   - Procedure: Deliver dynamic test patterns
   - Tolerance: ±2% for dose accuracy
   - Analysis: Compare with expected values

3. **Annual End-to-End Testing**:
   - Purpose: Comprehensive IMRT system verification
   - Equipment: Anthropomorphic phantom with detectors
   - Procedure: Complete process from CT simulation to delivery
   - Tolerance: ±3% for dose, ±2mm for position
   - Analysis: Compare with treatment planning system calculations

### SRS/SBRT-Specific Quality Assurance

Stereotactic treatments require stringent quality assurance:

1. **Monthly Small Field Dosimetry**:
   - Purpose: Verify small field dose accuracy
   - Equipment: Small volume detector in phantom
   - Procedure: Measure output factors for small fields
   - Tolerance: ±2% for fields >2cm, ±5% for fields <2cm
   - Mathematical Formulation for outpu
(Content truncated due to size limit. Use line ranges to read in chunks)