# Section 6.9: Shielding Design for Diagnostic, Nuclear Medicine and Therapeutic Installations

**Approximate Lecture Time:** 1.5 - 2.0 Hours

**Learning Objectives:**

Upon completion of this section, the student will be able to:

1.  **Explain** the fundamental principles of radiation shielding, including attenuation, Half-Value Layer (HVL), and Tenth-Value Layer (TVL).
2.  **Identify** common shielding materials and their relative effectiveness for photons and neutrons.
3.  **Define** the key parameters used in shielding calculations: Workload (W), Use Factor (U), and Occupancy Factor (T).
4.  **Distinguish** between primary and secondary radiation barriers and the types of radiation they are designed to attenuate (primary beam, leakage, scatter).
5.  **Describe** the general methodology for calculating required barrier thicknesses using NCRP report recommendations (e.g., NCRP 147, NCRP 151).
6.  **Discuss** specific shielding considerations for diagnostic X-ray rooms, CT scanners, nuclear medicine facilities (hot labs, uptake rooms, imaging rooms), and therapeutic installations (linac vaults, HDR brachytherapy rooms).
7.  **Explain** the need for and basic principles of neutron shielding for high-energy (>10 MV) linear accelerators.

**Key Points:**

*   **Goal:** Reduce radiation exposure to personnel and the public outside the shielded enclosure to below regulatory limits (e.g., 100 mrem/year or 2 mrem in any one hour for unrestricted areas).
*   **Principles:** Shielding relies on the attenuation of radiation as it passes through matter. HVL is the thickness required to reduce intensity by 50%; TVL reduces intensity by 90% (1 TVL ≈ 3.32 HVL).
*   **Materials:** Common materials include lead (high Z, effective for photons), concrete (cost-effective, good for photons and neutrons), steel, and specialized materials like borated polyethylene (for neutrons).
*   **WUT Factors:**
    *   *Workload (W):* Measure of the radiation output or usage per week (e.g., mA-min/wk for X-ray, Gy/wk at 1m for linacs, activity administered/wk for NM).
    *   *Use Factor (U):* Fraction of the time the primary beam is directed towards a specific barrier (U=1 for floors/ceilings/walls potentially hit by primary beam; U=1/4 often used for walls in therapy if beam orientation varies).
    *   *Occupancy Factor (T):* Fraction of time an area adjacent to the barrier is occupied by the individual maximally exposed (T=1 for offices, control consoles; T=1/5 for corridors; T=1/20 for restrooms; T=1/40 for outdoor areas).
*   **Barrier Types:**
    *   *Primary Barrier:* Attenuates the primary radiation beam.
    *   *Secondary Barrier:* Attenuates leakage radiation from the source housing and scattered radiation from the patient/phantom/walls.
*   **Calculation Methodology (NCRP):** Involves determining the required transmission factor (B) for each barrier to reduce the dose rate to the design goal (P), considering W, U, T, distance (d), and source output/leakage. The number of TVLs required is calculated, and the thickness is determined from attenuation data for the chosen material.
    *   Primary Barrier Transmission: $B_{pri} = \frac{P d_{pri}^2}{W U T}$
    *   Secondary Barrier Transmission (Scatter): $B_{sca} = \frac{P d_{sca}^2 d_{sec}^2}{a W T \alpha F}$
    *   Secondary Barrier Transmission (Leakage): $B_{L} = \frac{P d_{L}^2}{1000 W_{L} T}$ (for therapy leakage, often uses W instead of W_L and assumes 0.1% leakage limit)
*   **Modality Specifics:** Diagnostic X-ray focuses on scatter and leakage (NCRP 147); CT requires accounting for scatter from 360 degrees; NM involves shielding for gamma rays from patients and stored sources (NCRP 151); Therapy requires thick barriers for primary, scatter, and leakage, plus neutron shielding for >10 MV linacs (NCRP 151).
*   **Neutron Shielding:** High-energy photons (>~8-10 MeV) produce neutrons via photodisintegration in high-Z materials (target, flattening filter, collimators, patient). Requires hydrogenous materials (e.g., concrete, polyethylene) often combined with boron (for thermal neutron capture) in door design and mazes.

---

## 1. Fundamental Principles of Shielding

Radiation shielding aims to reduce the intensity of ionizing radiation to acceptable levels by placing absorbing materials between the source and the occupied area.

*   **Attenuation:** As radiation passes through matter, its intensity decreases due to absorption and scattering interactions. For monoenergetic photons under narrow-beam conditions, this follows an exponential relationship:
    $I(x) = I_0 e^{-\mu x}$
    where $I_0$ is the initial intensity, $I(x)$ is the intensity after passing through thickness $x$, and $\mu$ is the linear attenuation coefficient.
*   **Half-Value Layer (HVL):** The thickness of a specified material required to reduce the radiation intensity to 50% of its initial value.
    $HVL = \frac{ln(2)}{\mu} \approx \frac{0.693}{\mu}$
*   **Tenth-Value Layer (TVL):** The thickness of a specified material required to reduce the radiation intensity to 10% of its initial value.
    $TVL = \frac{ln(10)}{\mu} \approx \frac{2.303}{\mu}$
    Relationship: $1 TVL = \frac{ln(10)}{ln(2)} HVL \approx 3.32 HVL$
*   **Broad Beam Conditions:** In practice, scattered radiation within the barrier adds to the transmitted intensity. Shielding calculations use broad-beam attenuation data or TVLs, which are generally larger than narrow-beam values.
*   **Shielding Materials:** Choice depends on radiation type, energy, cost, and structural requirements.
    *   *Lead (Pb):* High density and atomic number, very effective for photons (especially lower energy diagnostic X-rays and gamma rays) via photoelectric effect and Compton scatter. Expensive, structurally weak.
    *   *Concrete:* Lower density than lead but cost-effective and structurally sound. Good for high-energy photons (Compton scatter dominates) and neutrons (hydrogen content moderates fast neutrons, aggregates absorb thermal neutrons).
    *   *Steel:* Often used structurally (e.g., plates in doors, beam stops).
    *   *Borated Polyethylene:* Polyethylene (rich in hydrogen) is excellent for moderating fast neutrons; added boron (Boron-10) has a high cross-section for capturing thermal neutrons, releasing a low-energy alpha particle.

## 2. Shielding Design Parameters (W, U, T)

NCRP methodology relies on quantifying the source usage and occupancy of surrounding areas.

*   **Workload (W):** Represents the total radiation output or usage per unit time (typically per week). Units vary by modality:
    *   *Diagnostic X-ray:* mA-min/week.
    *   *CT:* mGy-cm/week or procedure-based.
    *   *Nuclear Medicine:* Activity administered per week (MBq/wk or mCi/wk) or activity stored.
    *   *Therapy (Linac):* Dose delivered at 1 meter per week (Gy/wk). Calculated from typical patients/day, fractions/patient, dose/fraction.
*   **Use Factor (U):** Fraction of the operating time during which the radiation under consideration is directed towards a particular barrier. Applies primarily to the primary beam in therapy and sometimes diagnostic radiography.
    *   *Primary Beam:* U=1 for barriers that can be directly irradiated. U=1/4 often used for therapy room walls if beam orientation varies significantly. U=0 if a barrier cannot be struck by the primary beam.
    *   *Leakage & Scatter:* U=1 is always used, as leakage and scatter are omnidirectional.
*   **Occupancy Factor (T):** Fraction of the time that the area to be protected is occupied by the individual who spends the most time there. Based on realistic estimates of occupancy.
    *   *Full Occupancy (T=1):* Offices, control rooms, labs, nurses stations, living quarters, children's play areas.
    *   *Partial Occupancy (T=1/5 or 0.2):* Corridors, patient rooms, staff lounges.
    *   *Occasional Occupancy (T=1/20 or 0.05):* Public restrooms, waiting rooms, unattended parking lots.
    *   *Infrequent Occupancy (T=1/40 or 0.025):* Stairways, unattended storage rooms, outdoor areas with transient traffic.
*   **Design Goal (P):** The maximum permissible dose rate or weekly dose equivalent allowed in the occupied area. Based on regulatory limits for controlled vs. uncontrolled areas.
    *   *Uncontrolled Areas:* Typically designed to ≤ 0.02 mSv/week (1 mSv/year or 100 mrem/year), assuming T=1.
    *   *Controlled Areas:* Typically designed to ≤ 0.1 mSv/week (5 mSv/year or 500 mrem/year), assuming T=1.
*   **Distance (d):** Distance from the radiation source to the point being protected (meters).

## 3. Barrier Calculations (NCRP Methodology)

The goal is to find the barrier thickness that reduces the dose rate at the point of interest to below the design goal P.

**General Steps:**

1.  Determine the unshielded dose rate (or weekly dose) at the point of interest.
2.  Calculate the required attenuation or transmission factor (B) needed to reduce the unshielded dose to the design goal P.
3.  Determine the number of TVLs required: $n_{TVL} = -log_{10}(B)$.
4.  Calculate the barrier thickness: $Thickness = TVL_1 + (n_{TVL} - 1) \times TVL_e$, where $TVL_1$ is the first TVL and $TVL_e$ are subsequent TVLs (accounting for beam hardening).

**Specific Calculations:**

*   **Primary Barrier (Therapy):** Attenuates the primary beam.
    $B_{pri} = \frac{P d_{pri}^2}{W U T}$
    where $d_{pri}$ is the distance from the isocenter to the point beyond the barrier.
*   **Secondary Barrier - Scatter:** Attenuates radiation scattered from the patient/phantom.
    $B_{sca} = \frac{P d_{sca}^2 d_{sec}^2}{a W T \alpha F}$
    where $d_{sca}$ is distance from isocenter to patient, $d_{sec}$ is distance from patient to point beyond barrier, $a$ is the scatter fraction (energy and angle dependent, often from NCRP tables), $\alpha$ is the floor reflection factor (if applicable), and $F$ is the field area at the patient (cm²).
*   **Secondary Barrier - Leakage:** Attenuates leakage radiation from the accelerator head.
    $B_{L} = \frac{P d_{L}^2}{1000 W_{L} T}$ (General form)
    For therapy linacs, leakage is typically limited to 0.1% of the primary beam dose rate outside the useful beam at 1m. The calculation often simplifies using the primary workload W, assuming maximum leakage:
    $B_{L} \approx \frac{P d_{L}^2}{0.001 W T}$ (assuming $d_L$ is distance from isocenter)
*   **Required Thickness:** The larger of the scatter or leakage barrier thicknesses determines the required secondary barrier thickness. Often, leakage dominates for therapy vaults.

## 4. Modality-Specific Considerations

*   **Diagnostic X-ray (NCRP 147):**
    *   Workload often in mA-min/week.
    *   Lower energies mean lead is very effective.
    *   Scatter from patient is the dominant source for secondary barriers.
    *   Leakage limits are typically 1 mGy/hr (100 mR/hr) at 1m.
*   **Computed Tomography (CT) (NCRP 147):**
    *   Scatter originates from 360 degrees around the patient.
    *   Workload often based on mGy-cm or scan protocols.
    *   Calculations often use dose-length product (DLP) or CTDI (CT Dose Index).
*   **Nuclear Medicine (NCRP 151, NCRP 208):**
    *   Sources are unsealed (patients, stored vials).
    *   Shielding needed for hot labs, uptake rooms, imaging rooms, patient waiting areas, patient toilets.
    *   Calculations based on maximum activity handled/stored or administered, considering decay.
    *   Lead shielding (bricks, L-blocks, vial shields, syringe shields) is common.
    *   Consideration for airborne activity (fume hoods) and waste storage.
*   **Therapeutic Installations (NCRP 151):**
    *   *Linac Vaults:* Require substantial concrete barriers (often several feet thick) for primary, scatter, and leakage radiation from high-energy MV photon beams.
        *   *Maze Entrance:* Designed to reduce scattered radiation reaching the door. Multiple legs are more effective. Neutron dose at the door is often the limiting factor for high-energy linacs.
        *   *Door:* Must provide equivalent shielding to the maze, often very thick and heavy, incorporating lead and polyethylene/boron for neutron attenuation.
        *   *Ducts/Penetrations:* Require careful design to prevent radiation streaming.
    *   *HDR Brachytherapy Rooms:* Shielding against gamma rays (e.g., Ir-192). Less massive than linac vaults but still require significant shielding, often lead or concrete. Source transit dose and emergency scenarios must be considered.

## 5. Neutron Shielding (>10 MV Linacs)

High-energy photons interact with high-Z materials (target, flattening filter, jaws, MLCs, patient) via giant dipole resonance, producing neutrons (photoneutron production). Threshold is ~8-10 MeV, increasing significantly above 15 MeV.

*   **Neutron Sources:** Primary target area is the main source.
*   **Neutron Energy:** Spectrum includes fast neutrons (average energy ~1-2 MeV) and thermal neutrons (after moderation).
*   **Shielding Process:**
    1.  *Moderation:* Fast neutrons are slowed down (thermalized) by elastic scattering, primarily with hydrogen nuclei. Hydrogenous materials like concrete and polyethylene are effective moderators.
    2.  *Absorption:* Thermal neutrons are absorbed, often via neutron capture reactions. Boron-10 (in borated polyethylene or borated concrete) is highly effective due to its large (n, α) cross-section. Cadmium is also used but produces prompt capture gamma rays.
*   **Design Considerations:**
    *   *Maze/Door:* Neutron dose often dictates the design of the maze entrance and door thickness/composition.
    *   *Concrete Walls:* Standard concrete provides both photon and neutron shielding.
    *   *Capture Gammas:* Neutron capture reactions (especially in hydrogen and concrete elements) can produce high-energy gamma rays, which must be considered in the overall shielding design.

---

**Assessment Questions (ABR Style):**

1.  For a linear accelerator vault shielding calculation, the Use Factor (U) for leakage radiation is always considered to be:
    (A) 0
    (B) 0.1
    (C) 0.25
    (D) 0.5
    (E) 1

2.  Which of the following materials is most effective for shielding thermal neutrons?
    (A) Lead
    (B) Steel
    (C) Concrete
    (D) Polyethylene
    (E) Boron

3.  According to NCRP recommendations, an office area immediately adjacent to a diagnostic X-ray room wall should typically be assigned an Occupancy Factor (T) of:
    (A) 1/40
    (B) 1/20
    (C) 1/5
    (D) 1/2
    (E) 1

4.  A barrier designed to attenuate only leakage and scattered radiation is known as a:
    (A) Primary Barrier
    (B) Secondary Barrier
    (C) Tertiary Barrier
    (D) Neutron Barrier
    (E) Controlled Area Barrier

5.  The thickness of a shielding material required to reduce the radiation intensity by 90% is known as the:
    (A) Half-Value Layer (HVL)
    (B) Tenth-Value Layer (TVL)
    (C) Linear Attenuation Coefficient (µ)
    (D) Mean Free Path
    (E) Transmission Factor (B)

**Answers:**
1.  (E) Leakage radiation is assumed to be present in all directions whenever the beam is on, so U=1.
2.  (E) Boron (specifically Boron-10) has a very high cross-section for thermal neutron capture. Polyethylene is good for moderating fast neutrons, and concrete provides some moderation and absorption.
3.  (E) Offices and other areas of full occupancy are assigned T=1.
4.  (B) Secondary barriers protect against leakage and scatter radiation.
5.  (B) TVL is the thickness required for a 90% reduction (attenuation to 10%).

---

**References:**

*   NCRP Report No. 147, *Structural Shielding Design for Medical X-Ray Imaging Facilities* (2004).
*   NCRP Report No. 151, *Structural Shielding Design and Evaluation for Megavoltage X- and Gamma-Ray Radiotherapy Facilities* (2005).
*   NCRP Report No. 208, *Radiation Protection Considerations for Nuclear Medicine Patients Released from Treatment* (2022) - relevant for NM facility design.
*   McGinley, P. H. *Shielding Techniques for Radiation Oncology Faciliti
(Content truncated due to size limit. Use line ranges to read in chunks)