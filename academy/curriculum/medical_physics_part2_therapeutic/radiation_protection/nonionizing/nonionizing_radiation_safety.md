# Section 6.11: Nonionizing Radiation Safety

**Approximate Lecture Time:** 1 Hour

**Learning Objectives:**

Upon completion of this section, the student will be able to:

1.  **Identify** the primary safety concerns associated with Magnetic Resonance Imaging (MRI), including static magnetic fields, gradient fields, and radiofrequency (RF) fields.
2.  **Describe** the projectile effect in MRI and the importance of screening for ferromagnetic materials.
3.  **Explain** the concept of Specific Absorption Rate (SAR) and its relevance to RF heating in MRI.
4.  **Discuss** safety considerations related to acoustic noise and cryogens in MRI.
5.  **Classify** lasers according to hazard potential (e.g., ANSI Z136 standard).
6.  **Identify** the primary hazards associated with lasers used in medicine (eye and skin).
7.  **Describe** control measures for laser safety, including protective eyewear, controlled areas, and interlocks.
8.  **Explain** the potential bioeffects of diagnostic ultrasound (thermal and mechanical).
9.  **Define** the Thermal Index (TI) and Mechanical Index (MI) and their role in ultrasound safety.
10. **Apply** ALARA principles to the use of nonionizing radiation modalities.

**Key Points:**

*   **Nonionizing vs. Ionizing:** Unlike ionizing radiation, nonionizing radiation (MRI RF/gradients, lasers, ultrasound) does not have sufficient energy per quantum to ionize atoms but can still cause biological effects through other mechanisms (heating, mechanical stress, photochemical reactions, nerve stimulation).
*   **MRI Safety:**
    *   *Static Field:* Main hazard is the projectile effect (ferromagnetic objects becoming airborne). Strict screening and access control are paramount. Can also affect implanted electronic devices (pacemakers, neurostimulators).
    *   *Gradient Fields:* Rapidly switching gradients induce currents, potentially causing peripheral nerve stimulation (PNS). Limits are set to minimize this.
    *   *RF Fields:* Deposit energy, causing tissue heating. Specific Absorption Rate (SAR) quantifies this (W/kg). Regulatory limits exist for whole-body and localized SAR.
    *   *Acoustic Noise:* Gradient switching creates loud noise, requiring hearing protection.
    *   *Cryogens:* Liquid helium used to cool superconducting magnets poses risks during a quench (asphyxiation, frostbite).
*   **Laser Safety:**
    *   *Hazards:* Primarily eye damage (retinal or corneal burns depending on wavelength) and skin burns.
    *   *Classification:* Lasers are classified (Class 1, 1M, 2, 2M, 3R, 3B, 4) based on their potential hazard, dictating required safety measures.
    *   *Controls:* Engineering controls (interlocks, enclosed beams), administrative controls (training, procedures, Laser Safety Officer - LSO), and Personal Protective Equipment (PPE - appropriate laser safety eyewear).
*   **Ultrasound Safety:**
    *   *Bioeffects:* Potential for thermal effects (tissue heating) and mechanical effects (cavitation - formation/collapse of bubbles).
    *   *Safety Indices:* Thermal Index (TI) estimates potential temperature rise; Mechanical Index (MI) estimates likelihood of cavitation. Displayed on scanners.
    *   *ALARA:* Principle applies – use the lowest output power and shortest scan time consistent with obtaining diagnostic information.

---

## 1. Introduction to Nonionizing Radiation Safety

While medical physics often focuses heavily on ionizing radiation, several crucial diagnostic and therapeutic modalities utilize nonionizing radiation. These include Magnetic Resonance Imaging (MRI), lasers, and ultrasound. Although these modalities do not possess sufficient energy to ionize atoms directly, they interact with biological tissues through different mechanisms and present unique safety challenges that must be understood and managed by medical physicists, clinicians, and technologists.

This section explores the fundamental safety principles and specific hazards associated with MRI, lasers, and ultrasound in the clinical environment.

## 2. Magnetic Resonance Imaging (MRI) Safety

MRI utilizes a powerful static magnetic field, time-varying magnetic field gradients, and radiofrequency (RF) pulses to generate images. Each of these components presents distinct safety considerations.

### 2.1 Static Magnetic Field (B₀)

The primary hazard of the strong static magnetic field (typically 0.5T to 7T, though higher fields exist in research) is its ability to attract ferromagnetic objects with tremendous force. This is known as the **projectile effect** or **missile effect**.

*   **Projectile Effect:** Loose ferromagnetic items (e.g., oxygen tanks, IV poles, tools, wheelchairs, keys, hairpins, paperclips) can be rapidly accelerated towards the magnet bore, posing a severe risk of injury or death to anyone in their path, as well as potentially damaging the scanner.
*   **Screening:** Rigorous screening of all individuals and equipment entering the MRI scan room (Zone IV) is mandatory. This includes patients, staff, visitors, and emergency responders. Screening questionnaires, ferromagnetic detection systems (FMDS), and physical checks are employed.
*   **Implanted Devices:** The static field can exert forces or torque on certain metallic implants (e.g., older aneurysm clips, shrapnel) and can interfere with the function of electronic implants like pacemakers, implantable cardioverter-defibrillators (ICDs), cochlear implants, and neurostimulators. Devices must be confirmed as "MR Safe," "MR Conditional," or "MR Unsafe" before a patient enters the field. "MR Conditional" devices require specific conditions (field strength, SAR limits, gradient slew rates) to be met for safe scanning.
*   **Access Control:** Strict access control is implemented using physical barriers and signage to define safety zones (see Section 6.10 and specific MRI safety guidelines like the ACR Manual on MR Safety).

### 2.2 Time-Varying Gradient Magnetic Fields

Gradient fields are rapidly switched on and off to spatially encode the MR signal. According to Faraday's law of induction, these changing magnetic fields induce electrical currents in conductive materials, including human tissues.

*   **Peripheral Nerve Stimulation (PNS):** Induced currents can stimulate peripheral nerves and muscles, causing sensations ranging from mild tingling to involuntary muscle contractions. Gradient systems are designed, and pulse sequences are limited, to keep the rate of change of the magnetic field (dB/dt) below levels likely to cause significant PNS or cardiac stimulation.
*   **Acoustic Noise:** The rapid switching of gradients within the main magnetic field generates Lorentz forces on the gradient coils, causing vibrations that produce loud acoustic noise (often exceeding 100-120 dBA). Hearing protection (earplugs, headphones) is mandatory for patients and anyone remaining in the scan room during active scanning.

### 2.3 Radiofrequency (RF) Fields

RF pulses are used to excite protons in the body. The primary safety concern with RF fields is tissue heating due to energy absorption.

*   **Specific Absorption Rate (SAR):** SAR is the measure of RF power absorbed per unit mass of tissue, expressed in Watts per kilogram (W/kg). It depends on factors like field strength, RF pulse sequence characteristics (flip angle, repetition time, pulse duration), patient size, and the geometry of the RF transmit coil.
*   **Tissue Heating:** Absorbed RF energy is dissipated as heat. The body's thermoregulatory system can typically manage moderate heating, but excessive RF deposition can lead to temperature increases, potentially causing discomfort or, in extreme cases, burns. Patients with compromised thermoregulation (e.g., due to medication, fever, cardiovascular issues) are at higher risk.
*   **SAR Limits:** Regulatory bodies (e.g., FDA in the US, IEC internationally) set limits on whole-body averaged SAR and localized SAR (typically averaged over 1g or 10g of tissue) to prevent excessive heating. MRI systems monitor estimated SAR levels and restrict sequences to stay within these limits based on operating modes (Normal, First Level Controlled, Second Level Controlled).
*   **RF Burns:** Burns can occur due to direct contact with RF transmit coils or, more commonly, from induced currents in conductive loops formed by patient positioning (e.g., skin-to-skin contact like crossed ankles), ECG leads, pulse oximeter cables, or improperly placed surface coils. Careful padding and cable routing are essential to prevent loop formation.

### 2.4 Cryogen Safety

Superconducting magnets are cooled using liquid cryogens, primarily liquid helium (LHe), often with a layer of liquid nitrogen (LN₂).

*   **Quench:** A quench is the sudden loss of superconductivity, causing the magnet coils to rapidly heat up and boil off large volumes of cryogen gas (helium). While modern systems are designed to vent this gas safely outside the building, a failure in the vent system could lead to the scan room rapidly filling with helium gas.
*   **Hazards:** Helium displaces oxygen, creating an asphyxiation hazard. The escaping gas is also extremely cold, posing a risk of frostbite. Scan rooms are equipped with oxygen monitors and specific emergency procedures for quenches.

## 3. Laser Safety

Lasers (Light Amplification by Stimulated Emission of Radiation) produce intense, coherent beams of electromagnetic radiation (typically visible or infrared). They are used in medicine for various applications, including surgery, dermatology, ophthalmology, and patient alignment in radiotherapy.

### 3.1 Laser Hazards

The primary hazards depend on the laser's wavelength, power, and exposure duration.

*   **Eye Hazards:** The eye is particularly vulnerable. Depending on the wavelength, laser light can be focused by the lens onto the retina (visible and near-infrared), potentially causing permanent retinal burns and vision loss even at low power levels. Ultraviolet (UV) and far-infrared (IR) lasers are primarily absorbed by the cornea and lens, potentially causing corneal burns or cataracts.
*   **Skin Hazards:** High-power lasers can cause skin burns. Prolonged exposure to UV lasers can also increase the risk of skin cancer.
*   **Non-Beam Hazards:** These include electrical hazards from power supplies, fire hazards from beam interaction with flammable materials, and hazardous fumes or aerosols produced during laser ablation of tissue (laser plume).

### 3.2 Laser Classification

Lasers are classified based on their potential hazard, primarily determined by their power/energy output and wavelength. The most common system is defined by the American National Standards Institute (ANSI) Z136 series and adopted by regulatory bodies like the FDA.

*   **Class 1:** Considered non-hazardous under normal operating conditions (e.g., laser printers, CD players).
*   **Class 1M:** Non-hazardous unless viewed with magnifying optics.
*   **Class 2:** Low-power visible lasers; eye protection is normally afforded by the aversion response (blinking). (e.g., barcode scanners).
*   **Class 2M:** Low-power visible lasers; non-hazardous unless viewed with magnifying optics.
*   **Class 3R:** Marginally unsafe for direct viewing; risk of injury is low. (e.g., some laser pointers, alignment lasers).
*   **Class 3B:** Hazardous for direct viewing and specular reflections. Not typically a fire hazard or hazardous for diffuse reflections. (e.g., many therapeutic lasers, research lasers).
*   **Class 4:** High-power lasers; hazardous for direct viewing, specular and diffuse reflections. Potential fire hazard and skin hazard. (e.g., surgical lasers, industrial lasers).

### 3.3 Laser Safety Control Measures

A comprehensive laser safety program, often overseen by a designated Laser Safety Officer (LSO), implements a hierarchy of controls:

*   **Engineering Controls:** Features built into the laser system or facility (e.g., protective housing, interlocks on doors/enclosures, beam shutters, remote firing controls).
*   **Administrative Controls:** Procedures, training, standard operating procedures (SOPs), warning signs, designation of controlled areas.
*   **Personal Protective Equipment (PPE):** Primarily **laser safety eyewear** specifically chosen for the laser's wavelength(s) and required Optical Density (OD). Skin protection (gloves, lab coats) may also be needed for high-power lasers.

## 4. Ultrasound Safety

Diagnostic ultrasound uses high-frequency sound waves to create images. While generally considered very safe, there are potential biological effects associated with the energy deposited in tissues.

### 4.1 Potential Bioeffects

Two primary mechanisms for bioeffects are recognized:

*   **Thermal Effects:** Ultrasound energy absorbed by tissue is converted to heat. Significant temperature increases (several degrees Celsius) could potentially have adverse effects, particularly on sensitive tissues like the developing fetus. The **Thermal Index (TI)** is displayed on ultrasound systems to provide an estimate of the potential temperature rise under specific conditions (TIS for soft tissue, TIB for bone near focus, TIC for cranial bone).
*   **Mechanical Effects (Cavitation):** Ultrasound waves consist of compressions and rarefactions. The pressure changes can cause gas bubbles already present in tissue (or created by the ultrasound itself) to oscillate, grow, and potentially collapse violently (inertial cavitation). This collapse generates localized high temperatures and pressures, potentially damaging nearby cells. The **Mechanical Index (MI)** is displayed to estimate the likelihood of inertial cavitation based on peak negative pressure and frequency.

### 4.2 Safety Guidelines and ALARA

Extensive research has not conclusively demonstrated adverse effects from diagnostic ultrasound at typical clinical exposure levels. However, the potential for bioeffects exists, especially at higher outputs or longer exposure times. Therefore, the principle of **ALARA (As Low As Reasonably Achievable)** is applied:

*   Use ultrasound only when medically indicated.
*   Use the lowest output power (acoustic intensity) consistent with obtaining diagnostic information.
*   Minimize the exposure time (dwell time).
*   Be aware of the displayed TI and MI values and keep them as low as possible, particularly in sensitive applications like obstetrics.

Regulatory bodies and professional organizations (e.g., FDA, AIUM - American Institute of Ultrasound in Medicine) provide guidelines and recommendations for safe ultrasound use.

---

**Assessment Questions (ABR Style):**

1.  The primary safety concern associated with the static magnetic field in MRI is:
    (A) Tissue heating
    (B) Peripheral nerve stimulation
    (C) Acoustic noise
    (D) Projectile effect
    (E) Cavitation

2.  Specific Absorption Rate (SAR) is a measure used to quantify the potential for tissue heating from which component of the MRI system?
    (A) Static magnetic field
    (B) Gradient magnetic fields
    (C) Radiofrequency (RF) fields
    (D) Cryogen boil-off
    (E) Shim coils

3.  Which laser classification represents the highest potential hazard, requiring the most stringent control measures?
    (A) Class 1
    (B) Class 2
    (C) Class 3R
    (D) Class 3B
    (E) Class 4

4.  The Mechanical Index (MI) displayed on an ultrasound scanner provides an indication of the risk associated with:
    (A) Tissue temperature rise
    (B) Cavitation
    (C) Peripheral nerve stimulation
    (D) Projectile effect
    (E) Retinal damage

5.  A patient with an older, non-conditional pacemaker requires an MRI scan. What is the appropriate course of action?
    (A) Proceed with the scan using low SAR settings.
    (B) Proceed with the scan but monitor the patient closely.
    (C) Consult the cardiologist about temporarily reprogramming the pacemaker.
    (D) The scan is contraindicated due to the MR Unsafe device.
    (E) Scan only using a 1.
(Content truncated due to size limit. Use line ranges to read in chunks)