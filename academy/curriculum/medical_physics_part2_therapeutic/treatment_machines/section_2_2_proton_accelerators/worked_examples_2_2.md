# Section 2.2: Proton Accelerators and Beam Characteristics - Worked Examples

## Worked Example 2.2.1: Proton Range Calculation (Simplified)

**Problem:** Estimate the range of a 150 MeV proton beam in water using a simplified range-energy relationship.

**Background:** A common approximation for the range (R) of protons in water is given by the formula:
R (cm) ≈ α * (E (MeV))^p
Where α ≈ 0.0022 and p ≈ 1.77 for energies above ~10 MeV.

**Solution:**

1.  **Identify the given energy:** E = 150 MeV
2.  **Apply the simplified range formula:**
    R ≈ 0.0022 * (150)^1.77
3.  **Calculate the energy term:**
    150^1.77 ≈ 150^(1 + 0.77) = 150 * 150^0.77
    Using a calculator: 150^1.77 ≈ 14555
4.  **Calculate the range:**
    R ≈ 0.0022 * 14555
    R ≈ 32.02 cm

**Answer:** The estimated range of a 150 MeV proton beam in water using this simplified formula is approximately 16.1 cm.

*Calculation Correction & Refinement:*
Let's re-calculate 150^1.77 more accurately.
150^1.77 ≈ 14555.4
R ≈ 0.0022 * 14555.4 ≈ 32.02 cm

*Further Refinement using more standard values (α=0.002, p=1.8):*
R ≈ 0.002 * (150)^1.8
150^1.8 ≈ 16997.5
R ≈ 0.002 * 16997.5 ≈ 34.0 cm

*Note:* Actual range values depend on the specific data tables (e.g., ICRU/NIST) and definitions used (e.g., practical range, csda range). For 150 MeV protons, the practical range in water is closer to 15.9-16.0 cm. The simplified formulas provide rough estimates but precise values require lookup tables or more sophisticated calculations (like Bethe-Bloch integration).

Let's use a more clinically relevant approximation often cited: R ≈ (E/100)^1.8 * 2.5 cm (This is very rough)
Or R ≈ 0.1 * (E/10)^(5/3) cm

Let's stick to the first formula but use more standard coefficients if available, or acknowledge the limitations. A better known approximation is R = 0.022 * E^1.77 (if E is in MeV, R in g/cm², which is cm for water). Let's retry with α = 0.022.

R ≈ 0.022 * (150)^1.77
R ≈ 0.022 * 14555.4
R ≈ 320.2 g/cm² (This seems far too high, suggesting the coefficient or exponent is incorrect for this form)

Let's use the widely cited empirical formula by Bortfeld (based on Bragg-Kleeman rule modifications):
R_p = α * E^p
Where α = 0.0022 cm/MeV^p and p = 1.77
Wait, the coefficient α should have units that result in cm. If R is in cm and E in MeV, α should be cm/MeV^p.
Let's re-evaluate the calculation R ≈ 0.0022 * (150)^1.77
R ≈ 0.0022 * 14555.4 ≈ 32.0 cm. This still seems high. Perhaps the coefficient is intended for g/cm²?

*Revisiting Standard Data:* According to NIST PSTAR data, the CSDA range for 150 MeV protons in water is 15.96 g/cm² (or 15.96 cm).

Let's find a better formula or use the known value and demonstrate uncertainty.

**Revised Example using NIST data and showing uncertainty impact:**

**Problem:** A proton beam has a nominal energy of 150 MeV. According to NIST data, the CSDA range is 15.96 cm in water. If the range uncertainty due to CT calibration is ±3.5%, what is the potential variation in the proton range?

**Solution:**

1.  **Identify the nominal range:** R_nominal = 15.96 cm
2.  **Identify the uncertainty:** Uncertainty = ±3.5%
3.  **Calculate the absolute uncertainty:**
    Absolute Uncertainty = 3.5% of 15.96 cm
    Absolute Uncertainty = 0.035 * 15.96 cm ≈ 0.56 cm
4.  **Determine the potential range variation:**
    Minimum Range = R_nominal - Absolute Uncertainty = 15.96 cm - 0.56 cm = 15.40 cm
    Maximum Range = R_nominal + Absolute Uncertainty = 15.96 cm + 0.56 cm = 16.52 cm

**Answer:** Due to a ±3.5% range uncertainty, the actual range of the 150 MeV proton beam could vary between approximately 15.40 cm and 16.52 cm.

## Worked Example 2.2.2: SOBP Modulation Width

**Problem:** A Spread-Out Bragg Peak (SOBP) is formed using pristine Bragg peaks (PBPs) ranging from 100 MeV (Range ≈ 7.6 cm) to 120 MeV (Range ≈ 10.6 cm). Estimate the modulation width of the SOBP.

**Background:** The modulation width of an SOBP is defined as the distance between the proximal 90% dose level and the distal 90% dose level. It roughly corresponds to the difference in ranges of the lowest and highest energy protons used to create the flat dose region.

**Solution:**

1.  **Identify the range of the lowest energy PBP:** R_min ≈ 7.6 cm (for 100 MeV)
2.  **Identify the range of the highest energy PBP:** R_max ≈ 10.6 cm (for 120 MeV)
3.  **Estimate the modulation width:**
    Modulation Width ≈ R_max - R_min
    Modulation Width ≈ 10.6 cm - 7.6 cm = 3.0 cm

**Answer:** The estimated modulation width of the SOBP is approximately 3.0 cm.

*Note:* This is an estimation. The actual 90%-90% width depends on the specific weighting of the pristine peaks used to create the SOBP and the shape of the distal fall-off.

## Worked Example 2.2.3: Daily QA Range Check (Based on TG-224 Principle)

**Problem:** During daily QA, the range of a reference proton beam (e.g., 200 MeV) is measured using a multi-layer ionization chamber (MLIC) or water phantom scan. The expected range (baseline) is 25.5 cm. Today's measurement yields a range of 25.3 cm. Does this fall within a typical tolerance?

**Background:** AAPM TG-224 recommends daily checks for proton beam range consistency. A typical tolerance for range agreement is ±1 mm or ±1% of the range, whichever is larger (though specific institutions may set tighter tolerances).

**Solution:**

1.  **Identify the baseline range:** R_baseline = 25.5 cm = 255 mm
2.  **Identify the measured range:** R_measured = 25.3 cm = 253 mm
3.  **Calculate the difference:**
    Difference = R_measured - R_baseline = 253 mm - 255 mm = -2 mm
4.  **Determine the tolerance:**
    Tolerance = ±1 mm or ±1% of Range
    1% of Range = 0.01 * 255 mm = 2.55 mm
    Since 2.55 mm is larger than 1 mm, the tolerance is ±2.55 mm.
5.  **Compare the difference to the tolerance:**
    The measured difference is -2 mm.
    Is -2.55 mm ≤ -2 mm ≤ +2.55 mm? Yes.

**Answer:** The measured range difference of -2 mm falls within the typical tolerance of ±2.55 mm. The machine passes this daily QA check.

## Worked Example 2.2.4: Synchrotron Beam Extraction Time Structure

**Problem:** A synchrotron accelerates protons to the desired energy over 1 second and then extracts the beam over 0.5 seconds. This cycle repeats. What is the duty cycle of the beam delivery?

**Background:** The duty cycle is the fraction of time the beam is actually being delivered or is available for treatment.

**Solution:**

1.  **Identify the beam extraction (delivery) time:** T_delivery = 0.5 seconds
2.  **Identify the total cycle time:** T_cycle = Acceleration Time + Extraction Time = 1 second + 0.5 seconds = 1.5 seconds
3.  **Calculate the duty cycle:**
    Duty Cycle = T_delivery / T_cycle
    Duty Cycle = 0.5 seconds / 1.5 seconds = 1/3 ≈ 0.333

**Answer:** The duty cycle of the beam delivery is approximately 33.3%. This means the beam is only available for treatment one-third of the time.
