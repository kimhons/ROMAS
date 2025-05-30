## Subsection 2.1: Cell Survival Curves

### Learning Objectives
After completing this subsection, you will be able to:
1.  **Describe** the fundamental principles behind clonogenic survival assays and the methodology used to perform them.
2.  **Interpret** the key features of a cell survival curve (shoulder, slope) and explain what they represent biologically (repair, intrinsic sensitivity).
3.  **Compare and contrast** the clonogenic assay with alternative methods for measuring radiation effects (e.g., metabolic assays, DNA damage markers), understanding their pros and cons.
4.  **Analyze** how factors like oxygen levels, radiation type (LET), dose rate, and cell cycle influence the shape of survival curves.
5.  **Apply** cell survival concepts (like $SF_2$, $D_0$, $\alpha/\beta$) to understand and predict radiation responses in clinical scenarios, such as choosing fractionation regimens.

### Mathematical Refresher
Understanding cell survival curves requires familiarity with a few mathematical tools:

*   **Logarithmic Scales (Specifically Log Base 10 or Natural Log):**
    *   *Why use them?* Cell survival drops dramatically with increasing radiation dose. A linear scale would squash all the interesting changes at low survival fractions. A log scale expands this region, allowing us to see effects over several orders of magnitude (e.g., from 100% survival down to 0.01% survival).
    *   *How to read them:* On a typical survival curve (log survival vs. linear dose), each major division on the vertical (Y) axis represents a tenfold *decrease* in survival (e.g., 1.0, 0.1, 0.01, 0.001).
    *   *Key Property:* Equal distances on a log scale represent equal *ratios* or *factors* of change.
*   **Exponential Functions:**
    *   *Basic Form:* Often written as $S = e^{-kD}$, where $S$ is the surviving fraction, $D$ is the dose, $e$ is the base of the natural logarithm (approx. 2.718), and $k$ is a constant related to sensitivity.
    *   *Significance:* Simple exponential decay implies that each unit of dose has the same probability of causing a lethal "hit," independent of previous hits. This is often seen at high doses or with high-LET radiation.
    *   *Linearization:* Taking the natural logarithm (ln) of both sides gives $\ln(S) = -kD$. This means if survival follows a pure exponential decay, plotting $\ln(S)$ versus $D$ yields a straight line with a negative slope $k$.
*   **Statistical Concepts:**
    *   *Experimental Variability:* Biological experiments always have variability. Repeating measurements and calculating standard errors or confidence intervals helps quantify the uncertainty in survival data points.
    *   *Poisson Distribution:* Describes the probability of a certain number of random, independent events occurring in a fixed interval (e.g., radiation "hits" in a cell nucleus). Target theory uses this to model cell killing.
    *   *Curve Fitting:* We use mathematical models (like the Linear-Quadratic model) and statistical methods (like non-linear regression) to fit a curve to the experimental data points and estimate key parameters (like $\alpha$ and $\beta$).

### Core Content

#### Historical Development of Cell Survival Assays
Understanding how we measure cell survival today requires appreciating the key historical steps:

*   **Early Qualitative Observations (1900s-1940s):**
    *   *Bergonié and Tribondeau (1906):* Made the fundamental observation that cells that divide rapidly and are less differentiated (like stem cells or cancer cells) are generally more sensitive to radiation than slowly dividing, specialized cells. This remains a cornerstone principle.
    *   *Holthusen (1921):* Began trying to quantify the relationship between dose and effect.
    *   *Lea (1946) & Target Theory:* Proposed models where radiation "hits" specific targets within the cell (like DNA). Killing occurred when a critical number of targets were hit. This provided a mathematical framework, though biologically oversimplified.
*   **The Breakthrough: Puck and Marcus (1956):**
    *   *The Clonogenic Assay:* Developed the first reliable method to quantitatively measure the reproductive survival of individual mammalian cells (using HeLa cancer cells) after irradiation.
    *   *Method:* They plated known numbers of single cells, irradiated them, and counted the number of visible colonies (clones) that grew after incubation. This allowed calculation of the surviving fraction.
    *   *Key Finding:* Showed that survival decreased exponentially with dose (at least at higher doses), establishing the basis for modern survival curves.
    *   *Gold Standard:* Their colony formation assay remains the benchmark for measuring reproductive cell death.
*   **Elkind and Sutton (1959-1960):**
    *   *Sublethal Damage Repair (SLDR):* Performed split-dose experiments: gave a dose, waited, then gave a second dose. They found survival was *higher* than if the total dose was given at once. This demonstrated that cells could *repair* some radiation damage (sublethal damage) between fractions.
    *   *The Shoulder:* This repair capacity explained the initial "shoulder" region seen on survival curves at low doses, where cell killing is less efficient.
    *   *Fractionation Basis:* Their work provided the fundamental radiobiological rationale for fractionated radiotherapy – allowing normal tissues to repair SLD between doses more effectively than some tumors.
*   **Further Refinements (Hall, Bedford, others, 1960s-present):**
    *   Techniques adapted for many different cell types (normal and tumor).
    *   Established links between *in vitro* (lab dish) survival and *in vivo* (whole organism/tumor) radiation response.
    *   Explored other repair processes like Potentially Lethal Damage Repair (PLDR) – repair that depends on post-irradiation conditions.

#### Principles of Clonogenic Survival
This assay is fundamental because it measures the most important outcome for cancer treatment: the loss of a cell's ability to divide indefinitely.

*   **1. Reproductive Death (The Key Endpoint):**
    *   *Definition:* A cell is considered reproductively "dead" if it loses the ability to undergo unlimited cell division and form a large colony (typically defined as at least 50 cells, representing about 6 cell divisions).
    *   *Why it Matters:* A cancer cell that can only divide once or twice before dying or arresting is no longer a threat – it cannot sustain tumor growth or cause recurrence. Metabolic activity or temporary survival isn't enough; indefinite proliferation is the key.
    *   *Contrast:* This is different from immediate cell death (like lysis) or apoptosis measured shortly after irradiation. Clonogenic death often occurs after several attempted, failed cell divisions (linking back to mitotic catastrophe).
*   **2. Survival Fraction (SF) (Quantifying Survival):**
    *   *The Problem:* Not every single cell plated, even without radiation, will successfully form a colony due to plating stress, inherent viability issues, etc.
    *   *Plating Efficiency (PE):* First, determine the PE of the *unirradiated* control cells. $$ PE = \frac{\text{Number of colonies formed in control dish}}{\text{Number of cells plated in control dish}} $$ 
    *   *Calculation:* For irradiated cells, the Survival Fraction (SF) is calculated as: $$ SF = \frac{\text{Number of colonies counted after irradiation}}{\text{Number of cells plated} \times PE} $$ 
    *   *Interpretation:* SF represents the fraction of cells that retained their reproductive integrity after a specific radiation dose, corrected for the baseline plating efficiency.

    *   **Clinical Scenario/Worked Example:**
        *   *Scenario:* You are testing a new radiosensitizing drug on a lung cancer cell line (A549).
        *   *Control:* You plate 200 A549 cells without radiation and count 120 colonies. $PE = 120 / 200 = 0.6$ (or 60%).
        *   *Irradiation:* You plate 1000 cells and irradiate them with 4 Gy. After incubation, you count 90 colonies.
        *   *Calculation:* $SF \text{ at 4 Gy} = 90 / (1000 \times 0.6) = 90 / 600 = 0.15$.
        *   *Conclusion:* A dose of 4 Gy reduced the surviving fraction of these cells to 15%.
*   **3. Clonogenicity vs. Other Endpoints:**
    *   *vs. Metabolic Assays (MTT, MTS, ATP):* These measure metabolic activity, which can persist even in cells doomed to die reproductively later. They are faster but less relevant for predicting long-term tumor control by radiation.
    *   *vs. Apoptosis Assays (Annexin V, Caspase):* Apoptosis is only *one* mode of radiation-induced death and often not the dominant one in solid tumors. Clonogenic assays capture cell death regardless of the mechanism (apoptosis, mitotic catastrophe, necrosis etc.) as long as it prevents colony formation.
    *   *vs. DNA Damage Markers (γH2AX):* These measure initial damage or repair kinetics, which *correlate* with survival but don't directly measure the ultimate outcome of reproductive integrity.
    *   *Relevance:* Clonogenic survival integrates the net result of damage induction, repair fidelity, and cell death pathway activation over the time needed for colony formation, making it the most biologically relevant endpoint for radiotherapy.

#### Methodology of Clonogenic Assays
Performing this assay correctly requires careful attention to detail:

*   **Basic Protocol Steps:**
    1.  **Cell Preparation:** Start with healthy, exponentially growing cells. Use enzymes (like trypsin) to detach adherent cells gently, creating a single-cell suspension. Count cells accurately (e.g., using a hemocytometer or automated counter) and check viability (e.g., using trypan blue dye exclusion to ensure you're counting live cells).
    2.  **Irradiation:** Expose the cell suspension or freshly plated cells to precise radiation doses using a calibrated source (like a clinical linear accelerator or a dedicated irradiator). Control temperature and atmosphere (e.g., $CO_2$ levels) during irradiation.
    3.  **Plating:** Plate a *known*, *accurate* number of cells into culture dishes (e.g., Petri dishes). Crucially, plate *fewer* cells for *lower* doses and *more* cells for *higher* doses to aim for a countable number of colonies (e.g., 50-200) per dish. Use multiple replicate dishes for each dose point for statistical robustness.
        *   *Example Plating Numbers:* Control (0 Gy): 200 cells; 2 Gy: 500 cells; 4 Gy: 2000 cells; 6 Gy: 8000 cells (these numbers vary greatly depending on cell line sensitivity).
    4.  **Incubation:** Place the dishes in a controlled incubator (37°C, 5% $CO_2$) for 1-3 weeks, allowing surviving cells to divide and form visible colonies.
    5.  **Colony Counting:** Fix the cells (e.g., with methanol) and stain them (e.g., with crystal violet) to make colonies easily visible. Count only the colonies that reach the predefined size threshold (e.g., $\ge 50$ cells). Use a consistent method (manual or automated) and consider blinding the counter to the dose received to avoid bias.
*   **Technical Considerations (Potential Pitfalls):**
    *   *Cell Density:* Plating too few cells can lead to poor growth; plating too many can lead to colonies merging or growth inhibition. Using irradiated "feeder" cells can sometimes help support growth at low densities.
    *   *Microenvironment:* Ensure consistent media, serum, temperature, and $CO_2$. Oxygen levels during irradiation are critical (see Oxygen Effect below).
    *   *Timing:* The time between irradiation and plating can influence repair (PLDR). Incubation time must be sufficient for colonies to reach threshold size but not so long that they merge or deplete nutrients.

#### Survival Curve Features and Interpretation
Plotting SF (log scale) vs. Dose (linear scale) reveals the characteristic curve:

*   **Key Features:**
    1.  **Shape:** Typically starts with a shallow slope (the shoulder) at low doses, then bends downwards to become steeper and often approaches a straight line at high doses (on the log-linear plot).
    2.  **Shoulder Region:** Represents the cell's ability to accumulate and repair *sublethal damage (SLD)*. A wider shoulder means the cell can tolerate more SLD before significant killing occurs. This repair is why fractionation works – cells repair SLD between fractions.
    3.  **Final Slope:** Represents the efficiency of cell killing by dose once the repair capacity is saturated or damage becomes irreparable. A steeper slope means the cells are intrinsically more sensitive to being killed by each additional unit of dose.
*   **Mathematical Models (Describing the Shape):**
    *   *Linear-Quadratic (LQ) Model:* The most widely used model in clinical radiotherapy. $$ S = e^{-(\alpha D + \beta D^2)} $$ 
        *   $\alpha$ (alpha): Represents the initial slope, related to lethal damage caused by a single radiation track (single hit). Units: $Gy^{-1}$.
        *   $\beta$ (beta): Represents the component that increases with the square of the dose, related to lethal damage caused by the interaction of two separate radiation tracks (two hits). Units: $Gy^{-2}$.
        *   The curve bends because the $\beta D^2$ term becomes more dominant at higher doses.
    *   *Multi-Target Single-Hit Model:* An older model, conceptually useful but less used now. Assumes '$n$' targets must be hit to kill the cell. $$ S = 1 - (1 - e^{-D/D_0})^n $$ 
        *   $D_0$: Dose to reduce survival to 37% on the final straight part.
        *   $n$: Extrapolation number (related to shoulder width).
*   **Interpretation Parameters (Quantifying the Curve):**
    1.  **$D_0$ (Mean Lethal Dose):** Dose on the *final exponential slope* required to reduce survival by a factor of $1/e$ (to ~37%). A lower $D_0$ means steeper slope = higher sensitivity. *Less used with the LQ model dominant.* 
    2.  **$D_q$ (Quasi-threshold Dose):** Dose at which the back-extrapolation of the final slope intersects the 100% survival line. Measures the width of the shoulder. Larger $D_q$ = more repair/broader shoulder. *Less used with the LQ model dominant.* 
    3.  **$n$ (Extrapolation Number):** The Y-intercept of the back-extrapolated final slope. Related to $D_q$ and shoulder width. Larger $n$ = broader shoulder. *Less used with the LQ model dominant.* 
    4.  **$SF_2$ (Surviving Fraction at 2 Gy):** The measured SF after a single dose of 2 Gy. 
        *   *Clinical Relevance:* 2 Gy is a common dose per fraction in conventional radiotherapy. $SF_2$ provides a practical measure of cell sensitivity in the clinically relevant low-dose region. Lower $SF_2$ = more sensitive. Often correlates well with clinical tumor response.
        *   *Typical Range:* ~0.2 (sensitive) to ~0.7 (resistant) for human tumor cell lines.
    5.  **$\alpha$ and $\beta$ Parameters (from LQ model):**
        *   $\alpha$: Dominates cell killing at low doses per fraction.
        *   $\beta$: Dominates cell killing at high doses per fraction.
        *   *$\alpha/\beta$ Ratio:* The dose at which the linear ($\alpha D$) and quadratic ($\beta D^2$) components of cell killing are equal ($\alpha D = \beta D^2 \implies D = \alpha/\beta$). This ratio is crucial for understanding tissue responses to fractionation:
            *   **Early-responding tissues & most tumors:** High $\alpha/\beta$ ratio (~10 Gy). Sensitive to changes in total dose, less sensitive to dose per fraction. $\alpha$ component dominates in conventional fractionation.
            *   **Late-responding normal tissues:** Low $\alpha/\beta$ ratio (~3 Gy). Sensitive to changes in dose per fraction. $\beta$ component is significant even at ~2 Gy/fraction.
            *   **Clinical Implication:** This difference allows therapeutic gain with fractionation – sparing late effects while still killing tumor cells. It also guides hypofractionation strategies.

    *   **Clinical Scenario/Worked Example:**
        *   *Scenario:* Lab results for two tumor cell lines:
            *   Line A: $\alpha = 0.3\ Gy^{-1}$, $\beta = 0.03\ Gy^{-2}$, $\alpha/\beta = 10\ Gy$, $SF_2 = 0.45$
            *   Line B: $\alpha = 0.1\ Gy^{-1}$, $\beta = 0.05\ Gy^{-2}$, $\alpha/\beta = 2\ Gy$, $SF_2 = 0.70$
        *   *Interpretation:* 
            *   Line A is more sensitive overall (lower $SF_2$).
            *   Line A has a high $\alpha/\beta$ ratio, typical of many tumors. Killing is dominated by the $\alpha$ component at low doses.
            *   Line B is more resistant (higher $SF_2$).
            *   Line B has a low $\alpha/\beta$ ratio, behaving more like a late-responding normal tissue. It is more sensitive to changes in dose per fraction ($\beta$ component is more important).
        *   *Clinical Thought:* Conventional fractionation (e.g., 2 Gy/fraction) might be effective for Line A. For Line B, a hypofractionated regimen (higher dose per fraction) might be needed to achieve significant killing due to the dominant $\beta$ component, but this would also increase the risk to late-responding normal tissues with similar low $\alpha/\beta$ ratios.

#### Factors Affecting Survival Curves
Many factors modify a cell's response to radiation, changing the survival curve:

*   **Intrinsic Cellular Factors (Built-in Properties):**
    1.  **Cell Type:** Different tissues/tumors have inherently different sensitivities (e.g., lymphocytes are very sensitive, fibroblasts are resistant).
    2.  **Genetic Factors:** Mutations in DNA repair genes (like ATM, BRCA) often increase sensitivity (steeper curve, less shoulder). p53 status affects checkpoint control and apoptosis propensity.
    3.  **Cell Cycle Phase:** Cells are most sensitive in M and G2 phases, most resistant in late S phase. This underlies *redistribution* during fractionation – sensitive cells are killed, surviving resistant cells progress to sensitive phases for the next fraction.
    4.  **Proliferation Status:** Rapidly dividing cells often appear more sensitive (less time for repair), but quiescent ($G_0$) cells can sometimes be very resistant.
*   **Extrinsic Modifying Factors (Environmental/Treatment Related):**
    1.  **Oxygen Effect:** Oxygen is a potent radiosensitizer.
        *   *Mechanism:* Oxygen "fixes" radiation-induced free radical damage on DNA, making it permanent and harder to repair.
        *   *Hypoxia:* Cells lacking oxygen (hypoxic) are 2.5-3 times *more resistant* to low-LET radiation. Their survival curve is shallower with a reduced $\alpha/\beta$ ratio.
        *   *OER (Oxygen Enhancement Ratio):* Ratio of dose needed under hypoxia vs. aerated conditions for the same biological effect. $OER \approx 2.5-3$ for low-LET.
        *   *Clinical Relevance:* Hypoxia is common in solid tumors and a major cause of treatment failure. Fractionation allows *reoxygenation* – killing oxygenated cells allows hypoxic cells to gain access to oxygen before the next fraction.
    2.  **Radiation Quality (LET - Linear Energy Transfer):** LET measures how densely the radiation deposits energy.
        *   *Low-LET (X-rays, gamma rays, electrons):* Sparse ionization, curvy survival curve with shoulder (repair possible).
        *   *High-LET (alpha particles, neutrons, carbon ions):* Dense ionization, straighter survival curve, minimal shoulder (less repairable, complex damage). OER is reduced (approaches 1).
        *   *RBE (Relative Biological Effectiveness):* Ratio of dose of standard radiation (e.g., X-rays) to dose of test radiation needed for the same effect. RBE generally increases with LET up to about 100 keV/μm, then decreases.
        *   *Clinical Relevance:* High-LET radiation (like proton or carbon ion therapy) can be more effective against hypoxic or repair-proficient tumors but requires careful planning due to different biological effects.
    3.  **Dose Rate:** How quickly the dose is delivered.
        *   *High Dose Rate (HDR - typical external beam):* Standard curve, minimal time for repair during delivery.
        *   *Low Dose Rate (LDR - e.g., some brachytherapy):* Allows significant SLDR *during* irradiation, leading to a shallower effective survival curve (higher survival for a given total dose).
        *   *Very Low Dose Rate:* May allow adaptive responses, further increasing resistance.
        *   *FLASH (Ultra-High Dose Rate):* Paradoxically spares normal tissues more than tumors compared to conventional dose rates (mechanism under investigation).
    4.  **Chemical Modifiers:** Drugs given with radiation.
        *   *Radiosensitizers:* Increase radiation killing (steeper curve). Examples: chemotherapy drugs (cisplatin), targeted agents (EGFR inhibitors), hypoxia modifiers.
        *   *Radioprotectors:* Decrease radiation killing (shallower curve), ideally only in normal tissues. Example: Amifostine.

#### Alternative Methods for Measuring Cell Survival
While clonogenic assay is the gold standard, other methods provide complementary information or are faster/easier:

*   **Growth Assays (Measure Proliferation):**
    *   *Cell Counting/Growth Curves:* Simpler, track population growth over time. Good for relative comparisons but don't directly measure reproductive death.
    *   *Spheroid Growth Delay:* Uses 3D cell clusters (spheroids) that better mimic tumor structure. Measures time delay for spheroid to regrow after radiation. More complex but potentially more relevant.
*   **Metabolic/Viability Assays (Measure Cell Health):**
    *   *MTT/MTS/XTT:* Color change indicates metabolic activity (mitochondrial function). Fast, high-throughput, good for drug screening, but poor correlation with clonogenic survival after radiation.
    *   *ATP Assays:* Measure cellular energy levels (luminescence). Sensitive to viable cell number, faster than clonogenics, but again, doesn't measure reproductive death.
    *   *Flow Cytometry (Annexin V/PI):* Can quickly quantify apoptosis and necrosis in a population but misses other death modes like mitotic catastrophe or senescence contributing to loss of clonogenicity.
*   **Molecular/Functional Assays (Measure Damage/Response):**
    *   *γH2AX Foci Staining:* Visualizes DNA double-strand breaks (DSBs) via immunofluorescence. Measures initial damage and repair kinetics. Correlates with sensitivity but is an upstream event, not the final outcome.
    *   *Comet Assay:* Measures DNA strand breaks in individual cells via electrophoresis. Sensitive but technically demanding.
    *   *Micronucleus Assay:* Counts small nuclear fragments containing broken chromosome pieces after cell division. Reflects chromosomal instability and correlates reasonably well with clonogenic death.

*   **Why Clonogenic Still Matters:** Only the clonogenic assay directly measures the loss of indefinite proliferative potential, which is the ultimate goal of curative radiotherapy.

#### High-Throughput Survival Assessment
To screen many conditions (drugs, genes) quickly, faster or automated methods are used:

*   **Automated Clonogenics:** Robots handle plating, imaging systems count colonies using software. Increases throughput and consistency.
*   **Surrogate Assays:** Using faster assays (like automated microscopy measuring confluence/growth rate over several days, or high-content imaging analyzing cell morphology and markers) that show good correlation with clonogenic survival for specific contexts.
*   **Applications:** Essential for large-scale genetic screens (CRISPR, shRNA) to find genes affecting radiosensitivity, testing drug-radiation combinations, and developing personalized medicine approaches using patient-derived cells/organoids.

#### From In Vitro Survival to In Vivo Response
Bridging the gap between lab dish results and patient outcomes is complex:

*   **In Vivo Complexity:** Real tumors exist in a complex 3D microenvironment with hypoxia, nutrient gradients, immune cells, stromal interactions – all absent in standard 2D culture.
*   **Tumor Control Probability (TCP):** Mathematical models (often Poisson-based) relate the surviving fraction of clonogenic tumor cells after treatment to the probability of controlling the tumor. $$ TCP = e^{-N \times SF_{total}} $$ where $N$ is the initial number of clonogens and $SF_{total}$ is the overall surviving fraction after the full treatment course.
*   **Normal Tissue Complication Probability (NTCP):** Similar models relate the survival of critical cells in normal tissues to the probability of developing side effects.
*   **Therapeutic Ratio:** The goal is to maximize TCP while minimizing NTCP. Understanding the different survival curves (especially $\alpha/\beta$ ratios) for tumors vs. normal tissues helps optimize treatment fractionation and dose.
*   **Limitations:** In vitro $SF_2$ or $\alpha/\beta$ values are useful guides but don't perfectly predict clinical response due to the vast complexity of the in vivo situation (heterogeneity, microenvironment, immune response etc.). Patient-derived models (organoids, xenografts) aim to bridge this gap.

*   **Clinical Scenario:**
    *   *Problem:* A patient has a tumor type known to be hypoxic. Standard radiation might fail.
    *   *Radiobiology Insight:* Hypoxic cells have a shallower survival curve ($OER \approx 3$). To achieve the same level of killing as in oxygenated cells, roughly 3 times the dose is needed, which is often impossible without exceeding normal tissue tolerance.
    *   *Potential Solutions (based on survival curve concepts):*
        1.  *Fractionation:* Allow reoxygenation between fractions.
        2.  *Hypoxic Cell Radiosensitizers:* Drugs that specifically sensitize hypoxic cells (e.g., nimorazole).
        3.  *High-LET Radiation:* Carbon ions have a much lower OER ($\approx 1.1-1.6$), making them more effective against hypoxic cells.
        4.  *Dose Escalation:* If possible, increase the dose specifically to hypoxic regions identified on imaging (dose painting).


