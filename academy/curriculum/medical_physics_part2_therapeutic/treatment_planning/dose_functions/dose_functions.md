# Section 5.6: Dose Functions: PDD, TAR, TPR, TMR, SMR

**Approximate Lecture Time:** 2.5-3 Hours

**Learning Objectives:**

Upon completion of this section, the student will be able to:

1.  **Define** Percent Depth Dose (PDD) and **explain** its dependence on energy, depth, field size, and Source-Surface Distance (SSD).
2.  **Define** Tissue-Air Ratio (TAR) and **explain** its dependence on energy, depth, and field size, noting its independence from SSD.
3.  **Define** Tissue-Phantom Ratio (TPR) and Tissue-Maximum Ratio (TMR) and **explain** their dependence on energy, depth, and field size, noting their independence from SSD.
4.  **Distinguish** between TPR and TMR based on the reference depth used.
5.  **Define** Scatter-Air Ratio (SAR) and Scatter-Maximum Ratio (SMR) and **explain** their use in calculating dose contributions from scattered radiation.
6.  **Derive and explain** the mathematical relationships between PDD, TAR, TMR, and TPR.
7.  **Apply** these dose functions to perform basic dose calculations for both SSD (Source-Surface Distance) and SAD (Source-Axis Distance) treatment setups.
8.  **Explain** the concept of equivalent squares and how it is used to handle non-square fields when using tabulated dose function data.

**Key Points:**

*   **PDD (Percent Depth Dose):** `[Dose(d) / Dose(d_max)] * 100%` for a fixed SSD. Depends strongly on SSD due to inverse square law. Primarily used for SSD setups.
*   **TAR (Tissue-Air Ratio):** `Dose(d) in phantom / Dose(d) in air (at same point, with buildup cap)`. Independent of SSD. Historically important, less used now for MV beams due to difficulty measuring dose in air.
*   **TPR (Tissue-Phantom Ratio):** `Dose(d) in phantom / Dose(d_ref) in phantom (at same point)`. Independent of SSD. Reference depth (d_ref) is fixed but arbitrary (often 5 or 10 cm).
*   **TMR (Tissue-Maximum Ratio):** `Dose(d) in phantom / Dose(d_max) in phantom (at same point)`. Special case of TPR where d_ref = d_max. Independent of SSD. Most commonly used function for SAD calculations with MV beams.
*   **Relationships:** PDD can be converted to TMR/TPR (and vice versa) using inverse square factors to account for SSD dependence. `TMR(d, FS) = PDD(d, FS, SSD) / 100 * [(SSD+d)/(SSD+d_max)]² * SF(FS)`. (SF is phantom scatter factor, sometimes implicitly included).
*   **SAR/SMR:** Represent the ratio of scattered dose at a point to the primary dose at the same point (in air for SAR, at d_max for SMR). Used in Clarkson integration method for irregular fields.
*   **Equivalent Square:** The square field size that gives the same PDD/TAR/TMR/Output Factor as a given rectangular or irregular field. Often approximated using tables (e.g., BJR Supplement 25) or `EqSq = 4 * Area / Perimeter` for rectangular fields.
*   **Calculations:**
    *   **SSD Setup:** `Dose(d) = Dose(d_max) * PDD(d)/100`. MU calc involves PDD.
    *   **SAD Setup:** `Dose(d) = Dose_iso * TMR(d) / TMR(d_iso) * (SAD/SAD+d-d_iso)²` (if d != d_iso). MU calc involves TMR at isocenter depth and output factors defined at SAD.

---

## 1. Percent Depth Dose (PDD)

PDD is one of the oldest and most fundamental dose functions, particularly useful for treatments where the patient surface is set at a fixed distance from the source (SSD setups, e.g., electron treatments, older orthovoltage techniques).

*   **Definition:** PDD at a given depth *d* for a specific field size (FS) and Source-Surface Distance (SSD) is defined as the ratio, expressed as a percentage, of the absorbed dose at depth *d* to the absorbed dose at the depth of maximum dose (d<sub>max</sub>), measured along the central axis of the beam:

    `PDD(d, FS, SSD, E) = [Dose(d, FS, SSD, E) / Dose(d_max, FS, SSD, E)] * 100%`

    Where E represents the beam energy.

*   **Measurement:** Typically measured in a water phantom along the central axis using an ionization chamber or diode. The dose at d<sub>max</sub> serves as the normalization point (100%).

*   **Dependencies:**
    *   **Depth (d):** PDD increases from the surface (for MV photons) to d<sub>max</sub> and then decreases with increasing depth due to attenuation and inverse square law.
    *   **Energy (E):** Higher energy beams are more penetrating, resulting in higher PDD values at any given depth beyond d<sub>max</sub>. d<sub>max</sub> also shifts deeper with increasing energy.
    *   **Field Size (FS):** PDD increases with field size due to increased scatter contribution from the phantom to the point of measurement, especially at greater depths. The effect is more pronounced for lower energy beams.
    *   **SSD:** PDD increases with increasing SSD. This is because the inverse square law effect becomes less pronounced over a given depth interval at larger distances. Dose at depth *d* falls off relative to d<sub>max</sub> as `[(SSD+d_max)/(SSD+d)]²`. Increasing SSD makes this ratio closer to 1, thus increasing PDD. This dependence can be approximated using the Mayneord F-factor:
        *   `F = [(SSD₂ + d) / (SSD₁ + d)]² * [(SSD₁ + d_max) / (SSD₂ + d_max)]²`
        *   `PDD₂ ≈ PDD₁ * F`

*   **Clinical Use:** Primarily used for dose calculations in SSD setups. If the dose at d<sub>max</sub> (D<sub>dmax</sub>) is known (e.g., from machine calibration), the dose at any depth *d* is simply:
    *   `Dose(d) = D<sub>dmax</sub> * [PDD(d) / 100]`

## 2. Tissue-Air Ratio (TAR)

TAR was developed to provide a dose function independent of SSD, making it suitable for calculations involving rotational therapy or SAD (Source-Axis Distance) setups where SSD varies.

*   **Definition:** TAR at a given depth *d* for a specific field size (FS<sub>d</sub> at depth d) is defined as the ratio of the absorbed dose at depth *d* in a phantom to the absorbed dose measured at the **same point** in free space (or strictly, within a small equilibrium mass of tissue just large enough to provide electronic equilibrium) under identical beam conditions:

    `TAR(d, FS<sub>d</sub>, E) = Dose(d, FS<sub>d</sub>, E) in phantom / Dose(d, E) in air`

*   **Measurement:** Measuring dose "in air" accurately for high-energy photons is difficult due to the long range of secondary electrons. Requires a buildup cap around the detector to achieve electronic equilibrium. This difficulty led to the development of TPR and TMR.

*   **Dependencies:**
    *   **Depth (d):** TAR decreases with increasing depth due to attenuation.
    *   **Energy (E):** TAR increases with energy due to increased penetration.
    *   **Field Size (FS<sub>d</sub>):** TAR increases with field size defined at depth *d* due to increased scatter contribution.
    *   **SSD:** TAR is essentially **independent** of SSD because both the numerator (dose in phantom) and the denominator (dose in air) follow the inverse square law, and the ratio cancels out the SSD dependence.

*   **Components:** TAR can be considered as the sum of the primary beam contribution and the scattered radiation contribution. The scatter contribution is represented by the Scatter-Air Ratio (SAR).
    *   `TAR(d, FS<sub>d</sub>) = TAR(d, 0) + SAR(d, FS<sub>d</sub>)`
    *   Where `TAR(d, 0)` represents the TAR for a zero-area field (primary beam only).

*   **Clinical Use:** Historically used for SAD calculations. While less common now for MV photons (replaced by TMR/TPR), the concept is fundamental.

## 3. Tissue-Phantom Ratio (TPR) and Tissue-Maximum Ratio (TMR)

TPR and TMR were developed to overcome the practical difficulties of measuring TAR for high-energy beams. They use a reference dose measured *within* the phantom, making them easier to measure and more relevant.

*   **Definition (TPR):** TPR at a given depth *d* for a specific field size (FS<sub>d</sub> at depth d) is defined as the ratio of the absorbed dose at depth *d* in a phantom to the absorbed dose measured at a fixed **reference depth** (d<sub>ref</sub>) in the phantom at the **same point** (i.e., same SAD):

    `TPR(d, FS<sub>d</sub>, E) = Dose(d, FS<sub>d</sub>, E) in phantom / Dose(d_ref, FS<sub>d</sub>, E) in phantom`

    The reference depth d<sub>ref</sub> is typically chosen to be 5 cm or 10 cm.

*   **Definition (TMR):** TMR is a special case of TPR where the reference depth is chosen to be the depth of maximum dose (d<sub>max</sub>):

    `TMR(d, FS<sub>d</sub>, E) = Dose(d, FS<sub>d</sub>, E) in phantom / Dose(d_max, FS<sub>d</sub>, E) in phantom`

*   **Measurement:** Measured in a water phantom by keeping the detector at a fixed point (SAD) and changing the amount of water above the detector (i.e., changing the depth *d*). The field size is defined at the detector position (SAD).

*   **Dependencies:**
    *   **Depth (d):** TMR/TPR decrease with increasing depth beyond d<sub>ref</sub>/d<sub>max</sub> due to attenuation. TMR is normalized to 1.0 at d<sub>max</sub>.
    *   **Energy (E):** TMR/TPR increase with energy due to increased penetration.
    *   **Field Size (FS<sub>d</sub>):** TMR/TPR increase with field size defined at depth *d* (or SAD) due to increased scatter.
    *   **SSD:** TMR and TPR are **independent** of SSD, as both numerator and denominator are measured at the same distance from the source.

*   **Relationship between TPR and TMR:** They are closely related, differing only by the normalization depth. `TPR(d, FS) = TMR(d, FS) / TMR(d_ref, FS)`.

*   **Clinical Use:** TMR is the most commonly used dose function for dose calculations in SAD setups (isocentric treatments) with MV photon beams.
    *   If the dose is known at the isocenter depth (d<sub>iso</sub>), the dose at any other depth *d* along the central axis (at the same SAD) can be found using TMR:
        *   `Dose(d) = Dose(d_iso) * [TMR(d) / TMR(d_iso)]`
    *   Note: This simple ratio only applies if the point *d* is at the same distance from the source as the isocenter. If calculating dose off-axis or at a different distance, inverse square corrections are also needed.

## 4. Scatter Functions (SAR, SMR)

These functions isolate the contribution of scattered radiation to the total dose.

*   **Scatter-Air Ratio (SAR):** Defined as the difference between the TAR for a given field size and the TAR for a zero-area field (primary beam only) at the same depth:

    `SAR(d, FS<sub>d</sub>) = TAR(d, FS<sub>d</sub>) - TAR(d, 0)`

*   **Scatter-Maximum Ratio (SMR):** Defined similarly using TMR, representing the ratio of the scattered dose at depth *d* to the primary dose at d<sub>max</sub>:

    `SMR(d, FS<sub>d</sub>) = TMR(d, FS<sub>d</sub>) * SF(FS<sub>d</sub>) - TMR(d, 0) * SF(0)`
    *   Often simplified or defined relative to dose at dmax for the field size: `SMR(d, FS<sub>d</sub>) ≈ TMR(d, FS<sub>d</sub>) - TMR(d, 0)` (assuming scatter factor dependence is implicitly handled or approximated).
    *   The term `TMR(d, 0)` represents the TMR due to the primary beam only.

*   **Clinical Use:** SAR and SMR are primarily used in calculation methods that separate primary and scatter dose components, such as the Clarkson integration method for calculating dose from irregular fields. This method involves dividing the irregular field into sectors, calculating the scatter contribution from each sector using SAR/SMR values based on the sector radius, and summing them up along with the primary component.

## 5. Relationships Between Dose Functions

PDD, TAR, TPR, and TMR are all related and can be converted from one to another if the necessary parameters (SSD, energy, field size) are known.

*   **PDD and TMR:** This is a common conversion needed when applying data measured at a fixed SSD (PDD) to an SAD setup (TMR), or vice versa.
    *   `TMR(d, FS<sub>d</sub>) = [PDD(d, FS<sub>SSD</sub>, SSD) / 100] * [(SSD + d) / (SSD + d_max)]² * [SF(FS<sub>d</sub>) / SF(FS<sub>SSD</sub>)]`
        *   Where FS<sub>d</sub> is the field size at depth *d* (or SAD), and FS<sub>SSD</sub> is the field size defined at the surface for the PDD measurement.
        *   The term `[(SSD + d) / (SSD + d_max)]²` corrects for the inverse square law difference between depth *d* and d<sub>max</sub> relative to the source.
        *   The ratio of Scatter Factors (SF) or Collimator Scatter Factors (Sc) and Phantom Scatter Factors (Sp) might be needed for full rigor depending on how functions are defined and measured, but is often approximated or implicitly included.
    *   `PDD(d, FS<sub>SSD</sub>, SSD) = 100 * TMR(d, FS<sub>d</sub>) * [(SSD + d_max) / (SSD + d)]² * [SF(FS<sub>SSD</sub>) / SF(FS<sub>d</sub>)]`

*   **TAR and TMR/TPR:** Related through the backscatter factor (BSF) or peak scatter factor (PSF).
    *   `TAR(d, FS) = TMR(d, FS) * BSF(FS)` (BSF defined relative to dose in air)
    *   `TAR(d, FS) = TMR(d, FS) * PSF(FS)` (PSF defined relative to dose at dmax in a minimal phantom)

## 6. Equivalent Squares

Tabulated dose function data (PDD, TMR, etc.) and output factors are typically listed for square field sizes. To use this data for rectangular or irregular fields, the concept of equivalent square is used.

*   **Definition:** The equivalent square field (EqSq or L<sub>eq</sub>) of a non-square field is the side length of a square field that has the same dosimetric properties (e.g., same PDD, TMR, output factor) as the non-square field.
*   **Rectangular Fields:** For a rectangular field of size W x L, the equivalent square is often found using tables based on empirical data (e.g., BJR Supplement 25). A common approximation is:
    *   `EqSq ≈ (2 * W * L) / (W + L)`
*   **Circular Fields:** Equivalent square ≈ 0.89 * Diameter.
*   **Irregular Fields (Clarkson Method):** For complex irregular fields, the Clarkson integration method uses SAR/SMR values based on the radii of sectors covering the field to determine the effective scatter contribution, which can then be related back to an equivalent square or used directly.
*   **Use:** Once the equivalent square field size is determined, the tabulated data for that square field size can be used in dose calculations.

## 7. Applications in Dose Calculations

*   **SSD Setups (PDD):**
    *   Machine calibrated to deliver known dose rate (e.g., 1.0 cGy/MU) at d<sub>max</sub> for a reference field size (e.g., 10x10) and reference SSD (e.g., 100 cm).
    *   `MU = Prescribed Dose(d) / (DoseRate_ref * OutputFactor(FS) * [PDD(d, FS, SSD) / 100] * InvSqFactor_SSD)`
        *   OutputFactor accounts for field size change relative to reference.
        *   InvSqFactor_SSD corrects if treatment SSD differs from calibration SSD, `[(SSD_cal + d_max) / (SSD_treat + d_max)]²`.

*   **SAD Setups (TMR):**
    *   Machine calibrated to deliver known dose rate at isocenter (SAD) for a reference field size.
    *   Calculation point is usually the isocenter (depth d<sub>iso</sub>).
    *   `MU = Prescribed Dose(d_iso) / (DoseRate_ref * OutputFactor(FS_iso) * TMR(d_iso, FS_iso))`
        *   OutputFactor (Scp or Total Output Factor) includes collimator and phantom scatter, defined for field size at isocenter (FS<sub>iso</sub>).
    *   To find dose at another depth *d* on central axis:
        *   `Dose(d) = MU * DoseRate_ref * OutputFactor(FS_iso) * TMR(d, FS_iso)` (Note: FS<sub>iso</sub> is used for TMR at depth d as well, as TMR depends on FS at SAD).

---

**Assessment Questions (ABR Style):**

1.  Percent Depth Dose (PDD) increases with increasing:
    I.   Energy
    II.  Field Size
    III. SSD
    (A) I only
    (B) I and II only
    (C) II and III only
    (D) I and III only
    (E) I, II, and III

2.  Which of the following dose functions is inherently independent of SSD?
    (A) PDD
    (B) TMR
    (C) Mayneord F-factor
    (D) Backscatter Factor (BSF)
    (E) Both (B) and (D)

3.  Tissue-Maximum Ratio (TMR) is defined as the ratio of the dose at a point in phantom to the dose at:
    (A) The same point in air
    (B) A fixed reference depth (e.g., 5 cm) in phantom
    (C) The depth of maximum dose (d<sub>max</sub>) in phantom
    (D) The surface of the phantom
    (E) The isocenter

4.  The Mayneord F-fa
(Content truncated due to size limit. Use line ranges to read in chunks)