# Worked Examples: Section 4.3 - Brachytherapy Planning

This document provides step-by-step worked examples for common calculations encountered in brachytherapy planning.

## Example 1: Basic TG-43 Dose Rate Calculation

*   **Objective:** Calculate the dose rate at a specific point near a single HDR Ir-192 source using the TG-43 formalism.
*   **Scenario:** An HDR plan uses an Ir-192 source (model mHDR-v2). We want to find the dose rate at point P located at distance $r = 3$ cm from the source center along the transverse axis ($θ = 90°$).
*   **Given Data (Hypothetical/Illustrative for mHDR-v2 source model):**
    *   Air Kerma Strength: $S_K = 40000$ U (or $40000\ µGy \cdot m^2 \cdot h^{-1}$)
    *   Dose Rate Constant: $Λ = 1.110\ cGy \cdot h^{-1} \cdot U^{-1}$
    *   Reference distance: $r_0 = 1$ cm
    *   Reference angle: $θ_0 = 90°$
    *   Geometry Function (point source approx.): $G_L(r, θ) = 1/r^2$
    *   Radial Dose Function at r=3 cm: $g_L(3\ cm) = 0.955$
    *   Anisotropy Function at θ=90°: $F(r, 90°) = 1.000$ (by definition for the transverse axis)
*   **TG-43 Formula (2D):**
    $$ \\\dot{D}(r, \theta) = S_K \times \Lambda \times \frac{G_L(r, \theta)}{G_L(r_0, \theta_0)} \times g_L(r) \times F(r, \theta) $$ 
*   **Step-by-Step Calculation:**
    1.  **Calculate Geometry Function Ratio:**
        *   $G_L(r, \theta) = G_L(3\ cm, 90°) = 1 / (3\ cm)^2 = 1/9\ cm^{-2}$
        *   $G_L(r_0, \theta_0) = G_L(1\ cm, 90°) = 1 / (1\ cm)^2 = 1\ cm^{-2}$
        *   Ratio: $\frac{G_L(3\ cm, 90°)}{G_L(1\ cm, 90°)} = \frac{1/9}{1} = 1/9$
    2.  **Gather other parameters at P(r=3 cm, θ=90°):**
        *   $S_K = 40000$ U
        *   $Λ = 1.110\ cGy \cdot h^{-1} \cdot U^{-1}$
        *   $g_L(3\ cm) = 0.955$
        *   $F(3\ cm, 90°) = 1.000$
    3.  **Plug values into the formula:**
        $$ \\\dot{D}(3\ cm, 90°) = (40000\ U) \times (1.110\ \frac{cGy}{h \cdot U}) \times (1/9) \times (0.955) \times (1.000) $$ 
    4.  **Calculate the result:**
        $$ \\\dot{D}(3\ cm, 90°) = 40000 \times 1.110 \times 0.1111... \times 0.955 \times 1.000 \\ \approx 4706\ cGy/h $$ 
*   **Solution:** The dose rate at point P (3 cm, 90°) is approximately 4706 cGy/hour.
*   **Clinical Relevance:** This type of calculation forms the basis of dose computation in brachytherapy TPS. Understanding the components helps in verifying plan calculations and appreciating dose fall-off.

## Example 2: BED and EQD2 Calculation for HDR GYN Brachytherapy

*   **Objective:** Compare the biological effectiveness of an HDR brachytherapy boost regimen combined with EBRT for both tumor control and late rectal toxicity.
*   **Scenario:** A patient with cervical cancer receives EBRT (45 Gy in 25 fractions, $d_{EBRT}=1.8$ Gy) followed by an HDR boost. The HDR plan delivers 28 Gy in 4 fractions ($d_{HDR}=7$ Gy) to the HR-CTV $D_{90}$. The rectal $D_{2cc}$ from the HDR plan is 5 Gy per fraction (total 20 Gy HDR).
*   **Given Data:**
    *   Tumor/HR-CTV $\alpha/\beta = 10$ Gy
    *   Rectum (late effect) $\alpha/\beta = 3$ Gy
    *   Reference fraction size for EQD2 = 2 Gy
*   **Formulas:**
    *   $BED = n \times d \times (1 + \frac{d}{\alpha/\beta})$
    *   $EQD2 = BED \times \frac{\alpha/\beta + 2}{\alpha/\beta + d_{ref}} = BED / (1 + \frac{2}{\alpha/\beta})$ (since $d_{ref}=2$ Gy)
    *   Total Effect = Effect$_{EBRT}$ + Effect$_{Brachy}$
*   **Step-by-Step Calculation (Tumor/HR-CTV, $\alpha/\beta = 10$ Gy):**
    1.  **BED from EBRT:**
        *   $n=25$, $d=1.8$ Gy
        *   $BED_{EBRT} = 25 \times 1.8 \times (1 + \frac{1.8}{10}) = 45 \times (1 + 0.18) = 45 \times 1.18 = 53.1$ Gy₁₀
    2.  **BED from HDR Boost (to $D_{90}$):**
        *   $n=4$, $d=7$ Gy
        *   $BED_{HDR} = 4 \times 7 \times (1 + \frac{7}{10}) = 28 \times (1 + 0.7) = 28 \times 1.7 = 47.6$ Gy₁₀
    3.  **Total BED (Tumor):**
        *   $BED_{Total} = BED_{EBRT} + BED_{HDR} = 53.1 + 47.6 = 100.7$ Gy₁₀
    4.  **Total EQD2 (Tumor):**
        *   $EQD2_{Total} = BED_{Total} / (1 + \frac{2}{10}) = 100.7 / (1 + 0.2) = 100.7 / 1.2 \approx 83.9$ Gy
*   **Step-by-Step Calculation (Rectal $D_{2cc}$, $\alpha/\beta = 3$ Gy):**
    1.  **BED from EBRT (assuming $D_{2cc}$ receives full EBRT dose):**
        *   $n=25$, $d=1.8$ Gy
        *   $BED_{EBRT} = 25 \times 1.8 \times (1 + \frac{1.8}{3}) = 45 \times (1 + 0.6) = 45 \times 1.6 = 72.0$ Gy₃
    2.  **BED from HDR Boost (to $D_{2cc}$):**
        *   $n=4$, $d=5$ Gy (dose per fraction to rectal $D_{2cc}$)
        *   $BED_{HDR} = 4 \times 5 \times (1 + \frac{5}{3}) = 20 \times (1 + 1.667) = 20 \times 2.667 \approx 53.3$ Gy₃
    3.  **Total BED (Rectum $D_{2cc}$):**
        *   $BED_{Total} = BED_{EBRT} + BED_{HDR} = 72.0 + 53.3 = 125.3$ Gy₃
    4.  **Total EQD2 (Rectum $D_{2cc}$):**
        *   $EQD2_{Total} = BED_{Total} / (1 + \frac{2}{3}) = 125.3 / (1 + 0.667) = 125.3 / 1.667 \approx 75.2$ Gy
*   **Solution & Interpretation:**
    *   The total EQD2 delivered to the HR-CTV $D_{90}$ is approximately 83.9 Gy, which meets the typical GEC-ESTRO goal of 85-90 Gy (it's slightly low in this example, might need plan adjustment).
    *   The total EQD2 delivered to the Rectal $D_{2cc}$ is approximately 75.2 Gy. This slightly exceeds the typical hard constraint of 75 Gy₃, indicating a potential risk of late rectal toxicity that should be carefully considered or mitigated if possible through replanning.
*   **Clinical Relevance:** BED and EQD2 calculations are essential for comparing different fractionation regimens, combining doses from different modalities (EBRT + Brachy), and assessing plans against established tolerance limits based on biological effectiveness.

## Example 3: HDR Dwell Time Calculation (Simple Case)

*   **Objective:** Determine the required dwell time at a single position to deliver a specific dose at a point.
*   **Scenario:** Using the same source and point P as in Example 1, we want to deliver a dose of 500 cGy to point P (3 cm, 90°) using a single dwell position.
*   **Given Data (from Example 1):**
    *   Dose rate at P from the source at the dwell position: $\\\\\dot{D}_P = 4706$ cGy/hour
    *   Desired Dose at P: $D_P = 500$ cGy
*   **Formula:**
    *   $Dose = Dose\ Rate \times Time$
    *   $Time = Dose / Dose\ Rate$
*   **Step-by-Step Calculation:**
    1.  **Ensure Units are Consistent:** Dose rate is in cGy/hour. Let's calculate time in hours first, then convert to seconds.
        *   $Time (hours) = \frac{500\ cGy}{4706\ cGy/hour} \approx 0.1062\ hours$
    2.  **Convert to Seconds:**
        *   $Time (seconds) = Time (hours) \times 3600\ seconds/hour$
        *   $Time (seconds) = 0.1062 \times 3600 \approx 382.4\ seconds$
*   **Solution:** A dwell time of approximately 382.4 seconds is required at this single position to deliver 500 cGy to point P.
*   **Clinical Relevance:** In HDR planning, the TPS calculates the dose rate contribution from each potential dwell position to multiple calculation points (target points, OAR points). It then uses optimization algorithms to determine the optimal set of dwell times at various positions to achieve the desired overall dose distribution according to the prescription and constraints. This example shows the fundamental relationship for a single point and position.


