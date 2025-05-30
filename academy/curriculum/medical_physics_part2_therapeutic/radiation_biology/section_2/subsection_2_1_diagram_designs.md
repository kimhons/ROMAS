# Diagram Designs: Cell Survival Curves

## Diagram 1: Clonogenic Assay Experimental Methodology

### Purpose
To provide a comprehensive visual representation of the clonogenic assay methodology, illustrating each step from cell preparation to colony counting and survival curve generation.

### Key Elements

1. **Cell Preparation Panel**
   - **Cell Culture**
     - Flask with adherent cells (epithelial morphology)
     - Growth medium with appropriate supplements
     - Incubator conditions labeled (37°C, 5% CO₂, humidity)
     - Scale bar indicating cellular dimensions (10-20 μm)
   
   - **Cell Harvesting**
     - Trypsinization process
     - Detached cells in suspension
     - Centrifugation step
     - Cell pellet formation
   
   - **Cell Counting**
     - Hemocytometer grid with cells
     - Trypan blue exclusion for viability
     - Calculation formula for cell concentration
     - Automated counter alternative method

2. **Irradiation Setup Panel**
   - **Radiation Source**
     - Linear accelerator or X-ray machine
     - Calibrated dosimetry system
     - Radiation beam geometry
     - Backscatter material
   
   - **Sample Positioning**
     - Cell culture plates/flasks on treatment couch
     - Source-to-surface distance indicator
     - Field size and uniformity visualization
     - Temperature maintenance system
   
   - **Dose Delivery**
     - Dose range typically used (0-10 Gy)
     - Dose rate specification
     - Monitor unit calculation
     - Verification dosimetry

3. **Plating Process Panel**
   - **Dilution Series**
     - Serial dilution illustration
     - Cell concentrations for each dose level
     - Inverse relationship between dose and cell number
     - Calculation table showing plating numbers
   
   - **Plating Technique**
     - Multi-well plates or Petri dishes
     - Even cell distribution technique
     - Appropriate cell spacing
     - Multiple replicates for each condition
   
   - **Incubation**
     - Incubator settings
     - Typical incubation period (1-3 weeks)
     - Colony formation progression timeline
     - Growth medium maintenance

4. **Colony Assessment Panel**
   - **Fixation and Staining**
     - Fixative application (methanol/acetic acid)
     - Staining process (crystal violet)
     - Washing steps
     - Dried plate appearance
   
   - **Colony Identification**
     - Definition of colony (≥50 cells)
     - Microscopic view of colony morphology
     - Size variation among colonies
     - Abortive colonies vs. true colonies
   
   - **Counting Methods**
     - Manual counting with marker/grid
     - Automated image analysis system
     - Colony counting software interface
     - Quality control verification

5. **Data Analysis Panel**
   - **Calculation Steps**
     - Plating efficiency formula with example
     - Survival fraction calculation with example
     - Error propagation method
     - Statistical analysis approach
   
   - **Survival Curve Generation**
     - Raw data table format
     - Plotting on semi-log graph
     - Curve fitting process
     - Parameter extraction (α, β, SF2, etc.)
   
   - **Interpretation Framework**
     - Comparison to reference cell lines
     - Radiosensitivity classification
     - Quality metrics for assay validity
     - Reporting standards

### Design Notes
- Use consistent color coding throughout the workflow
- Include magnified insets for critical steps
- Provide timeline indicators showing typical duration of each step
- Use arrows to indicate process flow
- Include both macroscopic (plate/flask level) and microscopic (cellular level) visualizations
- Provide detailed legend explaining all components and processes
- Use high-resolution vector graphics for print quality
- Include brief explanatory text for each major step
- Provide cross-references to relevant sections in the text content

## Diagram 2: Survival Curve Interpretation Guide

### Purpose
To illustrate the key features, parameters, and mathematical models of radiation survival curves, providing a comprehensive visual guide to their interpretation.

### Key Elements

1. **Basic Survival Curve Anatomy Panel**
   - **Coordinate System**
     - Y-axis: Surviving fraction (logarithmic scale, 1 to 0.0001)
     - X-axis: Dose (linear scale, 0 to 10 Gy)
     - Grid lines for easy reading
     - Origin clearly marked
   
   - **Key Regions**
     - Shoulder region highlighted and labeled
     - Linear region highlighted and labeled
     - Transition zone between shoulder and linear regions
     - Extrapolation lines for parameter determination
   
   - **Data Representation**
     - Experimental data points with error bars
     - Fitted curve through data points
     - 95% confidence interval bands
     - Residual plot showing goodness of fit

2. **Mathematical Models Panel**
   - **Linear Model**
     - Equation: S = e^(-αD)
     - Straight line on log-linear plot
     - Parameter α visualization
     - Typical for high-LET radiation
   
   - **Linear-Quadratic Model**
     - Equation: S = e^(-αD-βD²)
     - Continuously bending curve
     - Visualization of α and β components
     - Dose range of applicability
   
   - **Multi-Target Single-Hit Model**
     - Equation: S = 1-(1-e^(-D/D₀))^n
     - Initial shoulder with final straight portion
     - Extrapolation number (n) visualization
     - Historical context note
   
   - **Model Comparison**
     - Overlay of all three models
     - Regions of agreement/disagreement
     - Dose ranges where each model is most appropriate
     - Mechanistic basis for each model

3. **Parameter Extraction Panel**
   - **D₀ Determination**
     - Definition (37% survival dose on final slope)
     - Graphical method for determination
     - Relationship to final slope (D₀ = 1/slope)
     - Typical values for different cell types
   
   - **Dq Determination**
     - Definition (quasi-threshold dose)
     - Back-extrapolation method
     - Relationship to shoulder width
     - Typical values for different radiation types
   
   - **Extrapolation Number (n)**
     - Definition (y-intercept of back-extrapolated line)
     - Graphical determination method
     - Relationship to repair capacity
     - Typical values for mammalian cells
   
   - **SF2 Determination**
     - Definition (survival at 2 Gy)
     - Clinical relevance explanation
     - Graphical determination method
     - Classification system based on SF2 values

4. **Linear-Quadratic Parameters Panel**
   - **α Parameter**
     - Definition (initial slope, Gy⁻¹)
     - Mechanistic basis (single-track events)
     - Determination method from curve fit
     - Typical values for different cell types
   
   - **β Parameter**
     - Definition (quadratic component, Gy⁻²)
     - Mechanistic basis (two-track events)
     - Determination method from curve fit
     - Typical values for different cell types
   
   - **α/β Ratio**
     - Definition (dose where linear and quadratic components equal)
     - Graphical representation on survival curve
     - Relationship to fractionation sensitivity
     - Typical values for early and late responding tissues
   
   - **Biological Effective Dose (BED)**
     - Derivation from LQ model
     - Calculation formula
     - Isoeffect curve visualization
     - Application to fractionation comparison

5. **Comparative Analysis Panel**
   - **Radiosensitivity Comparison**
     - Overlay of sensitive, moderate, and resistant cell lines
     - Parameter differences highlighted
     - Molecular determinants of differences
     - Classification system
   
   - **Radiation Quality Comparison**
     - Low-LET vs. high-LET curves
     - RBE visualization at different survival levels
     - Shoulder differences highlighted
     - Mechanistic explanation
   
   - **Modifying Factors**
     - Oxygen effect on survival curves
     - Dose rate effect visualization
     - Radiosensitizer effect
     - Radioprotector effect
   
   - **Fractionation Visualization**
     - Single dose vs. fractionated dose
     - Repair between fractions
     - Accumulated damage representation
     - Relationship to α/β ratio

### Design Notes
- Use consistent color coding for different models and parameters
- Implement clear visual distinction between experimental data and fitted curves
- Include magnified insets for critical regions (e.g., shoulder)
- Use arrows and annotations to indicate key features
- Provide step-by-step visual guides for parameter determination
- Include both theoretical curves and actual experimental data examples
- Provide detailed legend explaining all mathematical symbols and parameters
- Use high-resolution vector graphics for print quality
- Include brief explanatory text for each panel
- Provide cross-references to relevant sections in the text content

## Diagram 3: Comparative Survival Curves for Different Conditions

### Purpose
To illustrate how cell survival curves vary across different radiation types, cell lines, and modifying conditions, providing a comprehensive visual comparison of radiobiological responses.

### Key Elements

1. **Radiation Type Comparison Panel**
   - **Photon Radiation**
     - X-rays (250 kVp) survival curve
     - Gamma rays (Co-60) survival curve
     - Megavoltage X-rays (6 MV) survival curve
     - Characteristic shoulder and slope
   
   - **Particle Radiation**
     - Electron survival curve
     - Proton survival curve (entrance region)
     - Proton survival curve (Bragg peak)
     - Carbon ion survival curve
   
   - **LET Spectrum**
     - Very low LET (0.2 keV/μm)
     - Low LET (2 keV/μm)
     - Intermediate LET (20 keV/μm)
     - High LET (100 keV/μm)
     - Very high LET (200 keV/μm)
   
   - **RBE Visualization**
     - RBE calculation method
     - RBE at different survival levels
     - RBE-LET relationship curve
     - Optimal LET for maximum RBE

2. **Cell Type Comparison Panel**
   - **Lymphoid Cells**
     - Lymphocyte survival curve
     - Lymphoma cell line curve
     - Steep slope, minimal shoulder
     - Molecular basis for sensitivity
   
   - **Epithelial Cells**
     - Normal epithelial survival curve
     - Carcinoma cell line curve
     - Moderate shoulder and slope
     - Heterogeneity among epithelial types
   
   - **Fibroblasts**
     - Normal fibroblast survival curve
     - Transformed fibroblast curve
     - Pronounced shoulder, shallow slope
     - Repair capacity visualization
   
   - **Stem Cells vs. Differentiated Cells**
     - Hematopoietic stem cell curve
     - Neural stem cell curve
     - Differentiated neuron curve
     - Correlation with proliferative capacity

3. **Genetic Background Panel**
   - **DNA Repair Deficiency**
     - Wild-type cell survival curve
     - ATM-deficient cell curve
     - BRCA1/2-deficient cell curve
     - NHEJ-deficient cell curve
   
   - **Cell Cycle Checkpoint Defects**
     - p53 wild-type vs. mutant curves
     - G1/S checkpoint deficiency
     - G2/M checkpoint deficiency
     - Combined checkpoint deficiencies
   
   - **Radiosensitivity Syndromes**
     - Ataxia telangiectasia cells
     - Nijmegen breakage syndrome cells
     - Fanconi anemia cells
     - Xeroderma pigmentosum cells
   
   - **Oncogene Status**
     - RAS wild-type vs. mutant curves
     - MYC normal vs. overexpressed curves
     - EGFR normal vs. amplified curves
     - Combined oncogenic alterations

4. **Microenvironmental Factors Panel**
   - **Oxygen Effect**
     - Well-oxygenated cells (21% O₂)
     - Moderately hypoxic cells (2% O₂)
     - Severely hypoxic cells (0.2% O₂)
     - Anoxic cells (<0.01% O₂)
   
   - **Dose Rate Effect**
     - High dose rate (>1 Gy/min)
     - Moderate dose rate (0.1-1 Gy/min)
     - Low dose rate (0.01-0.1 Gy/min)
     - Very low dose rate (<0.01 Gy/min)
     - Ultra-high dose rate (FLASH, >40 Gy/s)
   
   - **Temperature Effect**
     - Hypothermia (30°C)
     - Normal temperature (37°C)
     - Mild hyperthermia (41°C)
     - Severe hyperthermia (43°C)
   
   - **pH and Nutrient Status**
     - Normal pH (7.4) and nutrients
     - Acidic pH (6.8)
     - Glucose deprivation
     - Combined stress conditions

5. **Chemical Modifiers Panel**
   - **Radiosensitizers**
     - Oxygen mimetics (nitroimidazoles)
     - Halogenated pyrimidines
     - DNA repair inhibitors
     - Combined modality effects
   
   - **Radioprotectors**
     - Amifostine (WR-2721)
     - Free radical scavengers
     - Cytoprotective cytokines
     - Combined protection strategies
   
   - **Biologically Targeted Agents**
     - PARP inhibitors
     - DNA-PK inhibitors
     - ATM/ATR inhibitors
     - Checkpoint inhibitors
   
   - **Dose Modification Factors**
     - Sensitizer enhancement ratio calculation
     - Protection factor calculation
     - Therapeutic index visualization
     - Clinical translation notes

### Design Notes
- Use consistent color coding for different radiation types, cell lines, and conditions
- Implement standardized axis scales across all panels for direct comparison
- Include magnified insets for regions of particular interest
- Use arrows and annotations to highlight key differences
- Provide molecular mechanism diagrams where appropriate
- Include both idealized curves and actual experimental data examples
- Provide detailed legend explaining all conditions and modifications
- Use high-resolution vector graphics for print quality
- Include brief explanatory text for each panel
- Provide cross-references to relevant sections in the text content

## Diagram 4: Alternative Cell Survival Assessment Methods

### Purpose
To compare and contrast different methods for measuring radiation-induced cell killing, illustrating the principles, procedures, advantages, and limitations of each approach.

### Key Elements

1. **Clonogenic Assay Panel (Gold Standard)**
   - **Principle Visualization**
     - Colony formation from single cells
     - Reproductive integrity assessment
     - Minimum colony size threshold (50 cells)
     - Timeline of colony development
   
   - **Procedure Flowchart**
     - Cell preparation and counting
     - Irradiation step
     - Plating at appropriate dilutions
     - Incubation period
     - Fixation, staining, and counting
   
   - **Results Representation**
     - Stained plates with colonies
     - Dose-dependent colony reduction
     - Survival curve generation
     - Parameter extraction
   
   - **Advantages/Limitations**
     - Pros: Gold standard, direct measure of reproductive death
     - Cons: Time-consuming, labor-intensive
     - Sensitivity and specificity metrics
     - Technical challenges visualization

2. **Growth Assays Panel**
   - **Cell Counting Methods**
     - Hemocytometer counting
     - Automated cell counter
     - Flow cytometry counting
     - Growth curve generation
   
   - **Spheroid Growth Delay**
     - 3D culture formation
     - Size measurement techniques
     - Growth delay quantification
     - Correlation with clonogenic survival
   
   - **Real-time Cell Analysis**
     - Impedance-based monitoring
     - Time-lapse microscopy
     - Growth kinetics parameters
     - Data analysis approaches
   
   - **Advantages/Limitations**
     - Pros: Simpler, works for all cell types
     - Cons: Less sensitive, affected by cell density
     - Correlation with clonogenic survival
     - Best application scenarios

3. **Metabolic and Viability Assays Panel**
   - **MTT/MTS Assays**
     - Tetrazolium reduction principle
     - Colorimetric measurement
     - Dose-response curves
     - Correlation with cell number
   
   - **ATP Assays**
     - Luciferase reaction principle
     - Luminescence measurement
     - Standard curve generation
     - Sensitivity range
   
   - **Membrane Integrity Assays**
     - Trypan blue exclusion
     - Propidium iodide uptake
     - Calcein-AM retention
     - Live/dead discrimination
   
   - **Advantages/Limitations**
     - Pros: Rapid, high-throughput
     - Cons: Indirect measure, metabolic artifacts
     -
(Content truncated due to size limit. Use line ranges to read in chunks)