# AAPM TG-55 Radiochromic Film

## Historical Context and Purpose

Radiochromic film has become an essential tool in radiation dosimetry, offering high spatial resolution, weak energy dependence, and near tissue-equivalence. The American Association of Physicists in Medicine (AAPM) Task Group 55 (TG-55) was formed to provide guidance on radiochromic film dosimetry, specifically focusing on the GafChromic film models available at the time of publication (1998).

The primary purposes of TG-55 were to:
1. Provide a comprehensive review of radiochromic film technology
2. Establish standardized procedures for film handling, calibration, and readout
3. Describe appropriate applications and limitations
4. Recommend quality assurance procedures

Since the publication of TG-55, radiochromic film technology has evolved significantly, with newer models (EBT, EBT2, EBT3, etc.) replacing the original HD-810 and MD-55 films discussed in the report. However, the fundamental principles and methodologies established by TG-55 remain relevant and form the foundation for modern radiochromic film dosimetry practices.

## Radiochromic Film Composition and Properties

### Basic Composition

Radiochromic films consist of a radiation-sensitive active layer sandwiched between protective coating layers. The composition varies by film model:

**Original Films (Discussed in TG-55):**
- **HD-810**: Single 6.5 μm active layer on 97 μm polyester base
- **MD-55-1**: Single 15 μm active layer between two 25 μm polyester substrates
- **MD-55-2**: Two 15 μm active layers separated by and sandwiched between polyester substrates

**Modern Films (Post-TG-55):**
- **EBT**: 30 μm active layer between polyester substrates
- **EBT2**: 30 μm active layer with yellow marker dye between polyester substrates
- **EBT3**: Symmetric design with 30 μm active layer between polyester substrates with silica particles

The active layer contains a crystalline polyacetylene matrix with radiation-sensitive diacetylene monomers. Upon irradiation, these monomers undergo polymerization, resulting in color changes from transparent to increasingly dark blue or green (depending on the film model).

### Physical Properties

Radiochromic film offers several advantageous physical properties:

1. **Tissue Equivalence**: The effective atomic number (Z<sub>eff</sub>) of radiochromic film is approximately 6.5-7.0, close to that of water (Z<sub>eff</sub> = 7.4) and tissue (Z<sub>eff</sub> = 7.2). This results in minimal energy dependence for photon beams above 100 keV.

2. **Spatial Resolution**: The crystalline structure provides microscopic resolution (>1200 lines/mm), limited primarily by the readout system rather than the film itself.

3. **Self-Developing**: Unlike radiographic film, radiochromic film requires no chemical processing, as the polymerization reaction proceeds automatically after irradiation.

4. **Insensitivity to Room Light**: Most radiochromic films are relatively insensitive to ambient light, though prolonged exposure should be avoided.

5. **Dose Range**: Different models cover various dose ranges:
   - HD-810: 10-400 Gy
   - MD-55: 1-100 Gy
   - EBT/EBT2/EBT3: 0.01-10 Gy (suitable for clinical applications)

### Dosimetric Properties

The dosimetric characteristics of radiochromic film include:

1. **Dose Response**: The optical density (OD) increases with absorbed dose, typically following a non-linear relationship that can be approximated by various fitting functions:
   - Linear: OD = a + b × Dose
   - Quadratic: OD = a + b × Dose + c × Dose²
   - Power function: OD = a + b × Dose<sup>c</sup>
   - Logarithmic: OD = a + b × ln(Dose)

2. **Energy Dependence**: Minimal energy dependence for photon energies above 100 keV, with variations typically less than 5% across clinical radiotherapy energy ranges (6-18 MV).

3. **Dose Rate Independence**: Response is largely independent of dose rate for typical radiotherapy applications (1-10 Gy/min).

4. **Post-Irradiation Development**: The polymerization reaction continues after irradiation, with optical density increasing rapidly in the first 24 hours and then stabilizing. Modern films (EBT3) show faster stabilization than earlier models.

5. **Temperature and Humidity Effects**: Sensitivity increases with temperature during irradiation (approximately 1% per °C). Humidity affects both the pre-irradiation storage and post-irradiation development.

## Film Handling and Preparation

### Storage Recommendations

Proper storage is critical to maintain film quality and consistency:

1. **Temperature**: Store at controlled temperature (20-25°C). Avoid temperature fluctuations.

2. **Humidity**: Maintain relative humidity between 30-60%. Excessive humidity can accelerate degradation.

3. **Light Exposure**: Store in light-tight packaging. While relatively insensitive to ambient light, prolonged exposure should be avoided.

4. **Pressure**: Avoid applying pressure to the film, which can create artifacts.

5. **Orientation**: Store films flat rather than rolled to prevent curvature that can affect scanning.

6. **Shelf Life**: Observe manufacturer-recommended shelf life (typically 1-2 years when properly stored).

### Handling Procedures

To minimize artifacts and ensure measurement accuracy:

1. **Gloves**: Always wear powder-free gloves when handling film to avoid fingerprints and contamination.

2. **Cutting**: If cutting is necessary, use sharp scissors or a paper cutter. Mark film orientation before cutting.

3. **Marking**: Use soft markers on the film edges only, never on areas to be analyzed.

4. **Dust and Contamination**: Handle in a clean environment. Use compressed air to remove dust before scanning.

5. **Bending**: Avoid bending or creasing the film, as this creates permanent artifacts.

6. **Uniformity**: For large batch measurements, ensure all films come from the same production lot.

### Film Preparation for Irradiation

Steps to prepare film for experimental or clinical use:

1. **Acclimation**: Allow film to reach thermal equilibrium with the irradiation environment (at least 1 hour).

2. **Identification**: Label each film piece with a unique identifier on the edge or using a system of small punched holes.

3. **Orientation**: Mark film orientation (landscape/portrait) to maintain consistent scanning direction.

4. **Size Preparation**: Cut films to appropriate size at least 24 hours before irradiation to allow edge effects to stabilize.

5. **Background Measurement**: For high-precision work, consider scanning films before irradiation to establish background optical density.

6. **Phantom Placement**: Place film between solid water or plastic water slabs with minimal air gaps. Apply sufficient pressure to ensure good contact but avoid excessive pressure that might damage the film.

## Calibration Procedures

### Establishing a Calibration Curve

A proper calibration curve relates optical density to absorbed dose:

1. **Calibration Film Selection**: Use films from the same lot as the experimental films.

2. **Dose Range**: Cover the entire range of expected doses with at least 8-10 calibration points.

3. **Field Setup**:
   - 10×10 cm² field at 100 cm SSD
   - Sufficient buildup to ensure electronic equilibrium (e.g., d<sub>max</sub> or greater)
   - Sufficient backscatter material (≥10 cm)

4. **Dose Delivery**:
   - Option 1: Irradiate separate film pieces to different doses
   - Option 2: Create a step-wedge pattern on a single film using either:
     - Sequential irradiations with partial blocking
     - Dynamic MLC delivery of a step pattern

5. **Reference Dosimetry**: Verify delivered doses using a calibrated ionization chamber under identical conditions.

### Scanning Protocol

Consistent scanning procedures are essential for accurate results:

1. **Scanner Selection**: Use a transmission flatbed scanner (reflective scanning is not recommended).

2. **Scanner Warm-up**: Allow the scanner to warm up for at least 15-30 minutes before use.

3. **Scanning Parameters**:
   - Resolution: 72-150 dpi for most applications (higher resolution increases noise)
   - Color depth: 48-bit RGB (16 bits per channel)
   - Image type: Uncompressed TIFF format
   - No color correction or filtering

4. **Orientation**: Place films consistently in landscape or portrait orientation, centered on the scanner bed.

5. **Region of Interest**: Use only the central portion of the scanner to avoid edge effects (typically 5 cm from edges).

6. **Multiple Scans**: Perform 3-5 repeated scans and average the results to reduce noise.

7. **Color Channel Selection**: For EBT/EBT2/EBT3 films, the red channel provides the highest sensitivity for doses <10 Gy, while the green channel may be used for higher doses.

### Mathematical Models for Calibration

Several mathematical models can be used to fit the calibration data:

1. **Linear Model**: 
   $OD = a + b \times Dose$
   
   - Simple but only accurate over limited dose ranges
   - Example: For doses between 0-2 Gy, OD = 0.1 + 0.2 × Dose

2. **Quadratic Model**: 
   $OD = a + b \times Dose + c \times Dose^2$
   
   - Better fit over wider dose ranges
   - Example: OD = 0.1 + 0.2 × Dose - 0.01 × Dose²

3. **Power Function**: 
   $OD = a + b \times Dose^c$
   
   - Often provides the best fit for EBT films
   - Example: OD = 0.1 + 0.15 × Dose<sup>0.8</sup>

4. **Rational Function**: 
   $OD = \frac{a + b \times Dose}{1 + c \times Dose}$
   
   - Works well for newer EBT2/EBT3 films
   - Example: OD = (0.1 + 0.3 × Dose)/(1 + 0.05 × Dose)

5. **Logarithmic Function**: 
   $OD = a + b \times \ln(Dose)$
   
   - Useful for high-dose regions
   - Example: OD = 0.1 + 0.15 × ln(Dose)

### Uncertainty Analysis

Understanding and quantifying uncertainties is crucial:

1. **Sources of Uncertainty**:
   - Film manufacturing variations (lot-to-lot, sheet-to-sheet)
   - Scanner response variations
   - Temperature and humidity effects
   - Post-irradiation development time variations
   - Fitting uncertainties in the calibration curve

2. **Typical Magnitude of Uncertainties**:
   - Overall uncertainty: 2-5% under optimal conditions
   - Can increase to >10% without proper protocols

3. **Uncertainty Reduction Strategies**:
   - Use films from the same lot
   - Maintain consistent temperature and humidity
   - Standardize post-irradiation scanning time
   - Use multiple films and average results
   - Apply triple-channel dosimetry methods for EBT films

## Scanning and Analysis Techniques

### Scanner Characteristics and Selection

The choice of scanner significantly impacts measurement accuracy:

1. **Scanner Types**:
   - Transmission (recommended): Light passes through the film
   - Reflection (not recommended): Light reflects off the film

2. **Key Scanner Specifications**:
   - Optical density range: Should exceed the maximum OD of irradiated films
   - Spatial resolution: 72-150 dpi is sufficient for most applications
   - Color depth: Minimum 16-bit per channel (48-bit RGB)
   - Stability: Minimal warm-up effects and consistent response

3. **Common Scanner Models**:
   - Epson 10000XL (gold standard for research)
   - Epson V700/V750
   - Epson Expression series

4. **Scanner Limitations**:
   - Light source non-uniformity
   - Warm-up effects
   - Polarization effects
   - Limited dynamic range

### Image Processing Workflow

A systematic approach to film analysis includes:

1. **Pre-Processing**:
   - Scanner warm-up (15-30 minutes)
   - Background correction using unexposed film
   - Dark current correction (scan with lamp off or lid open)

2. **Film Scanning**:
   - Consistent orientation (landscape/portrait)
   - Central placement on scanner bed
   - Multiple scans (3-5) for averaging
   - No image processing or color correction

3. **Image Analysis**:
   - Color channel separation (extract red, green, or blue channel)
   - Region of interest (ROI) selection
   - Background subtraction
   - Conversion from pixel value to optical density:
     $OD = \log_{10}(\frac{I_0}{I})$
     where I<sub>0</sub> is the background intensity and I is the film intensity

4. **Dose Conversion**:
   - Apply calibration curve to convert OD to dose
   - Apply any necessary correction factors

5. **Post-Processing**:
   - Noise reduction (median filtering, Gaussian smoothing)
   - Profile extraction
   - Gamma analysis for comparison with calculated doses

### Multichannel Dosimetry

Modern approaches use information from multiple color channels:

1. **RGB Channel Characteristics**:
   - Red: Highest sensitivity for <10 Gy, but saturates at higher doses
   - Green: Lower sensitivity but wider dynamic range
   - Blue: Lowest sensitivity, useful for very high doses

2. **Three-Channel Method**:
   - Uses all three color channels simultaneously
   - Separates dose-dependent optical density from non-dose-dependent artifacts
   - Mathematical model relates dose to optical density in each channel

3. **Advantages of Multichannel Approach**:
   - Reduces impact of artifacts (dust, scratches)
   - Corrects for scanner non-uniformities
   - Improves overall accuracy by 1-2%
   - Extends useful dose range

4. **Implementation**:
   - Requires calibration of all three channels
   - Uses optimization algorithms to find the dose that best fits the response in all channels
   - Commercial software available (FilmQA Pro, RIT, etc.)

### Software Tools

Several software options are available for radiochromic film analysis:

1. **Commercial Software**:
   - FilmQA Pro (Ashland/ISP)
   - RIT (Radiological Imaging Technology)
   - DoseLab (Mobius Medical Systems)

2. **Open-Source Options**:
   - Radiochromic.com
   - MATLAB-based tools (e.g., MCFit)
   - ImageJ with radiochromic film plugins

3. **Key Software Features**:
   - Calibration curve generation
   - Multichannel dosimetry
   - Gamma analysis
   - Profile extraction
   - 2D/3D visualization

## Clinical Applications

### Small Field Dosimetry

Radiochromic film is ideal for small field measurements:

1. **Advantages for Small Fields**:
   - High spatial resolution (critical for fields <2 cm)
   - Minimal detector volume effect
   - Energy independence (important in small fields with spectral changes)

2. **Measurement Procedures**:
   - Place film perpendicular to beam axis
   - Ensure sufficient buildup and backscatter
   - Use multiple films for statistical analysis

3. **Analysis Considerations**:
   - High-resolution scanning (≥150 dpi)
   - Careful ROI selection
   - Profile extraction for FWHM determination

4. **Typical Applications**:
   - SRS/SBRT field verification
   - MLC leaf position verification
   - Output factor measurements for small fields

### IMRT and VMAT QA

Film provides high-resolution verification of complex dose distributions:

1. **Patient-Specific QA**:
   - Coronal or sagittal plane dose verification
   - Comparison with TPS calculations
   - Gamma analysis (typically 3%/3mm criteria)

2. **Measurement Setup**:
   - Film in solid water phantom at prescription depth
   - Calibration films irradiated in same session
   - Registration marks for alignment with calculated dose

3. **Analysis Methods**:
   - Global gamma analysis
   - Dose difference maps
   - Distance-to-agreement analysis
   - DVH-based metrics for clinical structures

4. **Acceptance Criteria**:
   - Typically >90-95% passing rate for 3%/3mm gamma
   - Stricter criteria (2%/2mm) for critical structures

### Brachytherapy Dosimetry

Film provides valuable 2D dose distribution verification:

1. **HDR Brachytherapy**:
   - Source position verification
   - Dwell position and time verification
   - Applicator commissioning

2. **LDR Brachytherapy**:
   - Seed position verification
   - 2D dose distribution around seeds
   - Interseed attenuation effects

3. **Measurement Considerations**:
   - Energy dependence more significant at low energies
   - Calibration should match brachytherapy energy spectrum
   - Longer exposure times may require temperature/h
(Content truncated due to size limit. Use line ranges to read in chunks)