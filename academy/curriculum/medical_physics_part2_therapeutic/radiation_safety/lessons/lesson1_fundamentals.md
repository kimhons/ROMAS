# Fundamentals of Radiation Protection

## Overview
This lesson introduces the fundamental principles and concepts of radiation protection in radiation oncology. It covers the biological basis for radiation protection, historical development of protection standards, key principles including ALARA, practical protection methods using time, distance, and shielding, and the essential radiation quantities and units used in protection. Understanding these fundamentals provides the necessary foundation for implementing effective radiation safety practices in clinical settings.

## Learning Objectives
After completing this lesson, you will be able to:
- Explain the biological effects that form the basis for radiation protection standards
- Describe the historical development of radiation protection principles and standards
- Apply the ALARA principle in radiation oncology settings
- Implement time, distance, and shielding methods for radiation protection
- Define and calculate key radiation protection quantities and units
- Interpret radiation weighting factors and determine effective dose

## Estimated Completion Time
60 minutes

## Content Section 1: Biological Basis for Radiation Protection

### Subsection 1.1: Radiation Effects on Biological Systems
Radiation protection standards are based on our understanding of how ionizing radiation affects biological systems. These effects can be categorized as deterministic (tissue reactions) or stochastic effects.

Deterministic effects (tissue reactions) occur when radiation exposure exceeds certain thresholds, causing direct tissue damage. The severity of these effects increases with dose, and they typically manifest within days to weeks after exposure. Examples include:

- Erythema (skin reddening): threshold ~2 Gy
- Epilation (hair loss): threshold ~3 Gy
- Radiation dermatitis: threshold ~5 Gy
- Cataract formation: threshold ~0.5 Gy (protracted exposure)
- Hematopoietic syndrome: threshold ~1 Gy (whole body)
- Gastrointestinal syndrome: threshold ~6 Gy (whole body)
- Central nervous system syndrome: threshold ~20 Gy (whole body)

Stochastic effects have no threshold and occur probabilistically, with the probability (but not severity) increasing with dose. These include:

- Cancer induction (solid tumors and leukemia)
- Heritable effects (genetic mutations in offspring)

The linear no-threshold (LNT) model is the current basis for radiation protection standards for stochastic effects. This model assumes that:

1. There is no "safe" threshold dose below which the risk is zero
2. Risk increases linearly with dose
3. Risk is cumulative over a lifetime

The mathematical expression for cancer risk according to the LNT model is:

$$Risk = \alpha \times D$$

Where:
- $Risk$ is the probability of cancer induction
- $\alpha$ is the risk coefficient (approximately 5% per Sv for cancer mortality in a population)
- $D$ is the effective dose in Sv

[IMAGE: Graph showing linear no-threshold model compared to other dose-response models (threshold, hormesis, etc.)]

### Subsection 1.2: Radiation Sensitivity Factors
Several factors influence radiation sensitivity at the cellular, tissue, and individual levels:

**Cellular Factors:**
- Cell cycle phase (G2/M most sensitive, late S least sensitive)
- Oxygen concentration (well-oxygenated cells more sensitive)
- Repair capacity (deficient repair mechanisms increase sensitivity)
- Proliferation rate (rapidly dividing cells more sensitive)

**Tissue Factors (Law of Bergonié and Tribondeau):**
Tissues are more radiosensitive when they:
- Have high proliferation rates
- Have long future division potential
- Are less differentiated

This explains why tissues such as bone marrow, intestinal epithelium, gonads, and skin are more radiosensitive than tissues like muscle, brain, and kidney.

**Individual Factors:**
- Age (children more sensitive than adults)
- Gender (some differences in tissue sensitivities)
- Genetic factors (certain genetic syndromes increase sensitivity)
- Health status (compromised immune system increases sensitivity)

Understanding these sensitivity factors is crucial for radiation protection, particularly for special populations such as pediatric patients, pregnant women, and individuals with radiosensitivity syndromes.

## Content Section 2: Historical Development of Radiation Protection

### Subsection 2.1: Early Observations and Initial Standards
The history of radiation protection parallels our understanding of radiation hazards:

**Early Radiation Injuries (1895-1915):**
Shortly after Röntgen's discovery of X-rays in 1895, reports of skin burns, epilation, and dermatitis emerged among early radiation workers. By 1904, Thomas Edison's assistant, Clarence Dally, became the first documented radiation fatality after developing metastatic carcinoma from extensive radiation exposure to his hands.

**First Protection Measures (1915-1925):**
Initial protection recommendations focused on:
- Limiting exposure time
- Using protective barriers
- Maintaining distance from radiation sources
- Regular monitoring of radiation workers

**Formation of the ICRP (1928):**
The International X-Ray and Radium Protection Committee (later renamed the International Commission on Radiological Protection or ICRP) was established in 1928, marking the beginning of formal international radiation protection standards.

**Tolerance Dose Concept (1930s):**
The first quantitative standard was the "tolerance dose," defined as 0.2 R/day (approximately 2 mSv/day), based on the absence of observable effects rather than on stochastic risk assessment.

[IMAGE: Timeline showing key milestones in radiation protection history from 1895 to present]

### Subsection 2.2: Modern Radiation Protection Framework
The modern radiation protection framework evolved significantly after World War II:

**Post-War Developments (1950s):**
- Establishment of maximum permissible dose (MPD) concept
- Recognition of genetic effects and cancer risks
- Formation of organizations like UNSCEAR (1955) to assess radiation effects
- Development of the first comprehensive ICRP recommendations (1958)

**Risk-Based Approach (1970s-1990s):**
- Adoption of the linear no-threshold model for cancer risk
- Introduction of the effective dose concept (ICRP 26, 1977)
- Development of the ALARA principle
- Establishment of dose limits for workers and the public

**Current Framework (ICRP 103, 2007):**
The current radiation protection system is based on:
- Three fundamental principles: justification, optimization, and limitation
- Tissue weighting factors reflecting updated cancer risk data
- Consideration of both cancer and heritable effects
- Situation-based approach (planned, emergency, and existing exposure situations)
- Distinction between constraints (prospective) and limits (retrospective)

This evolution reflects the growing scientific understanding of radiation effects and the increasing emphasis on risk management rather than threshold-based protection.

## Content Section 3: ALARA Principle and Its Implementation

### Subsection 3.1: ALARA Concept
ALARA stands for "As Low As Reasonably Achievable." It is a fundamental principle in radiation protection that goes beyond simply meeting dose limits. The principle states that radiation exposures should be kept as low as reasonably achievable, taking into account economic and social factors.

The mathematical expression of the ALARA principle involves optimization, where the objective is to minimize the function:

$$X = \sum_{i} (\alpha_i \times S_i) + Y$$

Where:
- $X$ is the total "cost" to be minimized
- $S_i$ is the collective dose to population group $i$
- $\alpha_i$ is the monetary value assigned to unit collective dose for group $i$
- $Y$ is the cost of protection measures

This optimization balances radiation risk against the resources required for protection.

Key elements of ALARA include:
1. **Justification**: No practice involving radiation exposure should be adopted unless it produces sufficient benefit to offset the radiation detriment
2. **Optimization**: All exposures should be kept as low as reasonably achievable
3. **Limitation**: Individual doses should not exceed specified limits

### Subsection 3.2: Practical Implementation of ALARA
Implementing ALARA in radiation oncology involves several practical approaches:

**Administrative Controls:**
- Developing comprehensive radiation safety policies and procedures
- Establishing clear roles and responsibilities
- Implementing proper training programs
- Conducting regular audits and reviews
- Using appropriate authorization and supervision

**Engineering Controls:**
- Facility design with appropriate shielding
- Safety interlocks and warning systems
- Remote handling equipment for sources
- Proper ventilation systems
- Automated systems to reduce exposure time

**Operational Procedures:**
- Pre-treatment planning to minimize unnecessary exposure
- Quality assurance programs
- Proper maintenance of equipment
- Regular calibration of monitoring devices
- Incident reporting and investigation systems

**Practical Examples in Radiation Oncology:**
1. Using immobilization devices to ensure accurate patient positioning, reducing the need for repeat exposures
2. Implementing image-guided radiation therapy to improve targeting precision
3. Using remote afterloading systems for brachytherapy
4. Conducting thorough treatment planning to optimize dose distribution
5. Implementing robust quality assurance programs to prevent errors

[INTERACTIVE EXERCISE: ALARA Decision-Making Scenario]
This interactive exercise presents a scenario where you must make decisions about implementing new safety measures in a radiation oncology department. You will evaluate the cost, dose reduction, and practicality of different options to determine the most ALARA-compliant approach.

## Content Section 4: Time, Distance, and Shielding

### Subsection 4.1: Time Reduction
Minimizing exposure time is a fundamental radiation protection strategy. The radiation dose is directly proportional to the time spent in a radiation field:

$$D = \dot{D} \times t$$

Where:
- $D$ is the total dose
- $\dot{D}$ is the dose rate
- $t$ is the exposure time

Practical methods for reducing exposure time in radiation oncology include:

1. **Proper Planning**: Rehearsing procedures before actual execution
2. **Training**: Ensuring staff are proficient in their tasks
3. **Proper Tools**: Using specialized tools designed for efficiency
4. **Rotation of Personnel**: Distributing workload among multiple staff members
5. **Automation**: Using automated systems for source handling and treatment delivery

**Example Calculation:**
If the dose rate in a treatment room during a specific procedure is 0.1 mSv/hour, and the procedure time can be reduced from 30 minutes to 15 minutes through improved workflow, the dose reduction would be:

Original dose: $D_1 = 0.1 \text{ mSv/hour} \times 0.5 \text{ hour} = 0.05 \text{ mSv}$
Reduced dose: $D_2 = 0.1 \text{ mSv/hour} \times 0.25 \text{ hour} = 0.025 \text{ mSv}$
Dose reduction: 50%

### Subsection 4.2: Distance Utilization
The intensity of radiation decreases with the square of the distance from a point source, following the inverse square law:

$$\dot{D}_2 = \dot{D}_1 \times \left(\frac{d_1}{d_2}\right)^2$$

Where:
- $\dot{D}_1$ is the dose rate at distance $d_1$
- $\dot{D}_2$ is the dose rate at distance $d_2$

This relationship makes distance one of the most effective radiation protection tools.

Practical applications in radiation oncology include:

1. **Remote Handling Tools**: Long-handled tools for source manipulation
2. **Room Layout Design**: Maximizing staff distance from radiation sources
3. **Proper Positioning**: Standing in low-dose areas during procedures
4. **Remote Monitoring**: Using cameras and intercoms to monitor patients from a distance
5. **Remote Consoles**: Operating treatment machines from shielded control rooms

[ANIMATION: Visualization of inverse square law showing how radiation intensity decreases with distance]

**Example Calculation:**
If the dose rate at 1 meter from a brachytherapy source is 0.2 mSv/hour, the dose rate at 3 meters would be:

$$\dot{D}_2 = 0.2 \text{ mSv/hour} \times \left(\frac{1 \text{ m}}{3 \text{ m}}\right)^2 = 0.2 \text{ mSv/hour} \times \frac{1}{9} = 0.022 \text{ mSv/hour}$$

This represents a reduction to approximately 11% of the original dose rate by tripling the distance.

### Subsection 4.3: Shielding Principles
Shielding involves placing appropriate materials between the radiation source and the individual to attenuate the radiation. The effectiveness of shielding depends on:

1. **Radiation Type and Energy**: Different radiations require different shielding materials
2. **Shielding Material**: Characterized by atomic number, density, and thickness
3. **Geometry**: Configuration of the shield relative to the source and protected area

For photons, attenuation follows an exponential relationship:

$$I = I_0 e^{-\mu x}$$

Where:
- $I$ is the transmitted intensity
- $I_0$ is the initial intensity
- $\mu$ is the linear attenuation coefficient (cm⁻¹)
- $x$ is the shield thickness (cm)

The effectiveness of shielding is often expressed in terms of half-value layer (HVL) or tenth-value layer (TVL):

$$\text{HVL} = \frac{\ln(2)}{\mu} \approx \frac{0.693}{\mu}$$

$$\text{TVL} = \frac{\ln(10)}{\mu} \approx \frac{2.303}{\mu}$$

Common shielding materials in radiation oncology include:

| Material | Primary Use | Advantages | Limitations |
|----------|-------------|------------|-------------|
| Lead | Photon shielding | High density, high Z, compact | Toxic, heavy, expensive |
| Concrete | Structural barriers | Cost-effective, structural integrity | Requires significant thickness |
| Steel | Structural components | Strength, moderate shielding | Less effective than lead |
| Water | Neutron moderation | Readily available, effective for neutrons | Requires containment |
| Polyethylene | Neutron shielding | Hydrogen-rich, lightweight | Limited photon attenuation |

**Example Calculation:**
For a 6 MV photon beam with an HVL of 1.5 cm in lead, the thickness required to reduce the intensity to 1/10th (one TVL) would be:

$$\text{TVL} = \text{HVL} \times \frac{\ln(10)}{\ln(2)} = 1.5 \text{ cm} \times \frac{2.303}{0.693} = 1.5 \text{ cm} \times 3.32 = 4.98 \text{ cm}$$

Therefore, approximately 5 cm of lead would be required to reduce the intensity to 1/10th of its original value.

[INTERACTIVE EXERCISE: Shielding Calculator]
This interactive tool allows you to calculate required shielding thickness for different radiation types, energies, and materials. Input the radiation type, energy, desired attenuation factor, and material to determine the necessary thickness.

## Content Section 5: Radiation Quantities and Units

### Subsection 5.1: Physical Quantities
Several physical quantities are used to describe radiation fields and energy deposition:

**Fluence ($\Phi$)**: The number of particles incident on a sphere of cross-sectional area $dA$:

$$\Phi = \frac{dN}{dA}$$

Units: particles/m²

**Energy Fluence ($\Psi$)**: The energy incident on a sphere of cross-sectional area $dA$:

$$\Psi = \frac{dE}{dA}$$

Units: J/m²

**Kerma ($K$)**: Kinetic Energy Released per unit MAss, representing the energy transferred from uncharged particles to charged particles:

$$K = \frac{dE_{tr}}{dm}$$

Units: Gray (Gy) = J/kg

**Absorbed Dose ($D$)**: Energy imparted by ionizing radiation per unit mass:

$$D = \frac{d\varepsilon}{dm}$$

Units: Gray (Gy) = J/kg

The relationship between these quantities is important for understanding radiation protection measurements and calculations.

### Subsection 5.2: Protection Quantities
Protection quantities are used to express biological risk from radiation exposure:

**Equivalent Dose ($H_T$)**: Absorbed dose averaged over a tissue or organ and weighted for radiation quality:

$$H_T = \sum_R w_R \times D_{T,R}$$

Where:
- $w_R$ is the radiation weighting factor
- $D_{T,R}$ is the absorbed dose in tissue $T$ from radiation type $R$

Units: Sievert (Sv)

**Radiation Weighting Factors ($w_R$)** account for the different biological effectiveness of different radiation types:

| Radiation Type | Energy Range | $w_R$ |
|----------------|--------------|-------|
| Photons | All energies | 1 |
| Electrons, muons | All energies | 1 |
| Protons | > 2 MeV | 2 |
| Alpha particles | All energies | 20 |
| Neutrons | < 10 keV | 10 |
| | 10-100 keV | 20 |
| | 100 keV - 2 MeV | 10 |
| | 2-20 MeV | 5 |
| | > 20 MeV | 2.5 |

**Effective Dose ($E$)**: Sum of the weighted equivalent doses in all tissues and organs:

$$E = \sum_T w_T \times H_T$$

Where:
- $w_T$ is the tissue weighting factor
- $H_T$ is the equivalent dose in tissue $T$

Units: Sievert (Sv)

**Tissue Weighting Factors ($w_T$)** represent the relative contribution of individual tissues and organs to overall radiation detriment:

| Tissue/Organ | $w_T$ | $\sum w_T$ |
|--------------|-------|------------|
| Bone marrow, colon, lung, stomach, breast, remainder tissues | 0.12 | 0.72 |
| Gonads | 0.08 | 0.08 |
| Bladder, esophagus, liver, thyroid | 0.04 | 0.16 |
| Bone surface, brain, salivary glands, skin | 0.01 | 0.04 |
| **Total** | | **1.00** |

### Subsection 5.3: Operational Quantities
Operational quantities are used for practical radiation monitoring:

**Ambient Dose Equivalent ($H^*(d)$)**: Dose equivalent at a point in a radiation field that would be produced by the corresponding expanded and aligned field in the ICRU sphere at depth $d$ on the radius opposing the direction of the aligned field.

Units: Sievert (Sv)

**Personal Dose Equivalent ($H_p(d)$)**: Dose equivalent in soft tissue at an appropriate depth $d$ below a specified point on the body.

Units: Sievert (Sv)

Common depths used are:
- $H_p(10)$ for effective dose (deep dose)
- $H_p(3)$ for eye lens dose
- $H_p(0.07)$ for skin dose

These operational quantities are what is actually measured by radiation monitoring devices and then used to estimate protection quantities.

[TABLE: Comparison of Physical, Protection, and Operational Quantities]

| Category | Quantity | Symbol | Unit | Purpose |
|----------|----------|--------|------|---------|
| Physical | Absorbed Dose | $D$ | Gray (Gy) | Measure energy deposition |
| | Kerma | $K$ | Gray (Gy) | Measure energy transfer |
| Protection | Equivalent Dose | $H_T$ | Sievert (Sv) | Account for radiation quality |
| | Effective Dose | $E$ | Sievert (Sv) | Account for tissue sensitivity |
| Operational | Ambient Dose Equivalent | $H^*(d)$ | Sievert (Sv) | Area monitoring |
| | Personal Dose Equivalent | $H_p(d)$ | Sievert (Sv) | Individual monitoring |

## Content Section 6: Radiation Weighting Factors and Effective Dose

### Subsection 6.1: Biological Basis for Weighting Factors
Radiation and tissue weighting factors are based on radiobiological considerations:

**Radiation Weighting Factors ($w_R$)** are related to the concept of Relative Biological Effectiveness (RBE), which compares the biological effect of different radiation types:

$$\text{RBE} = \frac{\text{Dose of reference radiation to produce effect}}{\text{Dose of test radiation to produce same effect}}$$

The primary determinant of RBE is the linear energy transfer (LET) of the radiation, which describes the energy deposition density along the particle track:

$$\text{LET} = \frac{dE}{dl}$$

Where:
- $dE$ is the energy deposited
- $dl$ is the distance traveled

High-LET radiations (alpha particles, neutrons) produce more dense ionization patterns, causing more complex DNA damage that is harder to repair, resulting in higher biological effectiveness.

**Tissue Weighting Factors ($w_T$)** are based on:
1. Cancer incidence and mortality data from epidemiological studies
2. Risk of heritable effects
3. Years of life lost
4. Reduction in quality of life

The values are averaged over all ages and both genders to provide a simplified system applicable to all members of the population.

### Subsection 6.2: Calculating Effective Dose
Effective dose calculation involves several steps:

1. Determine the absorbed dose ($D_{T,R}$) to each tissue/organ from each radiation type
2. Apply radiation weighting factors ($w_R$) to get equivalent dose ($H_T$)
3. Apply tissue weighting factors ($w_T$) to get weighted equivalent doses
4. Sum all weighted equivalent doses to get effective dose ($E$)

**Example Calculation:**
A radiation oncology technologist receives the following organ doses during a procedure:

- Lungs: 0.5 mGy from photons
- Thyroid: 0.3 mGy from photons
- Skin (hands): 1.2 mGy from photons

Calculate the effective dose:

Step 1: Calculate equivalent doses (for photons, $w_R = 1$)
$H_{lungs} = 0.5 \text{ mGy} \times 1 = 0.5 \text{ mSv}$
$H_{thyroid} = 0.3 \text{ mGy} \times 1 = 0.3 \text{ mSv}$
$H_{skin} = 1.2 \text{ mGy} \times 1 = 1.2 \text{ mSv}$

Step 2: Apply tissue weighting factors
$w_T \times H_{lungs} = 0.12 \times 0.5 \text{ mSv} = 0.06 \text{ mSv}$
$w_T \times H_{thyroid} = 0.04 \times 0.3 \text{ mSv} = 0.012 \text{ mSv}$
$w_T \times H_{skin} = 0.01 \times 1.2 \text{ mSv} = 0.012 \text{ mSv}$

Step 3: Calculate effective dose
$E = 0.06 \text{ mSv} + 0.012 \text{ mSv} + 0.012 \text{ mSv} = 0.084 \text{ mSv}$

### Subsection 6.3: Limitations and Practical Considerations
While effective dose is a useful concept, it has several limitations:

1. **Uncertainty**: Tissue weighting factors have considerable uncertainty
2. **Population Averaging**: Values represent population averages, not individual risks
3. **Age and Gender Independence**: Does not account for age and gender differences
4. **Prospective Use**: Designed for prospective radiation protection, not retrospective risk assessment
5. **Medical Exposures**: Limited applicability to patient doses in medical procedures

Practical considerations when using effective dose include:

1. **Avoid Precision Illusion**: Report effective dose with appropriate significant figures
2. **Context**: Always provide context when communicating effective dose
3. **Comparisons**: Use effective dose for comparing different practices or techniques
4. **Record Keeping**: Maintain records of both equivalent and effective doses
5. **Dose Limits**: Compare with appropriate dose limits for workers or public

[INTERACTIVE EXERCISE: Effective Dose Calculator]
This interactive tool allows you to calculate effective dose by inputting absorbed doses to different organs and automatically applying the appropriate weighting factors.

## Clinical Application
A radiation oncology department is planning to implement a new high-dose-rate (HDR) brachytherapy program. The radiation safety officer must evaluate radiation protection requirements for the facility and staff.

The proposed treatment room has concrete walls of 20 cm thickness. The HDR unit will contain a 370 GBq (10 Ci) Ir-192 source. Staff will operate the unit from an adjacent control room. The workload is estimated at 10 patients per week, with an average treatment time of 15 minutes per patient.

**Radiation Protection Analysis:**

1. **Time Considerations:**
   - Total weekly time with source exposed: 10 patients × 15 minutes = 150 minutes = 2.5 hours
   - Staff exposure time can be minimized by:
     - Efficient patient setup before source loading
     - Remote monitoring during treatment
     - Automated source retraction after treatment

2. **Distance Considerations:**
   - Control console located in adjacent room (approximately 3 meters from source)
   - Using the inverse square law, dose rate at console (without shielding) would be:
     - Dose rate at 1 m from 370 GBq Ir-192: approximately 40 mSv/h
     - Dose rate at 3 m: 40 mSv/h × (1/3)² = 4.44 mSv/h

3. **Shielding Evaluation:**
   - For Ir-192 (average energy ~0.38 MeV), the TVL in concrete is approximately 15 cm
   - With 20 cm concrete walls: Transmission factor = 10^(-(20/15)) = 10^(-1.33) = 0.047
   - Dose rate at console with shielding: 4.44 mSv/h × 0.047 = 0.21 mSv/h
   - Weekly dose at console: 0.21 mSv/h × 2.5 h = 0.525 mSv/week
   - Annual dose (50 weeks): 26.25 mSv/year

4. **ALARA Implementation:**
   - This exceeds the recommended constraint of 10 mSv/year for occupational exposure
   - Additional shielding is needed: adding 5 cm of concrete (1/3 TVL) would reduce dose by factor of 2
   - Procedural controls: rotating staff assignments to distribute dose
   - Engineering controls: adding lead-lined door between control area and treatment room
   - Administrative controls: establishing restricted areas during source exposure

5. **Monitoring Requirements:**
   - Personal dosimeters (whole body and extremity) for all staff
   - Area monitors at console and adjacent areas
   - Regular radiation surveys during initial treatments
   - Quarterly review of dosimetry reports

This analysis demonstrates the practical application of fundamental radiation protection principles in a clinical radiation oncology setting.

## Key Points Summary
- Radiation protection is based on understanding biological effects, including deterministic effects (with thresholds) and stochastic effects (without thresholds)
- The linear no-threshold model forms the basis for protection against stochastic effects
- Radiation protection has evolved from early observations to a comprehensive framework based on justification, optimization, and limitation
- The ALARA principle requires keeping doses as low as reasonably achievable, considering economic and social factors
- Time, distance, and shielding are the three fundamental methods of radiation protection
- Radiation quantities include physical quantities (absorbed dose), protection quantities (equivalent and effective dose), and operational quantities (ambient and personal dose equivalent)
- Radiation and tissue weighting factors account for different biological effectiveness of radiation types and different tissue sensitivities
- Effective dose provides a way to express the overall risk from partial body exposures but has limitations that must be considered

## Check Your Understanding
1. Which of the following is a deterministic effect of radiation exposure?
   - A) Leukemia
   - B) Radiation-induced cataract
   - C) Solid tumor induction
   - D) Genetic effects in offspring
   
   Answer: B) Radiation-induced cataract. Cataracts are a deterministic effect with a threshold dose, while the other options are stochastic effects.

2. According to the inverse square law, if the dose rate at 1 meter from a point source is 100 mSv/h, what would be the dose rate at 5 meters?
   - A) 20 mSv/h
   - B) 4 mSv/h
   - C) 25 mSv/h
   - D) 5 mSv/h
   
   Answer: B) 4 mSv/h. Using the inverse square law: 100 mSv/h × (1/5)² = 100 mSv/h × 0.04 = 4 mSv/h.

3. Calculate the effective dose for a worker who receives the following organ doses from photon radiation: bone marrow 2 mGy, thyroid 5 mGy, and skin 10 mGy.
   - A) 0.54 mSv
   - B) 17 mSv
   - C) 0.74 mSv
   - D) 1.7 mSv
   
   Answer: A) 0.54 mSv. Effective dose = (0.12 × 2 mSv) + (0.04 × 5 mSv) + (0.01 × 10 mSv) = 0.24 mSv + 0.2 mSv + 0.1 mSv = 0.54 mSv.

4. Which of the following best describes the ALARA principle?
   - A) All doses must be kept below regulatory limits
   - B) Doses should be as low as reasonably achievable, considering economic and social factors
   - C) All radiation exposure should be avoided regardless of benefit
   - D) Average doses should be reduced annually regardless of cost
   
   Answer: B) Doses should be as low as reasonably achievable, considering economic and social factors. This is the definition of the ALARA principle.

5. What is the primary purpose of using tissue weighting factors in radiation protection?
   - A) To account for different radiation types
   - B) To account for different tissue sensitivities to radiation
   - C) To convert absorbed dose to equivalent dose
   - D) To measure operational quantities
   
   Answer: B) To account for different tissue sensitivities to radiation. Tissue weighting factors reflect the relative contribution of individual tissues and organs to overall radiation detriment.

## References
1. International Commission on Radiological Protection. The 2007 Recommendations of the International Commission on Radiological Protection. ICRP Publication 103. Ann ICRP. 2007;37(2-4):1-332.
2. National Council on Radiation Protection and Measurements. Structural Shielding Design and Evaluation for Megavoltage X- and Gamma-Ray Radiotherapy Facilities. NCRP Report No. 151. Bethesda, MD: NCRP; 2005.
3. International Atomic Energy Agency. Radiation Protection and Safety of Radiation Sources: International Basic Safety Standards. IAEA Safety Standards Series No. GSR Part 3. Vienna: IAEA; 2014.
4. Podgorsak EB, ed. Radiation Oncology Physics: A Handbook for Teachers and Students. Vienna: International Atomic Energy Agency; 2005.
5. Martin CJ, Sutton DG, eds. Practical Radiation Protection in Healthcare. 2nd ed. Oxford: Oxford University Press; 2015.
