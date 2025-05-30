## Subsection 2.3: Dose-Rate Effects

### Learning Objectives
After completing this subsection, you will be able to:
1. Explain how dose rate influences radiobiological effects at cellular and tissue levels
2. Apply the linear-quadratic model to quantify dose-rate effects
3. Compare and contrast the biological effects of different dose-rate categories
4. Evaluate the clinical implications of dose-rate effects in various radiation therapy modalities
5. Analyze the emerging evidence regarding ultra-high dose-rate (FLASH) radiotherapy

### Mathematical Foundation
Before exploring dose-rate effects in detail, let's review some key mathematical concepts that are essential for understanding this topic:

**Repair Kinetics Equations**:
- First-order repair kinetics: R(t) = R₀e^(-μt)
- Where R(t) is the amount of repairable damage at time t
- R₀ is the initial amount of repairable damage
- μ is the repair rate constant (related to repair half-time: T½ = ln(2)/μ)

**Continuous Low Dose-Rate Irradiation**:
- Lea-Catcheside time factor: G = (2/μD²)∫₀ᵀ R(t)(dD/dt)dt
- For continuous irradiation at constant dose rate: G = (2/μT)(1 - (1-e^(-μT))/μT)
- As T approaches infinity: G approaches 1/μT
- As T approaches zero: G approaches 1

**Incomplete Repair Model**:
- For fractionated irradiation: S = e^(-αD-βD²Hm)
- Where Hm is the incomplete repair factor
- For m fractions separated by time t: Hm = (1/m) + (2/m²)∑ᵢ₌₁ᵐ⁻¹∑ⱼ₌ᵢ₊₁ᵐe^(-μ(j-i)t)
- As t approaches infinity: Hm approaches 1/m (complete repair)
- As t approaches zero: Hm approaches 1 (no repair)

**Biologically Effective Dose Modification**:
- For protracted irradiation: BED = D(1 + G·d/(α/β))
- Where G is the Lea-Catcheside time factor
- For acute irradiation: G = 1
- For continuous irradiation at dose rate R for time T: G = (2/μT)(1 - (1-e^(-μT))/μT)

### Core Content

#### Fundamental Concepts of Dose Rate

Dose rate, the amount of radiation dose delivered per unit time, is a critical determinant of biological effect. The influence of dose rate on radiobiological response is complex and depends on multiple factors:

**Definition and Units**:
- Dose rate (Ṙ) = dose (D) / time (T)
- Standard units: Gy/min, Gy/h, or mGy/h
- Range in radiation therapy: 0.01 Gy/h to >100 Gy/s
- Range in radiation protection: μGy/h to mGy/h

**Dose-Rate Categories**:
1. **Ultra-Low Dose Rate (ULDR)**:
   - <0.01 Gy/h
   - Examples: Environmental background, radiation protection scenarios
   - Biological effects: Potential adaptive responses, bystander effects

2. **Low Dose Rate (LDR)**:
   - 0.01-1 Gy/h
   - Examples: LDR brachytherapy, some radioisotope therapies
   - Biological effects: Significant repair during irradiation, reduced cell killing

3. **Medium Dose Rate (MDR)**:
   - 1-10 Gy/h
   - Examples: HDR brachytherapy with distance, some radioisotope therapies
   - Biological effects: Partial repair during irradiation

4. **High Dose Rate (HDR)**:
   - >10 Gy/h (typically 1-3 Gy/min)
   - Examples: External beam radiotherapy, HDR brachytherapy
   - Biological effects: Minimal repair during irradiation

5. **Ultra-High Dose Rate (UHDR)/FLASH**:
   - >40 Gy/s (>2400 Gy/min)
   - Examples: Experimental FLASH radiotherapy
   - Biological effects: Oxygen depletion, reduced normal tissue toxicity

**Historical Development**:
- Strandqvist (1944): First clinical observations of fractionation and protraction effects
- Bedford and Hall (1963): Quantitative analysis of dose-rate effects
- Thames (1985): Development of incomplete repair model
- Steel (1989): Comprehensive dose-rate effect modeling
- Favaudon (2014): Discovery of FLASH effect at ultra-high dose rates

**Biological Basis of Dose-Rate Effects**:
- DNA damage repair during irradiation
- Redistribution of cells in cell cycle
- Reoxygenation of hypoxic cells
- Repopulation of cells between fractions
- Molecular signaling and stress responses

The fundamental importance of dose rate lies in its influence on the balance between damage induction and repair processes, which ultimately determines the biological outcome of radiation exposure.

#### Mechanistic Basis of Dose-Rate Effects

The biological effects of dose rate are primarily mediated through several key mechanisms:

**DNA Damage Repair During Irradiation**:
- Low dose rates allow repair of sublethal damage during irradiation
- Repair enzymes compete with damage induction
- Repair kinetics typically follow first-order processes
- Repair half-times for sublethal damage: 0.2-3 hours
- Different repair pathways have different kinetics:
  - Non-homologous end joining (NHEJ): Fast (minutes to hours)
  - Homologous recombination (HR): Slow (hours)
  - Base excision repair (BER): Very fast (minutes)

**Quadratic Component Reduction**:
- Low dose rates primarily affect the β component of the LQ model
- Reduced probability of interaction between lesions from separate tracks
- First lesion may be repaired before second lesion occurs
- Effective reduction in the quadratic term: βD² → βD²G
- G (Lea-Catcheside time factor) decreases with decreasing dose rate

**Cell Cycle Effects**:
- Protracted irradiation allows cell cycle progression during exposure
- Redistribution into more radioresistant phases (S phase)
- Accumulation at G2/M checkpoint
- Activation of checkpoint-dependent repair processes
- Differential effects based on cell cycle time relative to irradiation time

**Reoxygenation Effects**:
- Low dose rates allow reoxygenation during treatment
- Consumption of oxygen during irradiation (especially at UHDR)
- Changes in tumor microenvironment during protracted exposure
- Differential effects on hypoxic vs. well-oxygenated cells
- Potential radiobiological advantage for hypoxic tumors

**Molecular Signaling Responses**:
- Dose-rate dependent activation of stress response pathways
- Differential gene expression patterns
- Activation of adaptive responses at very low dose rates
- Bystander signaling effects
- Immunological responses

**Tissue-Specific Considerations**:
- Repair capacity varies between tissues
- Proliferation rates influence dose-rate effects
- Vascular responses differ with dose rate
- Stem cell compartment responses
- Microenvironmental factors

These mechanisms interact in complex ways to produce the overall dose-rate effect, which can be quantified using mathematical models derived from the linear-quadratic framework.

#### Mathematical Modeling of Dose-Rate Effects

The linear-quadratic model can be extended to account for dose-rate effects through several mathematical approaches:

**Lea-Catcheside Time Factor**:
- Modifies the quadratic component of the LQ model
- S = e^(-αD-βD²G)
- G is the generalized time factor (0 ≤ G ≤ 1)
- G = 1 for acute irradiation (high dose rate)
- G decreases as dose rate decreases or irradiation time increases
- General form: G = (2/D²)∫₀ᵀ∫₀ᵗ R(t-u)(dD/dt)(dD/du)dudt
- Where R(t) is the repair function: R(t) = e^(-μt)

**Continuous Irradiation at Constant Dose Rate**:
- For dose rate Ṙ over time T (D = Ṙ·T)
- G = (2/μT)(1 - (1-e^(-μT))/μT)
- As T approaches infinity (very low dose rate): G approaches 0
- As T approaches zero (very high dose rate): G approaches 1
- For intermediate cases:
  - T = 0.5/μ: G ≈ 0.76
  - T = 1/μ: G ≈ 0.63
  - T = 2/μ: G ≈ 0.43

**Incomplete Repair Model for Fractionated Irradiation**:
- For multiple fractions with incomplete repair between fractions
- S = e^(-αD-βD²Hm)
- Hm is the incomplete repair factor
- For m equal fractions separated by time t:
  - Hm = (1/m) + (2/m²)∑ᵢ₌₁ᵐ⁻¹∑ⱼ₌ᵢ₊₁ᵐe^(-μ(j-i)t)
- For two fractions: H₂ = 0.5 + 0.5e^(-μt)
- As t approaches infinity: Hm approaches 1/m (complete repair)
- As t approaches zero: Hm approaches 1 (no repair)

**Biologically Effective Dose Modification**:
- For protracted irradiation: BED = D(1 + G·d/(α/β))
- For continuous irradiation at constant dose rate Ṙ for time T:
  - BED = D(1 + (2Ṙ/μ(α/β))(1 - (1-e^(-μT))/μT))
- For very low dose rate (T → ∞):
  - BED approaches D(1 + Ṙ/(μ(α/β)))
- For very high dose rate (T → 0):
  - BED approaches D(1 + d/(α/β))

**Repair Half-Time Considerations**:
- Repair half-time (T½) related to repair rate constant: T½ = ln(2)/μ
- Typical values:
  - Early-responding tissues: 0.5-1 hour
  - Late-responding tissues: 1.5-3 hours
  - Variation between tissues and individuals
- Impact on dose-rate effect:
  - Longer T½ (slower repair): Greater dose-rate effect
  - Shorter T½ (faster repair): Smaller dose-rate effect

**Limitations of Mathematical Models**:
- Assume homogeneous cell populations
- Typically consider only one repair component
- May not account for cell cycle effects
- Do not incorporate reoxygenation or repopulation
- Limited applicability to very high or very low dose rates

These mathematical models provide a framework for quantifying dose-rate effects and predicting the impact of changing dose rate on biological outcomes in various clinical scenarios.

#### Dose-Rate Effects in Different Radiation Therapy Modalities

Dose-rate effects have significant implications for various radiation therapy modalities:

**External Beam Radiation Therapy (EBRT)**:
- Conventional EBRT: 1-6 Gy/min (HDR)
  - Minimal dose-rate effect within treatment fraction
  - Repair between fractions is primary radiobiological factor
  - Dose-rate variations between machines generally not clinically significant

- Intensity-Modulated Radiation Therapy (IMRT):
  - Effective dose rate reduced due to extended delivery time
  - "Beam-on" time may extend to 10-15 minutes
  - Potential for repair during delivery (especially for large targets)
  - Clinical significance debated but generally minimal

- Stereotactic Body Radiation Therapy (SBRT):
  - High doses per fraction (6-30 Gy)
  - Delivery times often extended (15-45 minutes)
  - Potential repair during delivery may reduce biological effectiveness
  - May partially explain why LQ model overestimates effect at high doses

**Brachytherapy**:
- Low Dose Rate (LDR) Brachytherapy:
  - 0.4-2 Gy/h, delivered over days to weeks
  - Significant repair during irradiation
  - Reduced biological effect per unit dose
  - Compensated by higher total physical doses
  - Examples: Permanent prostate implants (I-125, Pd-103)
  - BED calculation: BED = D(1 + (Ṙ/(μ(α/β))))

- High Dose Rate (HDR) Brachytherapy:
  - >12 Gy/h, typically delivered in minutes
  - Minimal repair during irradiation
  - Similar to EBRT in biological effectiveness
  - Examples: Temporary implants using Ir-192
  - BED calculation: BED = D(1 + d/(α/β))

- Pulsed Dose Rate (PDR) Brachytherapy:
  - Series of short HDR pulses (typically hourly)
  - Simulates continuous LDR
  - Incomplete repair between pulses
  - BED calculation requires incomplete repair model
  - Examples: Gynecological, head and neck applications

**Particle Therapy**:
- Proton Therapy:
  - Similar dose rates to conventional EBRT
  - Dose-rate effects comparable to photon therapy
  - Potential for enhanced repair inhibition due to LET effects

- Carbon Ion Therapy:
  - High-LET radiation reduces importance of dose-rate effects
  - Repair inhibition from complex damage
  - Less dependence on quadratic component
  - Reduced dose-rate effect compared to low-LET radiation

**Radiopharmaceutical Therapy**:
- Targeted Radionuclide Therapy:
  - Very low dose rates (0.01-0.5 Gy/h)
  - Continuous irradiation over days to weeks
  - Significant repair during irradiation
  - Examples: I-131 for thyroid cancer, Lu-177 for neuroendocrine tumors
  - BED calculation must account for physical and biological half-lives

- Radium-223 for Bone Metastases:
  - Alpha emitter with high LET
  - Reduced importance of dose-rate effects
  - Complex microdosimetry considerations

**FLASH Radiotherapy**:
- Ultra-high dose rates (>40 Gy/s)
  - Entire fraction delivered in milliseconds
  - Emerging evidence for reduced normal tissue toxicity
  - Tumor control appears maintained
  - Potential for improved therapeutic ratio
  - Mechanisms under investigation (oxygen depletion hypothesis)

Understanding dose-rate effects across these modalities is essential for accurate biological dose calculation, treatment planning, and modality selection based on tumor and normal tissue characteristics.

#### Clinical Implications of Dose-Rate Effects

Dose-rate effects have numerous clinical implications that influence treatment planning, modality selection, and outcome prediction:

**Equivalent Dose Calculations**:
- Conversion between different dose rates requires radiobiological modeling
- For LDR to HDR conversion:
  - BEDHDR = BEDLDR
  - DHDR(1 + dHDR/(α/β)) = DLDR(1 + (ṘLDR/(μ(α/β))))
  - Solving for DHDR gives equivalent HDR dose
- Clinical example: LDR vs. HDR brachytherapy for prostate cancer
  - 145 Gy LDR (I-125) ≈ 38 Gy in 4 fractions HDR
  - Assumes prostate α/β = 1.5 Gy, μ = 0.46 h⁻¹

**Treatment Planning Considerations**:
- Accounting for treatment delivery time in IMRT/VMAT
  - Extended delivery reduces biological effectiveness
  - May require dose adjustment for very large targets
  - More significant for tissues with fast repair kinetics

- Fractionation schedule design
  - Twice-daily treatments require sufficient interfraction interval
  - Typically 6-8 hours minimum between fractions
  - Based on repair half-times of late-responding tissues
  - Incomplete repair may increase late effects

- Brachytherapy optimization
  - Source selection based on half-life and dose rate
  - Dwell time optimization in HDR
  - Activity selection in LDR
  - Biological optimization incorporating repair parameters

**Modality Selection Based on Tumor Characteristics**:
- Rapidly proliferating tumors
  - Benefit from shorter overall treatment time
  - HDR approaches may be advantageous
  - Reduced opportunity for accelerated repopulation

- Hypoxic tumors
  - May benefit from LDR approaches
  - Allows reoxygenation during treatment
  - Particularly relevant for large tumors with hypoxic regions

- Repair-proficient tumors
  - More sensitive to dose-rate effects
  - May benefit from HDR approaches
  - Reduced opportunity for repair during delivery

**Normal Tissue Considerations**:
- Late-responding tissues
  - More sensitive to dose-rate effects (lower α/β, slower repair)
  - Greater sparing with LDR for same tumor effect
  - Critical for tissues with severe late complications

- Early-responding tissues
  - Less sensitive to dose-rate effects (higher α/β, faster repair)
  - Acute effects similar across dose rates for equivalent BED
  - Important for tolerance during treatment

**Special Clinical Scenarios**:
- Total Body Irradiation (TBI)
  - Traditional low dose rate (0.05-0.1 Gy/min)
  - Reduced toxicity compared to higher dose rates
  - Particularly important for pulmonary and renal toxicity
  - Modern techniques may use higher dose rates with lung blocking

- Pediatric radiation therapy
  - Potentially greater dose-rate effects due to developing tissues
  - Repair capacity differences in pediatric tissues
  - Long-term effects consideration paramount

- Re-irradiation
  - Repair capacity may be altered in previously irradiated tissues
  - Dose-rate effects may differ from primary treatment
  - Conservative approach to dose-rate selection recommended

**Emerging Clinical Applications**:
- FLASH Radiotherapy
  - Ultra-high dose rates show normal tissue sparing
  - Potential paradigm shift in radiation therapy
  - Clinical trials in planning stages
  - Technical challenges in implementation

- Spatially Fractionated Radiation Therapy (SFRT)
  - Very high doses to small volumes
  - Delivery time influences biological effect
  - Dose-rate considerations critical for modeling

- MR-guided adaptive radiotherapy
  - Extended treatment times due to adaptation
  - Potential repair during imaging and replanning
  - Biological effect modeling needed

Understanding these clinical implications allows radiation oncologists to optimize treatment approaches based on dose-rate considerations, potentially improving the therapeutic ratio for various clinical scenarios.

#### FLASH Radiotherapy: Ultra-High Dose-Rate Effects

FLASH radiotherapy, utilizing ultra-high dose rates (>40 Gy/s), represents an emerging paradigm with unique radiobiological properties:

**Historical Development**:
- Initial observations in 1960s-1970s (rarely pursued)
- Rediscovery by Favaudon et al. (2014)
- Demonstration of normal tissue sparing in mice
- Maintenance of tumor control
- Rapid expansion of research (2015-present)
- First human treatment (2019): basal cell carcinoma

**Defining Characteristics**:
- Dose rates >40 Gy/s (typically 100-1000 Gy/s)
- Entire treatment delivered in milliseconds
- Total dose similar to conventional therapy
- Pulse structure varies by technology
- Beam-on time typically <100 ms
- Currently limited to electrons, development for photons/protons

**The FLASH Effect**:
- Differential response between tumors and normal tissues
- Normal tissue sparing (30-70% reduction in toxicity)
  - Demonstrated in skin, lung, brain, GI tract
  - Preserved cognitive function
  - Reduced fibrosis
  - Decreased inflammation
- Tumor control equivalent to conventional dose rates
- Potential for improved therapeutic ratio
- Threshold dose rate approximately 40 Gy/s
- Requires delivery of entire fraction at FLASH dose rates

**Proposed Mechanisms**:
1. **Oxygen Depletion Hypothesis** (most supported):
   - Rapid consumption of oxygen during ultra-fast delivery
   - Transient hypoxia in normal tissues
   - Reduced oxygen enhancement ratio
   - Differential effect due to baseline oxygenation differences
   - Supported by:
     - Absence of FLASH effect in hypoxic conditions
     - Dependence on initial oxygen concentration
     - Mathematical modeling of oxygen diffusion

2. **Radiochemical Mechanism**:
   - Altered free radical chemistry at ultra-high dose rates
   - Reduced production of reactive oxygen species
   - Different spectrum of DNA damage
   - Supported by:
     - Pulse structure dependence
     - Differential effects with radical scavengers

3. **Immune System Modulation**:
   - Altered inflammatory response
   - Different cytokine profile
   - Modified immune cell recruitment
   - Supported by:
     - Reduced inflammatory infiltrates
     - Different cytokine expression patterns
     - Dependence on immune status

4. **DNA Damage Response Differences**:
   - Altered repair pathway engagement
   - Overwhelmed repair systems
   - Different spectrum of DNA damage
   - Supported by:
     - Differences in γH2AX foci
     - Altered repair kinetics
     - Differential gene expression

**Technical Challenges**:
- Dosimetry at ultra-high dose rates
  - Detector saturation
  - Recombination effects
  - Need for specialized dosimetry systems
  - Real-time monitoring challenges

- Beam delivery systems
  - Modified linear accelerators
  - Specialized electron beam systems
  - Synchrocyclotrons for proton FLASH
  - Limited field sizes currently

- Treatment planning
  - Lack of validated biological models
  - Uncertainty in RBE and dose prescription
  - Need for specialized algorithms

**Clinical Translation Status**:
- First human treatment (2019): single patient with resistant skin lymphoma
- Veterinary trials ongoing
- Phase I trials in planning stages
  - Skin cancers
  - Palliative treatments
  - Limited volume treatments

- Potential early applications:
  - Partial breast irradiation
  - Extremity sarcomas
  - Skin cancers
  - Palliative treatments

- Long-term vision:
  - Potential paradigm shift in radiotherapy
  - Possible dose escalation
  - Reduced normal tissue complications
  - Expanded indications for radiotherapy

FLASH radiotherapy represents a potentially transformative approach that challenges conventional radiobiological understanding of dose-rate effects. While still in early stages of development, it highlights the continued importance of dose rate as a fundamental determinant of biological response to radiation.

### Clinical Correlation: Dose-Rate Effects in Prostate Brachytherapy

**Case Example**: A 68-year-old man with intermediate-risk prostate cancer (cT2a, Gleason 3+4=7, PSA 8.5 ng/mL) is being evaluated for definitive radiation therapy. The radiation oncologist is considering three treatment options: LDR brachytherapy, HDR brachytherapy, or external beam radiation therapy (EBRT).

**Clinical Application**:

1. **Treatment Options and Dose-Rate Characteristics**:
   - LDR brachytherapy: I-125 permanent implant, 0.5-0.8 Gy/h initial dose rate, declining over months
   - HDR brachytherapy: Ir-192 temporary implant, ~1 Gy/min, delivered in 4-5 fractions
   - EBRT: 78 Gy in 39 fractions, 5 Gy/min, delivered over 8 weeks

2. **Radiobiological Assessment**:
   - Prostate cancer α/β ratio: 1.5 Gy
   - Repair half-time (T½): 1.5 hours (μ = 0.46 h⁻¹)
   - Late rectal toxicity α/β ratio: 3 Gy
   - Late urethral toxicity α/β ratio: 5 Gy

3. **BED Calculations**:
   - LDR brachytherapy (145 Gy prescribed dose):
     - Effective dose rate accounting for decay: ~0.5 Gy/h
     - BED = D(1 + (Ṙ/(μ(α/β)))) = 145(1 + (0.5/(0.46×1.5))) = 145(1 + 0.72) = 250 Gy₁.₅
     - EQD2 = 250/3 = 83.3 Gy

   - HDR brachytherapy (9.5 Gy × 4 fractions):
     - High dose rate: minimal repair during delivery
     - BED = D(1 + d/(α/β)) = 38(1 + 9.5/1.5) = 38(1 + 6.33) = 279 Gy₁.₅
     - EQD2 = 279/3 = 93 Gy

   - EBRT (78 Gy in 2 Gy fractions):
     - High dose rate: minimal repair during delivery
     - BED = D(1 + d/(α/β)) = 78(1 + 2/1.5) = 78(1 + 1.33) = 182 Gy₁.₅
     - EQD2 = 78 Gy

4. **Clinical Decision-Making**:
   - Tumor control considerations:
     - HDR brachytherapy provides highest BED (279 Gy₁.₅)
     - LDR brachytherapy intermediate BED (250 Gy₁.₅)
     - EBRT lowest BED (182 Gy₁.₅)
     - All approaches have established efficacy

   - Normal tissue considerations:
     - Rectal dose typically lowest with brachytherapy
     - Urethral dose typically highest with brachytherapy
     - LDR dose rate provides some normal tissue sparing through repair
     - HDR allows precise control of high-dose regions

   - Practical considerations:
     - LDR: Single procedure, radiation precautions for months
     - HDR: Multiple procedures/fractions, no long-term radiation precautions
     - EBRT: Daily treatments over 8 weeks, no invasive procedures

5. **Treatment Selection and Planning**:
   - HDR brachytherapy selected based on:
     - Highest tumor BED
     - Precise dose control
     - No long-term radiation precautions
     - Excellent published outcomes

   - Treatment planning considerations:
     - Catheter placement optimized for target coverage
     - Urethral dose constraints: D10% <115% of prescription
     - Rectal dose constraints: D2cc <75% of prescription
     - Optimization of dwell positions and times

This case illustrates how dose-rate effects directly inform clinical decision-making in brachytherapy, allowing quantitative comparison of different approaches through BED calculations. The significant differences in biological effectiveness between LDR and HDR approaches, despite similar physical doses, highlight the critical importance of understanding dose-rate effects in radiation oncology practice.

### Knowledge Check Questions

1. A patient receives 40 Gy via continuous low dose-rate irradiation at 0.5 Gy/h. Assuming a repair half-time of 1.5 hours and an α/β ratio of 3 Gy, what is the approximate biologically effective dose (BED)?
   A. 40 Gy₃
   B. 53 Gy₃
   C. 67 Gy₃
   D. 80 Gy₃

2. The primary mechanism responsible for the reduced biological effectiveness of low dose-rate radiation compared to high dose-rate radiation is:
   A. Increased cell cycle redistribution into resistant phases
   B. Repair of sublethal damage during irradiation
   C. Reduced oxygen enhancement ratio
   D. Increased apoptotic cell death

3. In the linear-quadratic model, dose-rate effects primarily influence which component?
   A. The linear (α) component only
   B. The quadratic (β) component only
   C. Both components equally
   D. Neither component, as the LQ model cannot account for dose-rate effects

4. A radiation oncologist is comparing two brachytherapy regimens for cervical cancer: LDR (60 Gy at 0.6 Gy/h) and HDR (7 Gy × 4 fractions). Assuming an α/β ratio of 10 Gy for tumor and repair half-time of 1.5 hours, which statement is most accurate?
   A. The LDR regimen delivers a higher biologically effective dose
   B. The HDR regimen delivers a higher biologically effective dose
   C. Both regimens deliver approximately the same biologically effective dose
   D. The comparison requires knowledge of absolute α values

5. Which of the following best describes the FLASH effect observed with ultra-high dose-rate radiotherapy?
   A. Increased tumor cell killing with equivalent normal tissue damage
   B. Decreased tumor cell killing with decreased normal tissue damage
   C. Equivalent tumor cell killing with decreased normal tissue damage
   D. Increased tumor cell killing with increased normal tissue damage

### References
1. Dale RG. The application of the linear-quadratic dose-effect equation to fractionated and protracted radiotherapy. Br J Radiol. 1985;58(690):515-528.
2. Fowler JF. 21 years of biologically effective dose. Br J Radiol. 2010;83(991):554-568.
3. Hall EJ, Brenner DJ. The dose-rate effect revisited: radiobiological considerations of importance in radiotherapy. Int J Radiat Oncol Biol Phys. 1991;21(6):1403-1414.
4. Thames HD. An 'incomplete-repair' model for survival after fractionated and continuous irradiations. Int J Radiat Biol Relat Stud Phys Chem Med. 1985;47(3):319-339.
5. Favaudon V, Caplier L, Monceau V, et al. Ultrahigh dose-rate FLASH irradiation increases the differential response between normal and tumor tissue in mice. Sci Transl Med. 2014;6(245):245ra93.
6. Wilson JD, Hammond EM, Higgins GS, Petersson K. Ultra-High Dose Rate (FLASH) Radiotherapy: Silver Bullet or Fool's Gold? Front Oncol. 2020;9:1563.
7. Joiner MC, Bentzen SM. Fractionation: the linear-quadratic approach. In: Joiner M, van der Kogel A, eds. Basic Clinical Radiobiology. 4th ed. Hodder Arnold; 2009:102-119.
