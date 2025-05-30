# Multiple Choice Questions (MCQs): Section 4.3 - Brachytherapy Planning

This document contains ABR-style multiple choice questions covering key concepts in brachytherapy planning. Detailed explanations are provided for each answer.

**Question 1:**
According to the AAPM TG-43U1 formalism, the dose rate constant (Λ) for a brachytherapy source relates which two quantities?

a) Air Kerma Strength ($S_K$) and Dose Rate in Water at 1 meter
b) Activity (Ci) and Dose Rate in Water at 1 cm
c) Air Kerma Strength ($S_K$) and Dose Rate in Water at the reference point (1 cm, 90°)
d) Activity (Ci) and Air Kerma Rate at 1 meter

**Answer: c) Air Kerma Strength ($S_K$) and Dose Rate in Water at the reference point (1 cm, 90°)**
*   **Explanation:** The dose rate constant, Λ, is defined as the ratio of the dose rate in water at the reference point ($r_0$=1 cm, $θ_0$=90°) to the Air Kerma Strength ($S_K$). It essentially converts the source strength specification ($S_K$) into the dose rate delivered in the medium under reference conditions. $\Lambda = \frac{\\\\\dot{D}(r_0, \theta_0)}{S_K}$. Options a, b, and d use incorrect distances, quantities (Activity), or locations.

**Question 2:**
A prostate LDR seed implant is planned using I-125 seeds. Which of the following $\alpha/\beta$ ratios would be most appropriate to use when calculating the Biologically Effective Dose (BED) for the prostate tumor itself?

a) 1.5 Gy
b) 3 Gy
c) 10 Gy
d) 20 Gy

**Answer: a) 1.5 Gy**
*   **Explanation:** Prostate cancer is generally considered to have a low $\alpha/\beta$ ratio, similar to late-responding normal tissues, typically estimated to be around 1.5 Gy to 3 Gy. This low ratio implies sensitivity to higher doses per fraction, providing a rationale for hypofractionation or LDR implants. 3 Gy is more typical for late-responding normal tissues like the rectum, while 10 Gy is characteristic of most other tumors and early-responding tissues. 20 Gy is unusually high.

**Question 3:**
In HDR brachytherapy planning for cervical cancer using a tandem and ring applicator, which dose point or volume parameter is most commonly used for evaluating bladder dose according to GEC-ESTRO guidelines?

a) Maximum Point Dose
b) $D_{90}$
c) $D_{2cc}$
d) Mean Dose

**Answer: c) $D_{2cc}$**
*   **Explanation:** The GEC-ESTRO guidelines recommend reporting the maximum dose received by the most irradiated 2 cubic centimeters ($D_{2cc}$) for organs at risk like the bladder and rectum. This parameter is considered more robust and clinically relevant than a single maximum point dose, which can be sensitive to calculation noise or small volumes, and more indicative of potential complications than mean dose or $D_{90}$ (which is a target parameter).

**Question 4:**
Which radioactive isotope is most commonly used for HDR remote afterloading brachytherapy?

a) Iodine-125 (I-125)
b) Palladium-103 (Pd-103)
c) Cesium-137 (Cs-137)
d) Iridium-192 (Ir-192)

**Answer: d) Iridium-192 (Ir-192)**
*   **Explanation:** Ir-192 is the workhorse isotope for HDR brachytherapy due to its suitable characteristics: a reasonably high specific activity allowing for small source size, appropriate gamma energy (~380 keV) for tissue penetration, and a half-life (73.8 days) that is convenient for source replacement schedules in busy clinics. I-125 and Pd-103 are primarily used for LDR permanent implants. Cs-137 was used for LDR but is largely phased out for HDR.

**Question 5:**
The geometry function, $G_L(r, \theta)$, in the TG-43 formalism primarily accounts for:

a) Attenuation and scatter within the medium
b) Anisotropy of dose emission from the source capsule
c) The inverse square law fall-off, modified for source geometry
d) The conversion from Air Kerma Strength to dose rate in water

**Answer: c) The inverse square law fall-off, modified for source geometry**
*   **Explanation:** The geometry function describes how the dose rate changes purely based on the spatial distribution of radioactivity within the source (point vs. line vs. complex shape) and the distance/angle to the calculation point, assuming radiation travels in straight lines without interaction (i.e., inverse square law effects). Attenuation and scatter are handled by the radial dose function ($g_L(r)$), anisotropy by the anisotropy function ($F(r, \theta)$), and the conversion factor is the dose rate constant (Λ).

**Question 6:**
A patient receives HDR brachytherapy boost for breast cancer using interstitial catheters. The plan prescribes 10 Gy in 2 fractions. Which parameter is critical for assessing dose homogeneity within the CTV Boost?

a) $D_{90}$
b) $V_{100}$
c) $V_{150}$ / $V_{200}$
d) Dose Homogeneity Index (DHI)

**Answer: d) Dose Homogeneity Index (DHI)**
*   **Explanation:** While $D_{90}$ and $V_{100}$ assess target coverage, and $V_{150}$/$V_{200}$ assess high-dose volumes (hot spots), the Dose Homogeneity Index (DHI) specifically quantifies the uniformity of the dose distribution within the target volume. A common definition is $DHI = (V_{100} - V_{150}) / V_{100}$. A value closer to 1 indicates a more homogeneous dose distribution.

**Question 7:**
Model-Based Dose Calculation Algorithms (MBDCA, TG-186) offer potential advantages over TG-43 primarily by:

a) Using a simpler mathematical formalism
b) Accounting for tissue heterogeneities and applicator attenuation
c) Requiring less complex commissioning QA
d) Being independent of source strength calibration

**Answer: b) Accounting for tissue heterogeneities and applicator attenuation**
*   **Explanation:** The main limitation of TG-43 is its assumption of an infinite, homogeneous water medium. MBDCA algorithms (like Acuros BV or collapsed cone) explicitly model radiation transport through the patient-specific anatomy, including variations in tissue density (bone, air, lung) and the effects of shielding or scatter from applicators, potentially leading to more accurate dose calculations in complex situations. MBDCA formalism is more complex, requires more extensive QA, and still relies on accurate source strength calibration.

**Question 8:**
During an LDR prostate seed implant using I-125, the physicist performs post-implant dosimetry based on a CT scan taken 1 day after the procedure. The calculated prostate $D_{90}$ is significantly lower than the prescribed 145 Gy. Which factor is LEAST likely to be the primary cause?

a) Significant prostate edema present on the post-implant CT
b) Inaccurate identification/localization of seeds on the CT scan
c) Migration of several seeds outside the prostate gland
d) Using the incorrect Dose Rate Constant (Λ) for the I-125 seed model

**Answer: d) Using the incorrect Dose Rate Constant (Λ) for the I-125 seed model**
*   **Explanation:** While using incorrect dosimetry data (like Λ) would cause calculation errors, it's less likely to be the *primary* cause of a *significant* drop in $D_{90}$ compared to the physical and geometric factors. Prostate edema (swelling) post-implant increases the prostate volume, effectively diluting the dose and lowering $D_{90}$. Inaccurate seed localization (missing seeds or misplacing them in the TPS) directly impacts the calculated dose distribution. Seed migration outside the target volume clearly reduces the dose delivered to the prostate. These geometric and volumetric changes (a, b, c) are common challenges in post-implant dosimetry and often have a larger impact on target coverage metrics like $D_{90}$ than minor errors in dosimetry parameters.

**Question 9:**
What is the primary radiobiological advantage of using LDR or PDR brachytherapy compared to HDR brachytherapy for tumors with potentially low $\alpha/\beta$ ratios or when considering late normal tissue effects?

a) Higher dose conformity achievable
b) Allows for more significant sublethal damage repair during treatment
c) Shorter overall treatment time
d) Reduced need for source calibration

**Answer: b) Allows for more significant sublethal damage repair during treatment**
*   **Explanation:** LDR and PDR deliver the dose over an extended period (hours to days). This prolonged delivery allows for continuous repair of sublethal damage in both tumor and normal tissues during the treatment. For tissues with a significant repair capacity (often characterized by a low $\alpha/\beta$ ratio, like late-responding normal tissues or some tumors like prostate), this repair during LDR/PDR can lead to a greater sparing effect compared to HDR, where the dose is delivered too quickly for significant intra-fraction repair. Dose conformity depends on technique, not inherently dose rate. HDR has a shorter treatment time per fraction. Source calibration is essential for all techniques.

**Question 10:**
Which QA procedure is specifically critical for verifying the operational safety and accuracy of an HDR remote afterloader unit?

a) Source $S_K$ calibration traceable to NIST
b) Applicator integrity check
c) Treatment planning system dose calculation verification
d) Source positional accuracy and timer linearity/end effect checks

**Answer: d) Source positional accuracy and timer linearity/end effect checks**
*   **Explanation:** While all listed QA procedures are important for brachytherapy overall, checks of the HDR unit's ability to accurately position the source at the programmed dwell locations and deliver dose for the correct amount of time (including timer linearity and accounting for transit dose/end effect) are fundamental to the safe and accurate operation of the remote afterloader itself (as recommended by TG-59). Source calibration (a) is crucial but usually done periodically or upon source change. Applicator checks (b) relate to the patient interface. TPS checks (c) verify the planning software.


