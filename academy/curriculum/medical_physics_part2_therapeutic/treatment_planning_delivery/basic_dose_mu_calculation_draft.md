# Section 5.8: Basic Dose (Monitor Unit) Calculation

**Approximate Lecture Time:** 2.5-3 Hours

**Learning Objectives:**

Upon completion of this section, the student will be able to:

1.  **Define** Monitor Unit (MU) and **explain** its role in radiation therapy delivery.
2.  **Describe** standard linac calibration conditions (e.g., 1 cGy/MU at d<sub>max</sub> for a 10x10 cm field at 100 cm SSD or SAD).
3.  **Identify and define** the factors required for basic MU calculations, including:
    *   Output factors: Collimator Scatter Factor (Sc), Phantom Scatter Factor (Sp), Total Scatter Factor (Scp).
    *   Dose functions: Percent Depth Dose (PDD), Tissue-Maximum Ratio (TMR).
    *   Distance corrections: Inverse Square Law factors.
    *   Transmission factors: Tray Factor (TF), Wedge Factor (WF).
    *   Off-Axis Ratio (OAR) or profile factors.
4.  **State and apply** the formula for MU calculation in SSD (Source-Surface Distance) setups using PDD.
5.  **State and apply** the formula for MU calculation in SAD (Source-Axis Distance) setups using TMR.
6.  **Perform** basic MU calculations for open and modified (wedged, blocked) fields in both SSD and SAD setups.
7.  **Explain** how equivalent squares are used in determining output and scatter factors.

**Key Points:**

*   **Monitor Unit (MU):** An arbitrary unit specific to a linac, representing a measure of beam-on time or integrated charge collected in the monitor ionization chamber. Linacs are calibrated to deliver a specific dose (e.g., 1 cGy) per MU under reference conditions.
*   **Calibration:** Typically 1 cGy/MU at d<sub>max</sub> for a 10x10 cm field size at 100 cm SSD (for SSD setups) or 1 cGy/MU at the isocenter (100 cm SAD) at d<sub>max</sub> for a 10x10 cm field (for SAD setups).
*   **Output Factors:** Correct the dose rate from reference conditions to treatment conditions.
    *   **Sc (Collimator Scatter Factor):** Ratio of dose rate for a given collimator setting to the dose rate for the reference collimator setting (10x10), measured in air. Depends on collimator setting.
    *   **Sp (Phantom Scatter Factor):** Ratio of dose rate for a given field size to the dose rate for the reference field size (10x10), accounting for scatter from the phantom. Depends on field size at depth.
    *   **Scp (Total Scatter Factor):** Combines Sc and Sp. `Scp(FS) = Sc(coll_setting) * Sp(FS_at_depth)`. Ratio of dose rate for a given field size in phantom to the dose rate for the reference field size (10x10) in phantom.
*   **SSD Calculation:** `MU = Prescribed_Dose(d) / (Cal_DoseRate * Scp(FS_SSD) * [PDD(d, FS_SSD, SSD) / 100] * ISqFactor * TF * WF * ...)`
    *   `FS_SSD` is field size at surface.
    *   `ISqFactor = [(SSD_cal + d_max_cal) / (SSD_treat + d_max_treat)]²` if treatment SSD differs from calibration SSD.
*   **SAD Calculation:** `MU = Prescribed_Dose(iso) / (Cal_DoseRate * Scp(FS_iso) * TMR(d_iso, FS_iso) * ISqFactor * TF * WF * ...)`
    *   `FS_iso` is field size at isocenter.
    *   `ISqFactor = (SAD_cal / SAD_treat)²` if treatment SAD differs from calibration SAD (usually both are 100 cm, so factor is 1).
    *   If calculating dose off-axis or at a depth *d* different from isocenter depth *d_iso*: `Dose(d) = MU * Cal_DoseRate * Scp(FS_iso) * TMR(d, FS_iso) * (SAD/Distance_to_point)² * OAR`
*   **Equivalent Square:** Used to find Sc, Sp, Scp, PDD, TMR for non-square fields from tabulated data for square fields.

---

## 1. Monitor Units (MUs) and Calibration

*   **Monitor Units (MUs):** Linear accelerators do not directly measure absorbed dose delivered to the patient. Instead, they use internal monitor ionization chambers located in the treatment head (after the target/flattening filter but before the collimating jaws) to measure integrated beam output. The reading from these chambers is displayed in Monitor Units (MUs). MUs are essentially a proxy for beam-on time, adjusted for dose rate variations.
*   **Calibration:** To relate MUs to absorbed dose, the linac must be calibrated under specific reference conditions. The goal is to establish the dose delivered per MU under these conditions. A common calibration standard (following protocols like TG-51) is:
    *   **1.0 cGy/MU** delivered at the **depth of maximum dose (d<sub>max</sub>)**
    *   in a **water phantom**
    *   for a **10 cm x 10 cm field size** defined at the reference distance
    *   at a **Source-Surface Distance (SSD) of 100 cm** (or Source-Axis Distance (SAD) of 100 cm, depending on the primary setup type used clinically).
    *   This calibrated dose rate (1 cGy/MU) serves as the baseline for all subsequent MU calculations.

## 2. Factors Affecting Dose Delivery

When moving from reference calibration conditions to actual patient treatment conditions, several factors change the dose delivered per MU at the point of interest (e.g., prescription point). MU calculations must account for these factors:

*   **Field Size Effects (Scatter):** Changing the field size alters the amount of scattered radiation reaching the point of interest.
    *   **Collimator Scatter (Sc):** Radiation scattered from the collimator system (jaws, MLCs). Depends on the physical opening of the collimators. Measured "in air" with a buildup cap. Defined as the ratio of dose in air for collimator setting *c* to dose in air for the reference 10x10 setting:
        `Sc(c) = Dose_air(c) / Dose_air(10x10)`
    *   **Phantom Scatter (Sp):** Radiation scattered within the patient/phantom. Depends on the irradiated volume, characterized by the field size at the depth of interest. Defined as the ratio of dose for field size *FS* to dose for the reference 10x10 field, considering only phantom scatter (often derived from total scatter and collimator scatter):
        `Sp(FS) = Scp(FS) / Sc(c)` (where *c* corresponds to *FS*)
    *   **Total Scatter Factor (Scp or S<sub>cp</sub> or Output Factor):** Accounts for changes in both collimator and phantom scatter. Defined as the ratio of dose rate in phantom for field size *FS* to the dose rate for the reference 10x10 field size in phantom under the same setup conditions (depth, distance):
        `Scp(FS) = Dose_phantom(FS) / Dose_phantom(10x10)`
        Scp is the most commonly used output factor in basic MU calculations. It depends on the field size defined at the reference distance (SSD or SAD).
    *   **Equivalent Square:** For rectangular fields (W x L), the equivalent square field size (`EqSq`) is used to look up Sc, Sp, and Scp values from tables generated for square fields. `EqSq ≈ (2 * W * L) / (W + L)`.

*   **Depth Effects (Attenuation and Scatter):** The dose deposited varies with depth.
    *   **Percent Depth Dose (PDD):** Used for SSD setups. Represents the dose at depth *d* as a percentage of the dose at d<sub>max</sub> for a given field size and SSD. `PDD(d, FS, SSD)`.
    *   **Tissue-Maximum Ratio (TMR):** Used for SAD setups. Ratio of dose at depth *d* to dose at d<sub>max</sub> for the same field size defined at the SAD. `TMR(d, FS)`. Independent of distance.

*   **Distance Effects (Inverse Square Law):** Radiation intensity decreases with the square of the distance from the source.
    *   Corrections are needed if the treatment distance (SSD or SAD) differs from the calibration distance, or when calculating dose at points other than d<sub>max</sub> (for PDD) or the isocenter (for TMR).

*   **Beam Modifiers (Transmission Factors):** Devices placed in the beam path attenuate the beam.
    *   **Tray Factor (TF):** Accounts for attenuation by a blocking tray or MLC base. `TF = Dose_with_tray / Dose_without_tray`. Typically 0.97-0.99.
    *   **Wedge Factor (WF):** Accounts for attenuation along the central axis by a physical or dynamic wedge. `WF = Dose_with_wedge / Dose_without_wedge` (measured on central axis). Depends on wedge angle, field size, depth, and energy.

*   **Off-Axis Effects:** Dose intensity varies across the beam profile (not perfectly flat).
    *   **Off-Axis Ratio (OAR):** Ratio of dose at an off-axis point to the dose on the central axis at the same depth. Used if the calculation point is not on the central axis.

## 3. MU Calculation for SSD Setups

In SSD setups, the patient surface is placed at a fixed distance from the source (e.g., 100 cm SSD). Dose is often prescribed to d<sub>max</sub> or another depth *d*. PDD is the relevant dose function.

**Formula:**

`MU = Prescribed_Dose(d) / (Cal_DoseRate * Scp(FS_SSD) * [PDD(d, FS_SSD, SSD) / 100] * ISqFactor * TF * WF * OAR * ...)`

Where:
*   `Prescribed_Dose(d)`: The dose to be delivered to the calculation point at depth *d* (in cGy).
*   `Cal_DoseRate`: The calibrated dose rate under reference conditions (typically 1.0 cGy/MU).
*   `Scp(FS_SSD)`: Total scatter factor for the field size defined at the surface (SSD).
*   `PDD(d, FS_SSD, SSD)`: Percent depth dose at depth *d* for the field size at SSD and the treatment SSD.
*   `ISqFactor`: Inverse square correction factor. Only needed if the treatment SSD differs from the calibration SSD (SSD<sub>cal</sub>, usually 100 cm). `ISqFactor = [(SSD_cal + d_max_cal) / (SSD_treat + d_max_treat)]²`. If SSD<sub>treat</sub> = SSD<sub>cal</sub>, this factor is 1.
*   `TF`: Tray factor (if used).
*   `WF`: Wedge factor (if used).
*   `OAR`: Off-axis ratio (if calculation point is off-axis).

**Example (SSD):**
Prescribe 200 cGy to d<sub>max</sub> for a 15x15 cm field at 100 cm SSD using 6 MV photons. Linac calibrated at 100 cm SSD to give 1 cGy/MU at d<sub>max</sub> for 10x10 field. Scp(15x15) = 1.020. No tray or wedge.

*   Depth *d* = d<sub>max</sub>. By definition, PDD(d<sub>max</sub>) = 100%.
*   SSD<sub>treat</sub> = SSD<sub>cal</sub> = 100 cm, so ISqFactor = 1.
*   `MU = 200 cGy / (1.0 cGy/MU * 1.020 * [100 / 100] * 1 * 1 * 1)`
*   `MU = 200 / 1.020 ≈ 196 MU`

**Example 2 (SSD):**
Prescribe 180 cGy to a depth of 10 cm for a 12x8 cm field at 100 cm SSD using 6 MV. Linac calibrated as above. EqSq(12x8) ≈ 9.6 cm. Scp(9.6x9.6) = 0.995. PDD(10 cm, 9.6x9.6, 100 SSD) = 67.5%. No tray or wedge.

*   `MU = 180 cGy / (1.0 cGy/MU * 0.995 * [67.5 / 100] * 1 * 1 * 1)`
*   `MU = 180 / (0.995 * 0.675)`
*   `MU = 180 / 0.6716 ≈ 268 MU`

## 4. MU Calculation for SAD Setups

In SAD (isocentric) setups, the linac rotates around the isocenter, which is placed within the patient (e.g., 100 cm SAD). The SSD varies depending on the beam angle and patient contour. Dose is prescribed to the isocenter or another point defined relative to it. TMR is the relevant dose function.

**Formula (Prescription to Isocenter):**

`MU = Prescribed_Dose(iso) / (Cal_DoseRate * Scp(FS_iso) * TMR(d_iso, FS_iso) * ISqFactor * TF * WF * OAR * ...)`

Where:
*   `Prescribed_Dose(iso)`: The dose to be delivered to the isocenter (in cGy).
*   `Cal_DoseRate`: The calibrated dose rate under reference conditions (typically 1.0 cGy/MU at d<sub>max</sub> for 10x10 at 100 SAD, or sometimes defined at isocenter depth for reference field).
*   `Scp(FS_iso)`: Total scatter factor for the field size defined at the isocenter (SAD).
*   `TMR(d_iso, FS_iso)`: Tissue-maximum ratio for the isocenter depth (`d_iso`) and field size at isocenter.
*   `ISqFactor`: Inverse square correction factor. Only needed if the treatment SAD differs from the calibration SAD (SAD<sub>cal</sub>, usually 100 cm). `ISqFactor = (SAD_cal / SAD_treat)²`. If SAD<sub>treat</sub> = SAD<sub>cal</sub>, this factor is 1.
*   `TF`: Tray factor (if used).
*   `WF`: Wedge factor (if used).
*   `OAR`: Off-axis ratio (if calculation point is off-axis relative to isocenter).

**Important Note on Calibration for SAD:** Some clinics calibrate 1 cGy/MU at d<sub>max</sub> at SAD, while others calibrate 1 cGy/MU *at the isocenter depth* (e.g., 10 cm) at SAD. If calibrated at isocenter depth d<sub>ref</sub>, the formula simplifies slightly as the TMR term might be implicitly included in the calibration definition, or the reference dose rate needs adjustment. Assuming calibration is 1 cGy/MU at d<sub>max</sub> at SAD:

**Example (SAD):**
Prescribe 200 cGy to the isocenter located at a depth of 8 cm. Field size is 12x12 cm at isocenter (100 cm SAD). 6 MV beam. Linac calibrated to 1 cGy/MU at d<sub>max</sub> (1.5 cm) for 10x10 field at 100 cm SAD. Scp(12x12) = 1.010. TMR(8 cm, 12x12) = 0.815. No tray or wedge.

*   SAD<sub>treat</sub> = SAD<sub>cal</sub> = 100 cm, so ISqFactor = 1.
*   `MU = 200 cGy / (1.0 cGy/MU * 1.010 * 0.815 * 1 * 1 * 1)`
*   `MU = 200 / (1.010 * 0.815)`
*   `MU = 200 / 0.82315 ≈ 243 MU`

**Calculating Dose at a Point other than Isocenter (SAD):**
If MU is known, the dose `Dose(P)` at an arbitrary point P (depth *d*, off-axis distance *r*) can be calculated:

`Dose(P) = MU * Cal_DoseRate * Scp(FS_iso) * TMR(d, FS_iso) * (SAD / Distance_to_P)² * OAR(d, r)`

*   `Distance_to_P` is the distance from the source to point P.
*   `OAR(d, r)` is the off-axis ratio at depth *d* and off-axis distance *r*.
*   Note that Scp and TMR still use the field size defined at the isocenter (`FS_iso`).

## 5. Worked Examples

**(Include more complex examples involving wedges, blocks/MLCs requiring equivalent square calculations, off-axis points, and potentially electron MU calculations if covered previously).**

**Example 3 (SSD with Wedge):**
Prescribe 180 cGy to d<sub>max</sub> for a 10x15 cm field at 100 cm SSD using 6 MV. A 30-degree physical wedge is used. Linac calibrated as before (1 cGy/MU at d<sub>max</sub>, 10x10, 100 SSD). EqSq(10x15) ≈ 12 cm. Scp(12x12) = 1.010. Wedge Factor (30°, 12x12) = 0.650. No tray.

*   Depth *d* = d<sub>max</sub>. PDD = 100%.
*   SSD<sub>treat</sub> = SSD<sub>cal</sub> = 100 cm, ISqFactor = 1.
*   `MU = 180 cGy / (1.0 cGy/MU * 1.010 * [100 / 100] * 1 * 1 * 0.650)`
*   `MU = 180 / (1.010 * 0.650)`
*   `MU = 180 / 0.6565 ≈ 274 MU`

**Example 4 (SAD with Tray):**
Prescribe 250 cGy to the isocenter at 12 cm depth. Field size 20x10 cm at isocenter (100 cm SAD). 10 MV beam. Linac calibrated 1 cGy/MU at d<sub>max</sub> (2.5 cm) for 10x10 at 100 SAD. EqSq(20x10) ≈ 13.3 cm. Scp(13.3x13.3) = 1.035. TMR(12 cm, 13.3x13.3) = 0.750. A standard blocking tray is used, TF = 0.975. No wedge.

*   SAD<sub>treat</sub> = SAD<sub>cal</sub> = 100 cm, ISqFactor = 1.
*   `MU = 250 cGy / (1.0 cGy/MU * 1.035 * 0.750 * 1 * 0.975 * 1)`
*   `MU = 250 / (1.035 * 0.750 * 0.975)`
*   `MU = 250 / 0.7575 ≈ 330 MU`

---

**Assessment Questions (ABR Style):**

1.  A linear accelerator is calibrated to deliver 1.0 cGy/MU at d<sub>max</sub> for a 10x10 cm field at 100 cm SSD. For a treatment using a 15x15 cm field at 100 cm SSD, which factor primarily accounts for the change in dose rate at d<sub>max</sub> compared to calibration?
    (A) PDD
    (B) TMR
    (C) Scp (Total Scatter Factor)
    (D) Inverse Square Factor
    (E) Wedge Factor

2.  In an SAD treatment setup (100 cm SAD), if the dose is prescribed to the isocenter at depth *d*, the MU calculation primarily uses which dose function?
    (A) PDD(d, FS_iso, 100 SSD)
    (B) PDD(d, FS_iso, Variable SSD)
    (C) TMR(d, FS_iso)
    (D) TAR(d, FS_iso)
    (E) Mayneord F-Factor

3.  For an SSD treatment at 100 cm SSD, 180 cGy is prescribed to a depth of 5 cm using a 6 MV beam. Calibration is 1 cGy/MU at d<sub>max</sub> (1.5 cm) for 10x10 at 100 SSD. Given: Scp(field) = 1.015, PDD(5 cm, field, 100 SSD) = 85.0%. Calculate the required MUs.
    (A) 180 MU
    (B) 205 MU
    (C) 211 MU
    (D) 241 MU
    (E) 250 MU

4.  For an SAD treatment at 100 cm SAD, 200 cGy is prescribed to the isocenter at 10 cm depth using a 10 MV beam. Calibration is 1 cGy/MU at d<sub>max</sub> (2.5 cm) for 10x10 at 100 SAD. Given: Scp(field) = 1.030, TMR(10 cm, field) = 0.780. Calculate the required MUs.
    (A) 200 MU
    (B) 249 MU
    (C) 256 MU
    (D) 263 MU
    (E) 328 MU

5.  Which of the following factors is generally INDEPENDENT of depth in the phantom?
    (A) PDD
    (B) TMR
    (C) Sc (Collimator Scatter Factor)
    (D) Sp (Phantom Scatter Factor)
    (E) Off-Axis Ratio

6
(Content truncated due to size limit. Use line ranges to read in chunks)