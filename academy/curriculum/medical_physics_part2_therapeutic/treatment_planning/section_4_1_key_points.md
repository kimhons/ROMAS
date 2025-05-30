# Section 4.1: Photon Treatment Planning - Key Points from Guidance Documents

This document summarizes key points extracted from relevant AAPM Task Group reports and Medical Physics Practice Guidelines (MPPGs) for Section 4.1: Photon Treatment Planning.

## Key Points from TG-53: Quality Assurance for Clinical Radiotherapy Treatment Planning (1998)

*   **Scope:** Provides a framework for comprehensive QA for modern (at the time) radiotherapy treatment planning, including 3D systems, conformal therapy, MLCs, 3D dose algorithms, and DVHs.
*   **Focus:** Emphasizes QA of the *entire treatment planning process*, not just the TPS software/hardware. Considers how the system is used and interacts with clinical workflow.
*   **Framework:** Recommends an organizational structure for QA programs, covering:
    *   Acceptance Testing: Verifying the system meets specifications upon arrival.
    *   Commissioning: Thoroughly testing and documenting system performance (nondosimetric and dosimetric aspects) before clinical use.
    *   Routine QA: Periodic checks to ensure continued accuracy and functionality.
    *   Ongoing Process QA: Integrating checks and balances within the daily clinical workflow.
*   **Individualization:** QA programs should be tailored to the specific needs, complexity, and equipment of each institution.
*   **Responsibility:** Primarily the responsibility of the Qualified Medical Physicist (QMP), but requires collaboration with dosimetrists, oncologists, therapists, and IT.
*   **Resources:** Adequate time and resources must be allocated for QA, proportional to the complexity of the planning process.
*   **Accuracy Targets:** Discusses sources of uncertainty and establishes general accuracy goals (though specific tolerances often depend on the test).
*   **Commissioning Detail:** Chapters 3 (Nondosimetric) and 4 (Dosimetric) provide extensive detail on commissioning aspects:
    *   Nondosimetric: Image acquisition/input/display, anatomical description (contouring, density), beam definition (geometry, MLCs, wedges), plan evaluation tools (DVHs, dose display), hardcopy output, data transfer, coordinate systems.
    *   Dosimetric: Measurement of consistent beam data, data input/modeling, algorithm parameterization, verification methods (comparison with measurement), specific tests for photons, electrons, brachytherapy, MU verification.
*   **Process QA (Chapter 6):** Focuses on procedural checks, documentation, plan review, communication, and ensuring consistency within the clinical workflow.
*   **System Management (Chapter 7):** Covers computer system management, data backup/security, network issues, and software version control.
*   **Appendices:** Provide examples of QA tests (nondosimetric, photon, electron, brachytherapy) and discuss vendor/user responsibilities.
*   **Key Principle:** A robust QA program is critical for patient safety, especially with increasing treatment planning complexity. Compromises for cost should not sacrifice necessary QA for the established clinical process.


## Key Points from TG-65: Tissue Inhomogeneity Corrections for Megavoltage Photon Beams (2004)

*   **Clinical Need:** Emphasizes the importance of inhomogeneity corrections due to varying tissue densities (lung, bone, air cavities) affecting dose distribution, especially with conformal treatments and dose escalation.
*   **Accuracy Requirements:** Reviews the relationship between dose accuracy and clinical outcomes (tumor control, normal tissue complications). Suggests that while 5% overall accuracy is often cited, the accuracy needed for inhomogeneity corrections themselves might be tighter (e.g., 2-3%) in critical regions, especially near interfaces or within small targets.
*   **Physics Review:** Details the underlying physics:
    *   Photon interactions (TERMA - Total Energy Released per unit MAss).
    *   Electron transport (DOSE - energy deposition by secondary electrons).
    *   Concepts of Charged Particle Equilibrium (CPE), Transient CPE (TCPE), and Lateral CPE.
    *   Influence of density and atomic number (Z) on interactions (Compton, Pair Production, Photoelectric) and electron stopping power. Density scaling is often a reasonable approximation, but Z effects can be important, especially near bone or contrast agents.
    *   Separation of primary and scattered dose components.
    *   Introduction to superposition/convolution principles as the basis for more accurate algorithms.
*   **Algorithm Categories:** Classifies algorithms based on electron transport handling and density sampling:
    *   **Category 1 (1D Density, No Electron Transport):** Simple methods like linear attenuation, effective attenuation, RTAR, Power Law (Batho). Easy to implement but inaccurate, especially near interfaces or laterally.
    *   **Category 2 (3D Density, No Electron Transport):** Methods like ETAR, dSAR, Delta Volume, dTAR, 3D Beam Subtraction. Account for 3D scatter but still lack explicit electron transport modeling. ETAR was common but has known limitations.
    *   **Category 3 (1D Density, Electron Transport):** Early convolution methods, often using FFT. Better than Cat 1/2 but limited by 1D density assumption.
    *   **Category 4 (3D Density, Electron Transport):** Superposition/Convolution (e.g., Collapsed Cone Convolution - CCC, Adaptive Convolution), Monte Carlo (MC). Considered the most accurate, explicitly modeling electron transport in 3D heterogeneous media. MC is the gold standard but computationally intensive.
*   **Data Comparisons:** Presents comparisons of different algorithms against measurements in phantoms with air, lung, and bone inhomogeneities.
    *   Highlights failures of simpler algorithms (Cat 1/2) near interfaces (dose reduction in tissue beyond air, dose increase before bone, underdose within low-density regions, overdose within bone).
    *   Shows improved accuracy of superposition/convolution and MC methods.
    *   Discusses the influence of CT number calibration on accuracy.
*   **IMRT Considerations:** Notes that inhomogeneities have a significant impact in IMRT due to steep dose gradients and small beamlets traversing heterogeneous regions. Accurate algorithms (Cat 4) are particularly important for IMRT planning.
*   **Recommendations:**
    *   Strongly recommends using algorithms that account for 3D density variations and electron transport (Category 4: Superposition/Convolution or Monte Carlo) for accurate dose calculation, especially for complex plans (IMRT) or sites with significant inhomogeneities (lung, head/neck).
    *   Emphasizes the need for thorough commissioning and validation of the chosen algorithm against measured data in heterogeneous phantoms.
    *   Advises physicists to understand the limitations of their specific TPS algorithm and communicate potential inaccuracies to oncologists.


## Key Points from TG-119 Instructions: IMRT Commissioning Tests (2009)

*   **Purpose:** Defines standard IMRT planning and delivery test cases (MultiTarget, Prostate, Head/Neck, C-Shape) to assess the overall accuracy of an IMRT system (planning, calculation, delivery).
*   **Methodology:** Uses downloadable CT/structure sets or allows creation on a local phantom. Specifies dose goals, beam arrangements (6 MV, specific gantry angles), and calculation parameters (grid <= 2mm).
*   **Measurements:** Requires three types of measurements in a water-equivalent slab phantom (15-20 cm thick):
    *   **Point Doses (Ion Chamber):** Composite plan delivery measured at specified points (isocenter, off-axis) using a small volume chamber (e.g., 0.125 cc). Dose conversion uses a ratio derived from a simple AP/PA 10x10 field measurement (Preliminary Test P1).
    *   **Planar Doses (Film):** Composite plan delivery measured on coronal planes using radiographic or radiochromic film. Film response normalized to ion chamber measurement on the same plane. Accuracy of film dosimetry should be established (Preliminary Test P2).
    *   **Field-by-Field Planar Doses:** Individual field measurements using arrays (diode, chamber), EPID, or film, comparing measured vs. predicted dose on a plane perpendicular to the beam.
*   **Analysis:**
    *   **Point Doses:** Report ratio (Measured - Planned) / Prescribed Dose.
    *   **Planar Doses (Composite & Field-by-Field):** Use Gamma analysis (3% dose difference / 3 mm distance-to-agreement). Report % points with Gamma <= 1.00. Analysis should exclude low-dose regions (e.g., <10% threshold). Specifies gamma parameters used by the task group for comparison (Absolute Dose, 10% Threshold, Van Dyk denominator = max measured point).
*   **Confidence Limits (CL):** Defines CL = |mean| + 1.96σ for point dose ratios and CL = (100 - mean pass rate) + 1.96σ for gamma pass rates. Allows comparison of local results to TG-119 published values. Exceeding TG-119 CLs may indicate a need for system review/improvement.
*   **Preliminary Tests:**
    *   **P1 (AP/PA):** Simple 10x10 fields to establish chamber dose calibration factor and baseline film/array gamma results.
    *   **P2 (Bands):** Step-wedge pattern using asymmetric jaws to test dosimetry system accuracy across a range of doses and gradients.
*   **Commissioning Test Cases:**
    *   **C1 (MultiTarget):** Stacked cylindrical targets with different dose levels.
    *   **C2 (Mock Prostate):** Ellipsoidal PTV with rectum and bladder OARs.
    *   **C3 (Mock Head/Neck):** Complex PTV including posterior neck nodes, avoiding cord and parotids.
    *   **C4 (C-Shape):** Target wrapping around a central avoidance core (two versions: 50% and 20% core dose constraints).
*   **Goal:** Provides a standardized method for institutions to benchmark their IMRT system's end-to-end accuracy against multi-institutional data.


## Key Points from TG-105: Issues Associated with Clinical Implementation of Monte Carlo-Based Photon and Electron External Beam Treatment Planning (2007)

*   **Motivation:** Monte Carlo (MC) is the most accurate method for dose calculation, especially in heterogeneous regions, but was historically too slow. Faster codes and computers make clinical MC feasible.
*   **Objective:** Educate physicists on MC principles, implementation issues, verification, and clinical implications for external beam photon/electron planning.
*   **MC Method Overview:**
    *   Statistical method simulating individual particle histories (photons, electrons, positrons) based on known interaction probabilities.
    *   Uses condensed history technique for electron transport (grouping multiple interactions into steps).
    *   Requires detailed modeling of the accelerator treatment head (source, target, flattening filter, collimators, MLCs, etc.) and patient geometry (from CT).
*   **Accelerator Head Simulation:**
    *   Crucial for accurate beam modeling.
    *   Requires detailed geometry and material specifications.
    *   Sensitivity to initial electron beam parameters (energy, spot size, angular divergence) - often requires tuning to match measured data (PDDs, profiles).
    *   Phase Space Files (PSFs): Often used to store particle information below a certain plane (e.g., below jaws) to speed up patient calculations. PSFs can be large.
    *   Virtual Source Models (VSMs): Alternative to full head simulation, using parameterized models fitted to measurements or MC simulations. May be faster but potentially less accurate, especially for complex fields or modifiers.
*   **Patient Dose Calculation:**
    *   **Statistical Uncertainty:** Inherent in MC. Dose in a voxel has statistical noise, decreasing with more particle histories (longer calculation time). Uncertainty needs to be managed (e.g., kept below 1-2% in high dose regions).
    *   **Variance Reduction Techniques (VRTs):** Methods like interaction forcing, splitting, Russian roulette used to improve efficiency (reduce calculation time for a given uncertainty), especially in challenging regions (low dose, small volumes).
    *   **CT-to-Material Conversion:** Assigning materials and densities to voxels based on CT numbers. Crucial for accuracy, especially regarding atomic composition (not just density). Different tissues (bone, lung, soft tissue) need correct assignment.
    *   **Dose-to-Water vs. Dose-to-Medium:** MC typically calculates dose-to-medium (energy absorbed per unit mass of the local material). TPS may report dose-to-water (dose if the voxel was water). Conversion involves stopping power ratios. Important to understand what the TPS reports and how it relates to clinical protocols (often based on dose-to-water).
    *   **Voxel Size:** Affects accuracy, especially in high gradient regions or near interfaces. Smaller voxels generally better but increase calculation time.
    *   **Cross Sections:** Accuracy depends on the underlying physics interaction data used by the MC code.
*   **Experimental Verification:**
    *   Essential for commissioning. MC is accurate *if implemented correctly*.
    *   Verify both the transport algorithm itself (using simple geometries) and the beam model.
    *   Requires high-quality measurements in various phantoms (homogeneous, heterogeneous with air/bone/lung inserts).
    *   Tests should include PDDs, profiles (in-field, penumbra, out-of-field), output factors (Sc, Sp, Scp), wedge fields, MLC fields, electron beams, buildup region, interface dosimetry.
    *   Compare MC calculations to measurements, considering both statistical uncertainty in MC and measurement uncertainty.
*   **Clinical Implications:**
    *   MC can reveal significant dose differences compared to simpler algorithms, especially in lung (lower dose), bone (higher dose), near air cavities, and in the buildup region.
    *   Differences can impact target coverage and OAR doses, potentially affecting TCP and NTCP.
    *   Particularly important for IMRT, SBRT, electron planning, and situations with significant heterogeneity.
*   **Summary:** MC offers superior accuracy but requires careful implementation, understanding of its principles (uncertainty, dose reporting), detailed beam modeling, and thorough experimental verification.
