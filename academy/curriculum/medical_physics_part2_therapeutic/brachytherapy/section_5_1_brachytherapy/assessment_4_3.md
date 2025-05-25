# Assessment: Section 4.3 - Brachytherapy Planning

This assessment covers the key concepts, calculations, and clinical applications of brachytherapy planning.

## Part 1: Multiple Choice Questions (Select the best answer)

1.  The primary advantage of brachytherapy over EBRT for certain localized tumors is:
    a) Lower total dose delivered
    b) Non-invasive nature
    c) Steeper dose gradient and potentially better OAR sparing
d) Less dependence on accurate imaging

2.  Air Kerma Strength ($S_K$) is the standard specification for brachytherapy sources. Its units are typically:
    a) Curie (Ci)
    b) $cGy \cdot h^{-1}$
    c) $µGy \cdot m^2 \cdot h^{-1}$ (or U)
d) $MeV \cdot cm^2 / g$

3.  Which component of the TG-43 formalism accounts for dose variations due to absorption and scatter in the medium relative to a $1/r^2$ fall-off?
    a) Dose Rate Constant (Λ)
    b) Geometry Function ($G_L(r, \theta)$)
    c) Radial Dose Function ($g_L(r)$)
d) Anisotropy Function ($F(r, \theta)$)

4.  Remote afterloading is a technique primarily used in:
    a) LDR permanent seed implants
    b) LDR temporary implants
    c) HDR and PDR brachytherapy
d) Electronic Brachytherapy

5.  For HDR GYN brachytherapy planning following GEC-ESTRO guidelines, the dose prescription is typically based on covering which volume?
    a) Point A
    b) The entire pelvic CTV
    c) The High-Risk CTV (HR-CTV) $D_{90}$
d) The bladder $D_{2cc}$

6.  Which of the following isotopes has the shortest half-life and is commonly used for LDR permanent prostate implants?
    a) Ir-192
    b) I-125
    c) Pd-103
d) Cs-137

7.  Calculating EQD2 is important in brachytherapy primarily for:
    a) Determining the source strength needed
    b) Comparing the biological effectiveness of different fractionation schedules or modalities
    c) Verifying the accuracy of the TG-43 calculation
d) Optimizing dwell times in HDR planning

8.  Model-Based Dose Calculation Algorithms (MBDCA, TG-186) aim to improve upon TG-43 by:
    a) Simplifying the source calibration process
    b) Using Monte Carlo simulations exclusively
    c) Explicitly accounting for tissue heterogeneities and applicator effects
d) Providing a faster calculation time

## Part 2: Short Answer Questions

9.  Briefly explain the difference between LDR, HDR, and PDR brachytherapy in terms of dose rate and typical treatment duration.
10. List three key QA checks that should be performed on an HDR remote afterloader unit.
11. What is the purpose of the anisotropy function $F(r, \theta)$ in the TG-43 formalism?
12. Describe the concept of inverse planning (e.g., IPSA) in HDR brachytherapy. What is its goal?

## Part 3: Calculation Problems

13. **TG-43 Calculation:** A single Ir-192 source (model XYZ) has $S_K = 30000$ U and $Λ = 1.115\ cGy \cdot h^{-1} \cdot U^{-1}$. Using the point source approximation ($G_L(r, \theta) = 1/r^2$), calculate the initial dose rate at a point P located 2 cm away along the transverse axis (θ=90°). Assume $g_L(2\ cm) = 0.980$ and $F(2\ cm, 90°) = 1.000$. Show your work.

14. **BED/EQD2 Calculation:** A patient receives an LDR prostate implant with I-125 seeds. The post-implant dosimetry shows the prostate $D_{90}$ is 145 Gy (total dose delivered over many half-lives). Assuming an $\alpha/\beta$ ratio of 1.5 Gy for prostate cancer, calculate the BED delivered to the $D_{90}$. (Hint: For a permanent implant decaying exponentially with decay constant λ and half-life $T_{1/2}$, the BED can be approximated using the initial dose rate $\\\dot{D}_0$ and repair constant µ, or more simply for total dose D: $BED = D \times (1 + \frac{g \cdot D}{(\alpha/\beta) \cdot (µ+\lambda)})$ where g relates to repair during delivery. A simpler approximation often used considers the effective treatment time. However, for comparing total doses, often the total dose is used in a modified BED formula or simply compared directly if $\alpha/\beta$ is very low. For this problem, let's use a simplified approach often seen in comparisons: Calculate the EQD2 assuming the 145 Gy was delivered in 2 Gy fractions, acknowledging this is a simplification for LDR. $EQD2 = D \times \frac{\alpha/\beta + d_{LDR}}{\alpha/\beta + 2}$, where $d_{LDR}$ is the dose per fraction if it were fractionated. A better approach uses the Lea-Catcheside factor or considers the initial dose rate. Let's rephrase: Calculate the EQD2 corresponding to a total LDR dose of 145 Gy, assuming $\alpha/\beta = 1.5$ Gy and comparing to a 2 Gy/fraction standard. Use the formula $EQD2 = D \times \frac{\alpha/\beta + d_{ref}}{\alpha/\beta + d_{eff}}$, where $d_{eff}$ is complex for LDR. **Alternative approach:** Calculate the BED assuming the dose is delivered at a constant effective rate over a simplified effective time. **Let's simplify for assessment:** Calculate the BED for an equivalent HDR regimen delivering the same biological effect. If an HDR regimen delivers $EQD2 = 60$ Gy (in 2 Gy fractions) to the rectum ($\\alpha/\\beta = 3$ Gy), what is the corresponding BED? $BED = EQD2 \times (1 + \frac{2}{\alpha/\beta})$. Calculate this BED.

    **(Revised Problem 14):** An HDR treatment delivers 6 Gy per fraction to a tumor with $\alpha/\beta = 10$ Gy. Calculate the BED for a single 6 Gy fraction. If 5 such fractions are given, what is the total BED?

15. **HDR Dwell Time:** If the dose rate at a target point from a single dwell position is 3000 cGy/hour, how long (in seconds) should the source dwell at that position to deliver 150 cGy to that point?

## Part 4: Clinical Application

16. Describe the typical steps involved in the physics planning process for an HDR intracavitary GYN brachytherapy case, starting from the CT simulation with the applicator in place to the final plan approval.

---

## Solutions

**Part 1:**
1.  c) Steeper dose gradient and potentially better OAR sparing
2.  c) $µGy \cdot m^2 \cdot h^{-1}$ (or U)
3.  c) Radial Dose Function ($g_L(r)$)
4.  c) HDR and PDR brachytherapy
5.  c) The High-Risk CTV (HR-CTV) $D_{90}$
6.  c) Pd-103 (Half-life ~17 days vs ~60 days for I-125)
7.  b) Comparing the biological effectiveness of different fractionation schedules or modalities
8.  c) Explicitly accounting for tissue heterogeneities and applicator effects

**Part 2:**
9.  *LDR:* Low Dose Rate (0.4-2 Gy/hr), continuous delivery over days. *HDR:* High Dose Rate (>12 Gy/hr), delivery in minutes per fraction, typically multiple fractions. *PDR:* Pulsed Dose Rate, dose delivered in short pulses (e.g., hourly) using an HDR unit, mimicking LDR biology over a similar total time.
10. Timer accuracy/linearity/end effect; Source positional accuracy (spatial); Safety interlocks (emergency stops, door interlocks, battery backup); Source calibration/constancy check (periodic).
11. $F(r, \theta)$ accounts for the variation in dose distribution around the source at different angles ($θ$) compared to the transverse axis, due to factors like source self-filtration and oblique filtration through the capsule. It corrects for the non-uniform emission of dose.
12. Inverse planning automatically determines the optimal source dwell times (and sometimes positions) to best achieve the prescribed target dose coverage while respecting dose constraints defined for OARs, based on user-input objectives.

**Part 3:**
13. $\\\\\dot{D}(2\ cm, 90°) = S_K \times \Lambda \times \frac{G_L(2, 90)}{G_L(1, 90)} \times g_L(2) \times F(2, 90)$
    $G_L(2, 90) = 1/2^2 = 1/4$; $G_L(1, 90) = 1/1^2 = 1$. Ratio = 1/4.
    $\\\\\dot{D} = (30000\ U) \times (1.115\ \frac{cGy}{h \cdot U}) \times (1/4) \times (0.980) \times (1.000)$
    $\\\\\dot{D} = 30000 \times 1.115 \times 0.25 \times 0.980 \approx 8195$ cGy/hour.

14. (Revised Problem) BED for single 6 Gy fraction ($\\alpha/\\beta = 10$ Gy):
    $BED = d \times (1 + \frac{d}{\alpha/\beta}) = 6 \times (1 + \frac{6}{10}) = 6 \times (1 + 0.6) = 6 \times 1.6 = 9.6$ Gy₁₀.
    Total BED for 5 fractions = $5 \times 9.6 = 48.0$ Gy₁₀.

15. $Time = Dose / Dose\ Rate = 150\ cGy / (3000\ cGy/hour)$
    $Time = 0.05$ hours
    $Time (seconds) = 0.05\ hours \times 3600\ seconds/hour = 180$ seconds.

**Part 4:**
16. 1. **Image Import & Fusion:** Import CT sim images (with applicator) into TPS. Fuse with prior diagnostic imaging (e.g., MRI) if used for contouring. 2. **Applicator Reconstruction:** Digitize applicator channels accurately on CT images. 3. **Contouring:** Define HR-CTV, IR-CTV (if applicable), Bladder, Rectum, Sigmoid, Bowel based on GEC-ESTRO guidelines. 4. **Dose Prescription:** Define dose goals for target ($D_{90}$) and constraints for OARs ($D_{2cc}$). 5. **Plan Optimization:** Define dwell positions. Use inverse planning (e.g., IPSA) or graphical/manual optimization to adjust dwell times. 6. **Dose Calculation:** Calculate 3D dose distribution using TG-43 or MBDCA. 7. **Plan Evaluation:** Analyze isodose lines and DVHs. Verify target coverage and OAR doses against prescription/constraints. Calculate EQD2 totals. 8. **Physics Review:** Independent check of plan parameters, calculations, and objectives. 9. **Plan Approval:** Review and approval by radiation oncologist and physicist. 10. **Plan Export:** Transfer approved plan data securely to the HDR afterloader unit.


