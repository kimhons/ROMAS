# Section 4.4: Deep Dive - AAPM TG-116: An Exposure Indicator for Digital Radiography

**Reference:** Shepard, S. J., Wang, J., Flynn, M., Gingold, E., Goldman, L., Krugh, K., ... & Willis, C. E. (2009). An exposure indicator for digital radiography. Report of AAPM Task Group 116. *AAPM Report No. 116*.

**Note:** This Task Group report focuses on standardizing exposure indicators for *digital radiography (DR)*, a topic typically associated with diagnostic imaging rather than therapeutic physics or treatment planning system QA. However, as requested, this summary is based on the provided document.

## 1. Introduction: The Problem with Digital Radiography Exposure

Digital radiography (DR) systems (including CR and direct DR) have a much wider dynamic range than traditional screen-film systems. This means they can produce images with acceptable contrast over a very broad range of detector exposures.

- **Screen-Film:** Image brightness/density is directly linked to exposure. Over/underexposure is visually obvious.
- **Digital Radiography:** Image brightness and contrast are primarily determined by post-processing algorithms, largely independent of the initial detector exposure. Underexposure leads to increased image noise, while overexposure increases patient dose without necessarily improving (and sometimes degrading) image quality, often without obvious visual cues.

This decoupling leads to "exposure creep" – a tendency for exposure levels (and thus patient dose) to gradually increase over time as technologists aim to avoid noisy (underexposed) images, and radiologists may not complain about slightly overexposed, less noisy images.

TG-116 was charged with recommending a standardized method to provide feedback to operators about the adequacy of detector exposure for every image acquisition.

## 2. Key Concepts and Recommendations

**2.1. Avoiding "Speed Class":**
- The report strongly recommends **avoiding** the concept of "speed class" for DR systems. Speed class is defined based on achieving a specific optical density on film, which is irrelevant in DR. Using this term creates confusion and scientific inaccuracies.

**2.2. Standardized Exposure Indicator:**
- The core recommendation is for a standardized **Exposure Indicator (EI)** that reflects the incident radiation exposure on the detector.
- This EI should be vendor-independent and consistently related to the actual detector exposure.

**2.3. Target Exposure Index (EIT):**
- For each specific type of radiographic examination (e.g., chest PA, abdomen AP), a **Target Exposure Index (EIT)** should be established by the institution (based on radiologist preference, physicist input, and manufacturer guidance).
- This EIT represents the desired detector exposure level that provides the optimal balance between image quality (acceptable noise) and patient dose for that specific exam.

**2.4. Deviation Index (DI):**
- The **Deviation Index (DI)** is the recommended feedback mechanism for technologists.
- It quantifies how far the actual EI for a given image deviates from the target EIT for that examination type.
- **Formula:** DI = 10 * log10 (EI / EIT)
- **Interpretation:**
    - DI = 0: Actual exposure matches the target.
    - DI > 0: Overexposure. A DI of +3 means exposure was 2x the target (10^(3/10) ≈ 2).
    - DI < 0: Underexposure. A DI of -3 means exposure was 1/2 the target (10^(-3/10) ≈ 0.5).
- **Goal:** Technologists should aim to achieve a DI close to 0 for most examinations.
- **Benefits:** Provides immediate, quantitative feedback on exposure adequacy relative to the established target, independent of vendor-specific EI values.

**2.5. Indicated Equivalent Air Kerma (KIND):**
- To facilitate standardization, the report introduces the concept of **Indicated Equivalent Air Kerma (KIND)**.
- KIND is the air kerma (in μGy) incident upon the detector under standard, free-in-air conditions (specific beam quality, geometry) that would produce the same pixel value (after processing corrections) as was measured in a specific region of interest (ROI) on the actual clinical image.
- Essentially, it relates the pixel values in a clinical image back to a standardized air kerma value, providing a vendor-neutral measure related to detector exposure.
- The EI used in the DI calculation should ideally be directly proportional to KIND.

## 3. Standard Radiation Exposure Conditions

To ensure consistency in calibrating and comparing EI values, TG-116 defines standard beam conditions:
- **Beam Quality:** Based on the IEC 61267 RQA5 condition (70 kVp, 21 mm Al total filtration), but modified slightly for practicality using commonly available filter materials (e.g., specific thicknesses of Type 1100 Al or a Cu/Al combination) to achieve a closely matched Half Value Layer (HVL).
- **Geometry:** Specific source-to-detector distance (180 cm) and field size.
- **Calibration:** Procedure outlined for measuring air kerma under these standard conditions and relating it to the detector's signal response (pixel values) to establish the relationship needed for KIND and EI calculation.

## 4. Clinical Implementation and Use

- **Establishing EIT Values:** Requires collaboration between radiologists, physicists, and lead technologists to determine the acceptable balance of noise and dose for different exam types and patient sizes.
- **Monitoring DI:** Technologists should monitor the DI for each exposure. Supervisors and physicists should periodically review DI values as part of the quality control program to identify trends (e.g., consistent over/underexposure for specific exams or technologists) and potential issues with equipment (e.g., AEC malfunction).
- **DI Ranges:** While aiming for DI=0, a range (e.g., -3 to +3) might be considered acceptable, depending on the exam and clinical context. Specific institutional policies should define alert levels.
- **AEC Integration:** Automatic Exposure Control (AEC) systems should be calibrated to achieve the desired EIT (resulting in DI ≈ 0) for an average-sized patient for each specific exam.
- **Limitations:** DI reflects *detector* exposure, not necessarily patient dose (which also depends on beam area, patient thickness, etc.). DI should not be used as the sole indicator of image quality (image review is still essential). Inappropriate clinical use (e.g., rejecting images solely based on DI without considering diagnostic content) should be avoided.

## Conclusion

AAPM TG-116 provides a framework for standardizing exposure feedback in digital radiography through the use of a Target Exposure Index (EIT) and a Deviation Index (DI). The DI offers a vendor-neutral, quantitative measure of detector exposure relative to a pre-defined target, aiming to combat exposure creep, optimize image quality, and manage patient dose more effectively than relying on subjective image appearance alone. Proper implementation requires establishing appropriate EIT values and integrating DI monitoring into the routine clinical workflow and quality control program.

