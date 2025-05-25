**Worked Example 1: GM Counter Dead Time Correction**

*Problem:* A GM survey meter with a known dead time (τ) of 150 microseconds (1.5 x 10⁻⁴ seconds) measures a count rate (n_measured) of 5,000 counts per minute (cpm) in a continuous radiation field. Estimate the true count rate (n_true).

*Solution:*
1.  Convert the measured count rate to counts per second (cps):
    n_measured (cps) = 5000 cpm / 60 s/min = 83.33 cps
2.  Use the formula for dead time correction (for non-paralyzable systems, a common approximation for GM counters):
    n_true = n_measured / (1 - n_measured * τ)
3.  Substitute the values:
    n_true = 83.33 cps / (1 - 83.33 cps * 1.5 x 10⁻⁴ s)
    n_true = 83.33 cps / (1 - 0.0125)
    n_true = 83.33 cps / 0.9875
    n_true ≈ 84.38 cps
4.  Convert the true count rate back to cpm:
    n_true (cpm) = 84.38 cps * 60 s/min ≈ 5063 cpm

*Conclusion:* The true count rate is approximately 5063 cpm, slightly higher than the measured rate due to counts lost during the dead time.

**Worked Example 2: Evaluating a Source Check Reading**

*Problem:* An ion chamber survey meter was calibrated, and the expected reading for its check source (Cs-137) in a specific geometry was established as 1.50 mR/hr. The department's policy requires the daily source check reading to be within +/- 10% of this expected value. Today's reading is 1.38 mR/hr. Is the instrument operating within acceptable limits?

*Solution:*
1.  Calculate the acceptable range:
    Lower Limit = Expected Reading - (10% of Expected Reading)
    Lower Limit = 1.50 mR/hr - (0.10 * 1.50 mR/hr) = 1.50 mR/hr - 0.15 mR/hr = 1.35 mR/hr
    Upper Limit = Expected Reading + (10% of Expected Reading)
    Upper Limit = 1.50 mR/hr + (0.10 * 1.50 mR/hr) = 1.50 mR/hr + 0.15 mR/hr = 1.65 mR/hr
2.  Compare the measured reading to the acceptable range:
    Measured Reading = 1.38 mR/hr
    Acceptable Range = 1.35 mR/hr to 1.65 mR/hr
3.  Since 1.38 mR/hr is within the range [1.35, 1.65] mR/hr, the instrument passes the source check.

*Conclusion:* The survey meter's reading is within the acceptable +/- 10% tolerance, and it can be used for surveys.

**Worked Example 3: Applying Energy Dependence Correction**

*Problem:* A survey meter calibrated using Cs-137 (662 keV) reads 5.0 mR/hr when measuring radiation from an I-125 source (approx. 30 keV photons). The manufacturer's data indicates the meter has an energy correction factor (ECF) of 1.8 for I-125 relative to Cs-137 (meaning it under-responds at I-125 energies). Estimate the true exposure rate.

*Solution:*
1.  The energy correction factor (ECF) relates the true exposure rate to the measured exposure rate:
    ECF = True Exposure Rate / Measured Exposure Rate
2.  Rearrange to solve for the True Exposure Rate:
    True Exposure Rate = Measured Exposure Rate * ECF
3.  Substitute the values:
    True Exposure Rate = 5.0 mR/hr * 1.8
    True Exposure Rate = 9.0 mR/hr

*Conclusion:* Due to the meter's under-response at low energies, the true exposure rate from the I-125 source is estimated to be 9.0 mR/hr, significantly higher than the direct reading.

**Worked Example 4: Inverse Square Law Calculation**

*Problem:* An ion chamber survey meter measures an exposure rate of 100 mR/hr at a distance of 30 cm from a small brachytherapy source (treat as a point source). Assuming the inverse square law applies, what is the expected exposure rate at a distance of 90 cm?

*Solution:*
1.  The inverse square law states that intensity (I) is inversely proportional to the square of the distance (d) from the source: I₁ * d₁² = I₂ * d₂²
2.  Identify the knowns and unknown:
    I₁ = 100 mR/hr
    d₁ = 30 cm
    d₂ = 90 cm
    I₂ = ?
3.  Rearrange the formula to solve for I₂:
    I₂ = I₁ * (d₁² / d₂²)
    I₂ = I₁ * (d₁ / d₂)²
4.  Substitute the values:
    I₂ = 100 mR/hr * (30 cm / 90 cm)²
    I₂ = 100 mR/hr * (1/3)²
    I₂ = 100 mR/hr * (1/9)
    I₂ ≈ 11.1 mR/hr

*Conclusion:* The expected exposure rate at 90 cm is approximately 11.1 mR/hr.

**Worked Example 5: Estimating Surface Contamination Activity**

*Problem:* A pancake GM probe measures 1200 counts per minute (cpm) net (background subtracted) when held 1 cm above a contaminated surface. The probe has a window area of 15 cm² and a calibrated efficiency of 15% (0.15 cpm/dpm) for the beta emitter involved (e.g., P-32) in this geometry. Estimate the surface activity concentration in Bq/cm².

*Solution:*
1.  Calculate the total activity detected in disintegrations per minute (dpm):
    Activity (dpm) = Net Counts (cpm) / Efficiency
    Activity (dpm) = 1200 cpm / 0.15
    Activity (dpm) = 8000 dpm
2.  Calculate the activity concentration in dpm/cm²:
    Activity Concentration (dpm/cm²) = Total Activity (dpm) / Probe Area (cm²)
    Activity Concentration (dpm/cm²) = 8000 dpm / 15 cm²
    Activity Concentration (dpm/cm²) ≈ 533.3 dpm/cm²
3.  Convert dpm/cm² to Bq/cm² (1 Bq = 60 dpm):
    Activity Concentration (Bq/cm²) = Activity Concentration (dpm/cm²) / 60
    Activity Concentration (Bq/cm²) = 533.3 dpm/cm² / 60 dpm/Bq
    Activity Concentration (Bq/cm²) ≈ 8.89 Bq/cm²

*Conclusion:* The estimated surface activity concentration is approximately 8.89 Bq/cm².
