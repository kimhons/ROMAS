# Deep Dive: AAPM TG-119 - IMRT Commissioning: Tests, Planning, Measurement, and Analysis (Instructions Document)

**Source:** TG-119 IMRT Commissioning Tests: Instructions for Planning, Measurement, and Analysis (Version 10/21/2009)

**Disclaimer:** This deep dive is based primarily on the *Instructions* document accompanying the main TG-119 report. Access to the full report (Ezzell et al., Med Phys 36(11), 2009) was limited, so some context or detailed results might be missing. The Instructions document focuses on the practical implementation of the commissioning tests.

## 1. Introduction and Purpose

TG-119 aimed to provide a standardized methodology for commissioning Intensity-Modulated Radiation Therapy (IMRT) planning and delivery systems. Recognizing the complexity of IMRT, the task group designed a set of standardized planning and measurement exercises that clinics could perform to test the **overall accuracy of their IMRT process**, from planning through delivery and verification.

**Key Goals:**

*   Define standard IMRT planning "problems" (structure sets and dose goals).
*   Specify beam arrangements and planning parameters.
*   Define measurement procedures (ion chamber points, planar dose).
*   Standardize data analysis methods (point dose ratios, Gamma analysis).
*   Provide baseline results ("confidence limits") from multiple institutions against which clinics could compare their own performance.

**Important Distinction:** TG-119 tests are designed as **end-to-end system checks**. They do not isolate specific error sources (e.g., calculation algorithm vs. delivery accuracy vs. measurement uncertainty) but rather assess the cumulative accuracy of the entire clinical IMRT workflow.

## 2. General Description of the Tests

*   **Structure Sets:** The task group provided downloadable CT datasets and RT Structure Sets for several test cases (MultiTarget, Prostate, Head/Neck, C-Shape). Users could either plan directly on these or transfer/recreate the structures on their local phantom CT scans.
*   **Phantom:** A water-equivalent slab phantom allowing for both ion chamber point measurements and planar film measurements (typically on coronal planes) at various depths.
*   **Energy:** Tests were standardized for 6 MV photons.
*   **Calculation Grid:** Recommended 2 mm or finer.
*   **Dose Goals:** Specific dose/volume objectives were provided for each target and OAR in each test case to ensure comparable plan complexity across institutions.
*   **Clinical Parameters:** Users were instructed to use IMRT planning parameters typical for their clinical practice (e.g., intensity levels, smoothing, minimum segment size/MU).

*Street Wisdom:* The goal isn't necessarily to create the *best possible* plan for the TG-119 structures, but rather to create a plan that meets the specified goals using your clinic's standard techniques and parameters. This makes the subsequent measurements a realistic test of your clinical process.

## 3. Measurement Procedures

TG-119 specified three types of measurements:

1.  **Ion Chamber Point Doses (Composite Plan):**
    *   Measure dose at specific points (defined for each test case, usually in high-dose and low-dose/gradient regions) using a small-volume ion chamber (e.g., 0.125 cc scanning chamber).
    *   Measurements are performed for the *composite* plan (all beams delivered at their respective gantry angles).
    *   **Calibration/Normalization (Test P1):** A crucial preliminary step involves irradiating the phantom with a simple AP/PA 10x10 cm² field to a known dose (e.g., 200 cGy) and measuring the chamber reading. This establishes a **reading-to-dose conversion factor** specific to that day's setup, minimizing effects of linac output variations and phantom differences from water.
    *   Calculations should be done consistently (heterogeneity corrections on or off, preferably on).
    *   Reported dose should ideally be the mean dose over the chamber's sensitive volume.

2.  **Planar Dose Distributions (Composite Plan):**
    *   Measure 2D dose distributions on specified coronal planes using film (radiographic or radiochromic) or potentially other 2D detectors.
    *   Film response should be normalized to the ion chamber measurement on the same plane (using the factor from P1 or a dedicated point on the film plane).
    *   Emphasis on using best practices for film dosimetry to minimize uncertainty.

3.  **Planar Dose Distributions (Field-by-Field):**
    *   Measure 2D dose distributions for *each individual IMRT field* delivered perpendicularly to a detector array (diode, chamber), EPID, or film.
    *   This tests the delivery accuracy of individual beams, often compared to TPS calculations on a plane perpendicular to the beam axis.

*Street Wisdom:* The preliminary test P1 (AP/PA 10x10) is fundamental. It links your relative measurements (chamber readings, film OD) to absolute dose under simple, well-understood conditions, providing the anchor for evaluating the complex IMRT deliveries.

## 4. Data Analysis

Standardized analysis was key for comparing results to the TG-119 baseline.

*   **Point Doses (Ion Chamber):**
    *   Comparison metric: **(Measured Dose - Planned Dose) / Prescribed Dose**
    *   Note: The denominator is the *prescribed* dose for the plan (e.g., 180-200 cGy/fraction equivalent), not the planned dose at the specific point. This normalizes the deviation relative to the overall plan goal.
*   **Planar Doses (Film/Arrays/EPID):**
    *   **Gamma Analysis:** The primary tool for comparing measured and calculated 2D distributions.
    *   **Criteria:** Standardized at **3% dose difference** (relative to a normalization point, see below) and **3 mm distance-to-agreement (DTA)**.
    *   **Passing Metric:** Percentage of points within a defined Region of Interest (ROI) where the Gamma index ($\\gamma$) is $\\le 1$.
    *   **ROI Definition:** Exclude low-dose regions, typically using a threshold of 10% of the maximum dose on the plane.
    *   **Gamma Implementation Details:** The Instructions note that Gamma results depend heavily on implementation details. For comparison with TG-119, specific parameters were used (based on a common commercial system at the time):
        *   Absolute Dose comparison (no global renormalization).
        *   Dose difference denominator: Value of the *maximum measurement point* on the plane (often referred to as % difference relative to max dose or global % difference).
        *   Other settings: "Van Dyk On" (likely referring to interpolation or search method), "Apply Measurement Uncertainty On" (if applicable).

*Street Wisdom:* Understanding your Gamma analysis software is crucial. Is the % dose difference calculated relative to the local point dose, the global maximum dose, or the prescription dose? TG-119 used % difference relative to the maximum measured dose for planar analysis. Using different criteria will yield different passing rates and make comparisons difficult.

## 5. Confidence Limits

TG-119 introduced the concept of "Confidence Limits" (CL) to statistically summarize the agreement found across the participating institutions.

*   **Point Doses:** $CL = |mean| + 1.96 \times \sigma$
    *   Where 'mean' is the average of the (Meas - Plan) / Rx ratios for a set of points (e.g., all high-dose points), and $\sigma$ is the standard deviation.
    *   Interpretation: For a large number of measurements, 95% are expected to have a deviation ratio less than or equal to the CL.
*   **Gamma Analysis:** $CL = (100 - mean) + 1.96 \times \sigma$
    *   Where 'mean' is the average passing rate (%) for a set of planar measurements, and $\sigma$ is the standard deviation.
    *   Interpretation: For a large number of planar analyses, 95% are expected to have a passing rate greater than or equal to $(100 - CL)\%$.

**Recommendation:** Clinics should perform the TG-119 tests, calculate their *local* confidence limits using the same methodology, and compare them to the baseline CLs published in the main TG-119 report. If local CLs are significantly worse (larger for point doses, larger for Gamma), it may indicate issues in the IMRT planning or delivery process that warrant investigation.

## 6. Preliminary Tests (P1, P2)

*   **P1 (AP/PA 10x10):** As described above, used to establish the dose/reading conversion factor. Agreement is not assessed here, but Gamma analysis of the planar measurements provides a baseline for the measurement system under simple conditions.
*   **P2 (Bands):** Uses AP/PA fields with varying jaw settings (or MLC segments) to create bands of different dose levels (e.g., ~40 cGy to ~200 cGy). This tests the system's ability to deliver and measure different dose levels accurately in non-modulated fields and provides low-gradient regions to check film dosimetry linearity/accuracy.

## 7. Commissioning Tests (C1-C4)

These are the core IMRT test cases, increasing in complexity.

*   **C1 (MultiTarget):** Three stacked cylindrical targets with different dose prescriptions. Tests ability to deliver different doses to adjacent volumes.
    *   Beams: 7 fields, 50° intervals.
    *   Measurements: Chamber points at isocenter (high dose), ±4 cm superior/inferior (lower doses); Film at isocenter plane.
*   **C2 (Mock Prostate):** Realistic prostate PTV with abutting rectum OAR.
    *   Beams: 7 fields, 50° intervals.
    *   Measurements: Chamber points at isocenter (high dose) and 2.5 cm posterior (low dose/gradient); Film at isocenter plane and 2.5 cm posterior plane.
*   **C3 (Mock Head/Neck):** Complex PTV wrapping around spinal cord and parotid OARs.
    *   Beams: 9 fields, 40° intervals.
    *   Measurements: Chamber points at isocenter (high dose) and 4 cm posterior (low dose/gradient near cord); Film at isocenter plane (includes parotids) and 4 cm posterior plane.
*   **C4 (C-Shape):** C-shaped PTV surrounding a central cylindrical avoidance structure (core).
    *   Two versions: "Easy" (core dose < 50% of PTV dose) and "Hard" (core dose < 20% of PTV dose). The "Hard" version requires very steep dose gradients.
    *   Beams: 4 fields (0°, 90°, 180°, 270°).
    *   Measurements: Chamber points anterior (high dose) and center (low dose); Film at isocenter plane.

## 8. Conclusion and Relevance

TG-119 provides a standardized, practical, and widely adopted methodology for the end-to-end commissioning and ongoing QA of IMRT systems. By performing these tests and comparing results to the established confidence limits, clinics can gain valuable insights into the accuracy of their IMRT process and identify potential areas for improvement. While technology continues to evolve (VMAT, SBRT, new algorithms), the principles and many of the test structures remain relevant for verifying the complex interplay between treatment planning and dose delivery.


