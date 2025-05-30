# Section 5.9: Brachytherapy

**Approximate Lecture Time:** 3-4 Hours

**Learning Objectives:**

Upon completion of this section, the student will be able to:

1.  **Define** brachytherapy and **distinguish** it from external beam radiotherapy.
2.  **Identify** common radionuclides used in brachytherapy (e.g., Ir-192, I-125, Pd-103, Cs-137, Co-60) and **describe** their key physical characteristics (half-life, energy spectrum, specific activity).
3.  **Define** and **explain** the significance of source specification quantities: Activity, Air Kerma Strength (S<sub>K</sub>), Apparent Activity.
4.  **Describe** different types of brachytherapy sources (seeds, wires, ribbons, pellets, electronic sources) and their construction.
5.  **Classify** brachytherapy techniques based on:
    *   Source placement (interstitial, intracavitary, intraluminal, surface/mold).
    *   Dose rate (Low Dose Rate - LDR, Medium Dose Rate - MDR, High Dose Rate - HDR, Pulsed Dose Rate - PDR).
    *   Duration (temporary vs. permanent implants).
6.  **Describe** common applicators used in intracavitary brachytherapy (e.g., tandem and ovoids/ring for GYN, vaginal cylinders).
7.  **Explain** the principles of interstitial implantation techniques (e.g., template-guided, freehand).
8.  **Outline** the key components and recommendations of the AAPM Task Group 43 (TG-43) formalism for brachytherapy dose calculation.
9.  **Define and explain** the parameters within the TG-43 formalism: Air Kerma Strength (S<sub>K</sub>), Dose Rate Constant (Λ), Geometry Function (G(r,θ)), Radial Dose Function (g(r)), Anisotropy Function (F(r,θ)).
10. **Perform** basic point dose calculations using the TG-43 formalism.
11. **Compare and contrast** LDR and HDR brachytherapy in terms of treatment delivery, dose distributions, radiobiology, staffing, and radiation safety.
12. **Describe** the principles of HDR remote afterloading systems.
13. **Outline** the general workflow for brachytherapy treatment planning, including imaging, applicator/source localization, dose specification, optimization (for HDR), and plan evaluation.
14. **Discuss** key radiation safety considerations specific to brachytherapy, including source handling, storage, inventory, emergency procedures, and patient/staff protection for LDR and HDR.

**Key Points:**

*   **Brachytherapy:** Radiation therapy technique where sealed radioactive sources are placed directly into or near the target volume.
*   **Advantages:** Highly conformal dose distributions, rapid dose fall-off sparing surrounding normal tissues.
*   **Source Specification:** Air Kerma Strength (S<sub>K</sub>) is the standard quantity (unit: U = µGy m²/h = cGy cm²/h). `S_K = K_dot(d) * d²`, where K_dot(d) is air kerma rate at distance *d*.
*   **Common Sources:**
    *   **Ir-192:** HDR/PDR/LDR, T<sub>1/2</sub>=73.8 days, Avg E ≈ 380 keV.
    *   **I-125:** LDR (permanent seeds), T<sub>1/2</sub>=59.4 days, Avg E ≈ 28 keV.
    *   **Pd-103:** LDR (permanent seeds), T<sub>1/2</sub>=17.0 days, Avg E ≈ 21 keV.
    *   **Cs-137:** LDR (historical, being phased out), T<sub>1/2</sub>=30.0 years, E = 662 keV.
*   **TG-43 Formalism (Updated):** Standard method for calculating dose around brachytherapy sources.
    *   `D_dot(r, θ) = S_K * Λ * [G_L(r, θ) / G_L(r_0, θ_0)] * g_L(r) * F(r, θ)` (Line source model)
    *   `D_dot(r, θ) = S_K * Λ * [G_P(r, θ) / G_P(r_0, θ_0)] * g_P(r) * F(r, θ)` (Point source model)
    *   Λ: Dose rate constant (cGy h⁻¹ U⁻¹).
    *   G(r,θ): Geometry function (accounts for inverse square).
    *   g(r): Radial dose function (accounts for scatter/attenuation along transverse axis).
    *   F(r,θ): Anisotropy function (accounts for dose variation with angle due to self-absorption/filtration).
*   **LDR vs HDR:**
    *   **LDR:** 0.4-2 Gy/h. Continuous irradiation over days. Requires hospitalization, significant radiation safety procedures for staff/visitors.
    *   **HDR:** > 12 Gy/h. Delivered in minutes via remote afterloader. Outpatient procedure, improved radiation safety for staff (source shielded when not treating).
*   **Remote Afterloaders:** Devices that automatically deliver HDR sources to planned positions within applicators via transfer tubes.
*   **Treatment Planning:** Involves imaging (CT/MR/US), digitizing applicator/source positions, defining target/OARs, calculating dose distribution, and optimizing dwell times/positions (HDR).
*   **Safety:** Critical aspects include source security, inventory, handling procedures (ALARA), emergency protocols, patient release criteria (LDR), and afterloader QA (HDR).

---

## 1. Introduction to Brachytherapy

Brachytherapy, derived from the Greek words *brachys* (short distance) and *therapy*, is a form of radiotherapy where sealed radioactive sources are placed directly inside or very close to the tumor volume. This proximity allows for the delivery of a high, conformal dose to the target while minimizing the dose to surrounding healthy tissues due to the rapid dose fall-off governed primarily by the inverse square law.

**Contrast with External Beam Radiotherapy (EBRT):**
*   **EBRT:** Radiation source is outside the body (e.g., linac), beam travels through normal tissue to reach the tumor.
*   **Brachytherapy:** Source is inside or adjacent to the tumor.

**Advantages of Brachytherapy:**
*   Highly conformal dose distributions.
*   Rapid dose fall-off spares adjacent organs at risk (OARs).
*   Can deliver very high doses locally.
*   Less sensitive to organ motion compared to EBRT in some cases.

**Disadvantages:**
*   Invasive procedure.
*   Potential for dose inhomogeneity within the target.
*   Requires specialized expertise and equipment.
*   Significant radiation safety considerations, especially with LDR.

## 2. Brachytherapy Sources and Characteristics

### 2.1. Common Radionuclides

Several radionuclides are used, chosen based on their half-life, energy spectrum, specific activity, and desired dose rate.

| Radionuclide | Symbol | Half-Life (T<sub>1/2</sub>) | Average Energy (approx.) | Typical Use      | Form        |
| :----------- | :----- | :----------------------- | :----------------------- | :--------------- | :---------- |
| Iridium-192  | ¹⁹²Ir  | 73.8 days                | 380 keV                  | HDR, PDR, LDR    | Wire, Seed  |
| Iodine-125   | ¹²⁵I   | 59.4 days                | 28 keV                   | LDR (Permanent)  | Seed        |
| Palladium-103| ¹⁰³Pd  | 17.0 days                | 21 keV                   | LDR (Permanent)  | Seed        |
| Cesium-137   | ¹³⁷Cs  | 30.0 years               | 662 keV                  | LDR (Historical) | Tube, Needle|
| Cobalt-60    | ⁶⁰Co   | 5.27 years               | 1.25 MeV                 | HDR (Historical) | Pellet      |
| Strontium-90 | ⁹⁰Sr   | 28.8 years               | 546 keV (β⁻)             | Surface (Ophthalmic) | Applicator |
| Ytterbium-169| ¹⁶⁹Yb  | 32.0 days                | 93 keV                   | HDR (Investigational)| Seed        |

*   **Low Energy Sources (¹²⁵I, ¹⁰³Pd):** Primarily used for permanent LDR seed implants (e.g., prostate). Their low energy requires less shielding but makes dose calculation more sensitive to tissue composition and source geometry.
*   **High Energy Sources (¹⁹²Ir, ¹³⁷Cs, ⁶⁰Co):** Used for temporary implants (LDR/HDR). Higher energy provides greater penetration but requires more shielding.
*   **Electronic Brachytherapy (eBx):** Uses miniature, low-energy X-ray tubes placed near the target. Not a radionuclide source, but delivers dose similarly. Used for surface or intracavitary treatments (e.g., skin, breast).

### 2.2. Source Construction

Sources are typically sealed capsules containing the radioactive material.
*   **Seeds:** Small (e.g., 4.5 mm long, 0.8 mm diameter) cylindrical capsules, often made of titanium, containing the radionuclide adsorbed onto a matrix (e.g., silver rod for ¹²⁵I) or as a solid core.
*   **Wires/Ribbons:** Flexible wires (e.g., ¹⁹²Ir) or seeds embedded in absorbable ribbons.
*   **Needles/Tubes:** Rigid tubes containing radioactive material (e.g., historical ¹³⁷Cs needles).
*   **HDR Sources:** Typically a single, small, high-activity source (e.g., ¹⁹²Ir pellet) attached to a wire that is driven by the afterloader.

### 2.3. Source Specification

Quantifying the 

strength" of a brachytherapy source is crucial for dose calculation.

*   **Activity (A):** Historical unit (Curie - Ci) or SI unit (Becquerel - Bq). Represents the rate of radioactive decay (`A = λN`). Not ideal for dose calculation as it doesn't account for photon energy or emission probability.
*   **Apparent Activity (A<sub>app</sub>):** Activity of a bare point source of the same radionuclide that would produce the same exposure rate/air kerma rate in air at a reference distance as the actual encapsulated source. Attempts to account for self-absorption and filtration.
*   **Air Kerma Strength (S<sub>K</sub>):** The **recommended** quantity (AAPM TG-32, TG-43). Defined as the product of the air kerma rate (`K̇_air(d)`) in free space and the square of the distance (*d*) from the source center along the transverse axis (`S_K = K̇_air(d) * d²`).
    *   Unit: **U = µGy m² h⁻¹ = cGy cm² h⁻¹**.
    *   Independent of distance (*d*) beyond where charge particle equilibrium is established.
    *   Directly relates to the dose rate in the medium via the dose rate constant (Λ).
    *   Traceable to national standards laboratories (e.g., NIST).

## 3. Classification of Brachytherapy Techniques

Brachytherapy can be classified in several ways:

### 3.1. By Source Placement

*   **Interstitial:** Sources are placed directly into the target tissue (e.g., prostate seeds, breast implants).
*   **Intracavitary:** Sources are placed within a body cavity close to the tumor (e.g., GYN treatments using tandem and ovoids/ring, vaginal cylinder).
*   **Intraluminal:** Sources are placed within a body lumen (e.g., esophagus, bronchus, bile duct).
*   **Surface (Mold/Plaque):** Sources are placed in a mold or applicator that sits on the skin surface or ocular surface (e.g., skin cancer, ophthalmic treatments).

### 3.2. By Dose Rate

Based on the dose rate delivered at a reference point or distance:

*   **Low Dose Rate (LDR):** 0.4 - 2 Gy/hour. Treatment delivered continuously over hours or days.
*   **Medium Dose Rate (MDR):** 2 - 12 Gy/hour. Less common, sometimes used as an alternative to LDR.
*   **High Dose Rate (HDR):** > 12 Gy/hour. Treatment delivered in multiple fractions over minutes using a remote afterloader.
*   **Pulsed Dose Rate (PDR):** Delivers dose in short pulses (e.g., hourly) over a period similar to LDR, aiming to mimic LDR radiobiology while using an HDR source/afterloader.

### 3.3. By Duration

*   **Temporary:** Sources are removed after the prescribed dose is delivered (common for LDR intracavitary/interstitial, all HDR/PDR).
*   **Permanent:** Sources (typically LDR seeds like ¹²⁵I or ¹⁰³Pd) are left in place permanently, delivering dose as they decay (e.g., prostate seed implants).

## 4. Applicators and Implantation Techniques

*   **Intracavitary Applicators:** Devices designed to hold sources in specific geometries within body cavities.
    *   **Gynecological (GYN):** Tandem (intrauterine tube) and Ovoids/Ring (vaginal fornices) applicators are common for cervical cancer. Vaginal cylinders are used for endometrial or vaginal cuff treatments.
*   **Interstitial Implantation:**
    *   **Needles/Catheters:** Hollow needles or flexible catheters are inserted into the target tissue, through which sources (seeds, wires, HDR source) are loaded.
    *   **Template-Guided:** A template grid is used to guide needle placement for precise geometry (e.g., prostate, GYN interstitial).
    *   **Freehand:** Needles/catheters placed without a template, often under image guidance (US, CT, fluoro).
*   **Surface Molds/Applicators:** Custom or standard devices to hold sources at a fixed distance from the skin or eye.

## 5. Dose Calculation: The TG-43 Formalism

The AAPM Task Group 43 (TG-43) report and its updates (TG-43U1) provide the standard clinical formalism for calculating dose around cylindrically symmetric brachytherapy sources.

**Assumptions:** Assumes dose is calculated in an infinite, homogeneous water medium.

**Coordinate System:** Polar coordinates (r, θ) relative to the source center, where *r* is the distance and *θ* is the angle relative to the source long axis.

**General Formula (2D):**

`Ḋ(r, θ) = S_K * Λ * [G(r, θ) / G(r₀, θ₀)] * g(r) * F(r, θ)`

Where:
*   `Ḋ(r, θ)`: Dose rate at point (r, θ) (cGy/h).
*   `S_K`: Air Kerma Strength of the source (U = cGy cm²/h).
*   `Λ`: Dose Rate Constant. Dose rate to water at the reference point (r₀=1 cm, θ₀=90°) per unit S<sub>K</sub>. (Unit: cGy h⁻¹ U⁻¹).
*   `G(r, θ)`: Geometry Function. Accounts for the spatial distribution of radioactivity within the source (inverse square law modified for source geometry). For a point source: `G_P(r, θ) = 1/r²`. For a line source of length L: `G_L(r, θ) = β / (L * r * sinθ)` where β is the angle subtended by the line source at point (r, θ).
*   `G(r₀, θ₀)`: Geometry function at the reference point (r₀=1 cm, θ₀=90°).
*   `g(r)`: Radial Dose Function. Accounts for dose fall-off along the transverse axis (θ=90°) due to absorption and scatter in the medium, relative to the reference distance r₀. `g(r₀) = 1`.
*   `F(r, θ)`: Anisotropy Function. Accounts for the variation of dose with angle (θ) relative to the transverse axis, due to self-absorption in the source/capsule and scatter. `F(r, θ₀) = 1`.

**Consensus Data Sets:** TG-43 recommends using consensus data sets published for specific source models for Λ, g(r), and F(r,θ).

**Point Dose Calculation Example:**
Calculate the dose rate at r=3 cm, θ=90° from an ¹⁹²Ir HDR source with S<sub>K</sub> = 40,000 U. Use consensus data: Λ = 1.115 cGy h⁻¹ U⁻¹, g(3 cm) = 0.950. Assume point source geometry for simplicity (G(r,θ)=1/r², G(1,90°)=1/1²=1) and F(3, 90°)=1.

`Ḋ(3, 90°) = 40000 U * 1.115 cGy h⁻¹ U⁻¹ * [ (1/3²) / (1/1²) ] * 0.950 * 1`
`Ḋ(3, 90°) = 40000 * 1.115 * (1/9) * 0.950`
`Ḋ(3, 90°) ≈ 4696 cGy/h`

**Limitations:** The formalism assumes a water medium. Corrections may be needed for tissue inhomogeneities, air cavities, or high-Z materials (applicators, shielding), often requiring model-based dose calculation engines (MBDCAs) beyond TG-43.

## 6. LDR vs. HDR Brachytherapy

| Feature          | LDR (Low Dose Rate)                     | HDR (High Dose Rate)                       |
| :--------------- | :-------------------------------------- | :----------------------------------------- |
| **Dose Rate**    | 0.4 - 2 Gy/h                            | > 12 Gy/h                                  |
| **Source**       | ¹²⁵I, ¹⁰³Pd (permanent); ¹⁹²Ir, ¹³⁷Cs (temporary) | ¹⁹²Ir (most common), ⁶⁰Co (historical)   |
| **Delivery**     | Continuous over days (temp) or lifetime (perm) | Minutes per fraction, multiple fractions | 
| **Setting**      | Hospitalization (temp), Outpatient (perm) | Outpatient                                 |
| **Afterloader**  | Manual loading (historical) or remote   | Remote Afterloader required                |
| **Optimization** | Source placement critical               | Dwell time optimization possible           |
| **Radiobiology** | Continuous low rate repair effects      | Similar to EBRT fractions                  |
| **Staff Safety** | Significant exposure potential          | Minimal exposure (source retracted)        |
| **Patient Safety**| Source displacement/loss risk (perm)    | Afterloader malfunction risk               |
| **Cost**         | Lower equipment cost, higher inpatient cost | Higher equipment cost, lower per-procedure cost |

## 7. HDR Remote Afterloading Systems

HDR brachytherapy relies on remote afterloading devices.
*   **Components:** Shielded safe containing the source, drive mechanism/wire, transfer tubes, treatment console.
*   **Opera
(Content truncated due to size limit. Use line ranges to read in chunks)