# Section 2.3: Specialized Machines - Worked Examples

**Example 1: Gamma Knife Dose Rate Calculation (TG-178)**

*   **Problem:** A physicist is performing the annual calibration of a Leksell Gamma Knife Perfexion unit using an Exradin A16 ionization chamber ($N_{D,w}^{Co-60} = 5.450 \times 10^7$ Gy/C) according to TG-178. The measurement is performed at the UCP within the Elekta ABS phantom using the 16 mm collimator setting. The average raw electrometer reading is 35.05 nC for a 60-second irradiation time. Environmental conditions are T = 21.5 °C and P = 101.8 kPa. Ion recombination ($P_{ion}$) was measured as 1.006, and polarity correction ($P_{pol}$) as 0.998. Calculate the absorbed dose rate to water at the UCP for the 16 mm setting.
*   **Solution:**
    1.  **Calculate $P_{TP}$:**
        $P_{TP} = \frac{(273.15 + T)}{(273.15 + 22)} \times \frac{101.325}{P} = \frac{(273.15 + 21.5)}{(273.15 + 22)} \times \frac{101.325}{101.8} = 0.9983 \times 0.9953 = 0.9936$
    2.  **Calculate Corrected Charge ($M_{Q_{msr}}^{f_{msr}}$):**
        $M = M_{raw} \times P_{TP} \times P_{ion} \times P_{pol} = (35.05 \times 10^{-9} \text{ C}) \times 0.9936 \times 1.006 \times 0.998 = 34.92 \times 10^{-9} \text{ C}$
    3.  **Find $k_{Q_{msr}, Q}^{f_{msr}, f_{ref}}$:** From TG-178 Table V for an Exradin A16 chamber in an LGK Perfexion (approximated as Co-60 spectrum), $k_{Q_{msr}, Q}^{f_{msr}, f_{ref}} \approx 1.000$ (as the beam quality is very close to Co-60).
    4.  **Calculate Dose Rate ($\\dot{D}_{w, Q_{msr}}^{f_{msr}}$):**
        $\dot{D}_{w, Q_{msr}}^{f_{msr}} = \frac{M}{t} \times N_{D,w}^{Co-60} \times k_{Q_{msr}, Q}^{f_{msr}, f_{ref}}$
        $\dot{D}_{w, Q_{msr}}^{f_{msr}} = \frac{34.92 \times 10^{-9} \text{ C}}{60 \text{ s}} \times (5.450 \times 10^7 \text{ Gy/C}) \times 1.000$
        $\dot{D}_{w, Q_{msr}}^{f_{msr}} = (5.82 \times 10^{-10} \text{ C/s}) \times (5.450 \times 10^7 \text{ Gy/C}) = 3.17 \text{ Gy/min}$
*   **Conclusion:** The absorbed dose rate to water at the UCP for the 16 mm collimator setting is approximately 3.17 Gy/min under the reference conditions specified by TG-178.

**Example 2: Orthovoltage PDD Calculation (Approximate)**

*   **Problem:** Using typical orthovoltage data (e.g., BJR Supplement 25), estimate the Percent Depth Dose (PDD) at 2 cm depth for a 10 cm x 10 cm field size at 50 cm SSD, for a beam with HVL = 2.0 mm Cu (approx. 200 kVp).
*   **Solution:**
    1.  **Locate Relevant Data:** Find PDD tables in BJR Supplement 25 (or similar resource) for HVL = 2.0 mm Cu.
    2.  **Find PDD:** Look up the PDD value for a 10x10 cm² field at 50 cm SSD and 2 cm depth.
        *   (Example value from BJR Suppl. 25, Table 4.10): For HVL 2.0 mm Cu, 10x10 field, 50 cm SSD, the PDD at 2 cm depth is approximately 68.1%.
*   **Conclusion:** The approximate PDD at 2 cm depth for this beam configuration is 68.1%. This means the dose at 2 cm is about 68.1% of the dose at the depth of maximum dose (dmax, usually the surface for orthovoltage).

**Example 3: CyberKnife Output Constancy Check**

*   **Problem:** The daily QA check for a CyberKnife G4 system involves delivering 1000 MU using the fixed 15 mm collimator to a dedicated QA phantom with an integrated detector. The baseline reading established at commissioning was 1.050 (arbitrary units). Today's reading is 1.035. Is this within a typical ±2% tolerance?
*   **Solution:**
    1.  **Calculate Percent Difference:**
        $\% \text{ Difference} = \frac{(\text{Current Reading} - \text{Baseline Reading})}{\text{Baseline Reading}} \times 100\%$
        $\% \text{ Difference} = \frac{(1.035 - 1.050)}{1.050} \times 100\% = \frac{-0.015}{1.050} \times 100\% = -1.43\%$
    2.  **Compare to Tolerance:** The calculated difference (-1.43%) is within the ±2% tolerance.
*   **Conclusion:** The CyberKnife output is within the acceptable tolerance for the daily QA check.

**Example 4: TomoTherapy MVCT Number Accuracy**

*   **Problem:** During monthly QA on a TomoTherapy unit, the MVCT scan of a cheese phantom is analyzed. The mean MVCT number in a region of interest (ROI) known to be solid water equivalent is measured as +15 Hounsfield Units (HU). The baseline value for this ROI is +5 HU. Is this within a typical tolerance of ±20 HU?
*   **Solution:**
    1.  **Calculate Difference:**
        Difference = Current Value - Baseline Value = +15 HU - (+5 HU) = +10 HU
    2.  **Compare to Tolerance:** The difference (+10 HU) is within the ±20 HU tolerance.
*   **Conclusion:** The MVCT number accuracy for the solid water equivalent material is within the acceptable tolerance for the monthly QA check.
