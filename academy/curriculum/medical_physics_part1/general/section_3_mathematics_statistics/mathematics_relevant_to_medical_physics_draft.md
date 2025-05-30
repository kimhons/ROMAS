# Section 7.1: Mathematics Relevant to Medical Physics

## Introduction

Mathematics provides the fundamental language and tools necessary to describe, model, and solve problems in medical physics. From the basic principles of radiation interaction to complex image reconstruction algorithms and treatment planning optimization, a solid understanding of relevant mathematical concepts is essential. This section reviews key areas of mathematics frequently employed in diagnostic imaging, nuclear medicine, and radiation therapy, including calculus, linear algebra, Fourier analysis, numerical methods, and coordinate systems.

## Calculus

Calculus deals with rates of change (differentiation) and accumulation (integration). It is fundamental to describing many physical processes in medical physics.

*   **Differentiation:** Used to find rates of change.
    *   *Example:* Radioactive decay rate (dN/dt = -λN), where N is the number of radioactive nuclei and λ is the decay constant.
    *   *Example:* Calculating the gradient of dose distributions to find maximum or minimum dose points.
    *   *Example:* Describing the change in beam intensity as it passes through matter (dI/dx = -μI, leading to I = I₀e^(-μx)).
*   **Integration:** Used to find the total amount or accumulation.
    *   *Example:* Calculating the total activity remaining after a certain time by integrating the decay rate.
    *   *Example:* Calculating the total dose delivered over time or within a volume.
    *   *Example:* Determining the area under a curve, such as calculating the integral dose or evaluating detector response.
    *   *Example:* Solving for beam intensity after passing through a thickness x: ∫(dI/I) = -∫μ dx, leading to ln(I) - ln(I₀) = -μx, or I = I₀e^(-μx).
*   **Differential Equations:** Equations involving derivatives that model physical systems.
    *   *Example:* First-order linear differential equations describe radioactive decay and beam attenuation.
    *   *Example:* Partial differential equations (PDEs) can be used in advanced dose calculation algorithms (e.g., Boltzmann transport equation approximations) or modeling heat deposition (e.g., from RF fields in MRI).

## Linear Algebra

Linear algebra deals with vectors, matrices, and linear transformations. It is crucial for image processing, reconstruction, and dose calculations.

*   **Vectors:** Represent quantities with magnitude and direction (e.g., position, displacement, dose gradients).
*   **Matrices:** Rectangular arrays of numbers used to represent data (e.g., images, transformation operations).
    *   *Example:* Digital images are represented as matrices of pixel values.
    *   *Example:* Rotation matrices are used to describe gantry, collimator, and couch rotations in radiotherapy.
    *   *Example:* Transformation matrices describe changes between coordinate systems.
*   **Matrix Operations:** Addition, subtraction, scalar multiplication, matrix multiplication, transpose, inverse.
    *   *Example:* Image filtering and manipulation often involve matrix operations (e.g., convolution kernels).
    *   *Example:* Solving systems of linear equations is fundamental to iterative image reconstruction (e.g., in CT, PET, SPECT) and inverse planning optimization in IMRT/VMAT.
    *   *Example:* Eigenvalues and eigenvectors are used in principal component analysis (PCA) for image analysis and dimensionality reduction.

## Fourier Analysis

Fourier analysis decomposes functions or signals into a sum of sine and cosine waves of different frequencies. It is indispensable in medical imaging.

*   **Fourier Transform (FT):** Converts a signal from the time or spatial domain to the frequency domain.
    *   *Continuous FT:* F(ω) = ∫f(t)e^(-iωt) dt
    *   *Discrete FT (DFT):* Used for digital signals/images.
    *   *Fast Fourier Transform (FFT):* An efficient algorithm to compute the DFT.
*   **Applications:**
    *   **MRI:** The raw signal acquired in MRI is in the frequency domain (k-space). An inverse Fourier transform is used to reconstruct the image.
    *   **CT:** Filtered back-projection reconstruction involves Fourier transforms for filtering the projection data.
    *   **Image Processing:** Frequency-domain filtering (e.g., high-pass for edge enhancement, low-pass for noise reduction) is performed using FTs.
*   **Convolution Theorem:** States that convolution in the spatial/time domain is equivalent to multiplication in the frequency domain (and vice versa). This simplifies convolution operations, which are common in image filtering and dose calculation (convolution/superposition algorithms).
    *   FT{f(x) * g(x)} = FT{f(x)} ⋅ FT{g(x)}
    *   FT{f(x) ⋅ g(x)} = FT{f(x)} * FT{g(x)} (scaled by 1/2π depending on convention)

## Numerical Methods

Numerical methods provide techniques for approximating solutions to mathematical problems that cannot be solved analytically or are too complex for manual calculation. They are essential for computer-based calculations in medical physics.

*   **Interpolation/Extrapolation:** Estimating values between (interpolation) or beyond (extrapolation) known data points.
    *   *Example:* Interpolating PDD or TMR values for depths or field sizes not explicitly measured.
    *   *Example:* Resampling images to different resolutions.
*   **Numerical Integration:** Approximating definite integrals.
    *   *Example:* Calculating dose volume histograms (DVHs) involves integrating dose over specified volumes.
    *   *Example:* Methods like the trapezoidal rule or Simpson's rule.
*   **Root Finding:** Finding the values of x for which f(x) = 0.
    *   *Example:* Solving equations in treatment planning or shielding calculations where analytical solutions are difficult.
    *   *Example:* Methods like bisection method, Newton-Raphson method.
*   **Solving Differential Equations:** Approximating solutions to ODEs and PDEs.
    *   *Example:* Finite difference methods used in some dose calculation algorithms or modeling dynamic processes.
*   **Monte Carlo Methods:** Using random sampling to simulate processes and obtain numerical results. Extensively used for accurate dose calculations, detector modeling, and shielding design.

## Coordinate Systems

Different coordinate systems are used to describe positions and orientations in medical physics.

*   **Cartesian Coordinates (x, y, z):** The standard system for defining points in 3D space. Commonly used for patient anatomy representation in CT/MRI images and defining locations within a treatment room.
*   **Polar Coordinates (r, θ):** Used in 2D, often for describing points relative to a central axis, like in beam profiles or detector arrays.
*   **Cylindrical Coordinates (ρ, φ, z):** Useful for objects with cylindrical symmetry, sometimes used in detector modeling or specific phantom geometries.
*   **Spherical Coordinates (r, θ, φ):** Useful for problems with spherical symmetry, such as calculating dose from point sources (e.g., in brachytherapy using TG-43 formalism) or describing directions in space.
*   **Transformations:** Converting coordinates between different systems (e.g., patient coordinates, gantry coordinates, beam coordinates) is crucial in radiotherapy treatment planning and delivery systems to ensure accurate targeting.

## Conclusion

Mathematics is an indispensable toolset for the medical physicist. Calculus allows the modeling of dynamic processes like decay and attenuation. Linear algebra provides the framework for handling images and transformations. Fourier analysis is key to understanding and performing image reconstruction in modalities like MRI and CT. Numerical methods enable complex computations required for dose calculation, optimization, and simulation. A thorough grasp of these mathematical principles allows physicists to understand the theoretical underpinnings of their equipment and techniques, develop new technologies, and ensure the accuracy and safety of clinical procedures.

## ABR-Style Assessment Questions

1.  The attenuation of a monoenergetic photon beam through a homogeneous material is best described by which type of mathematical function?
    a) Linear function
    b) Power function
    c) Exponential function
    d) Logarithmic function

2.  In Computed Tomography (CT) image reconstruction using filtered back-projection, the primary purpose of applying a filter (e.g., Ram-Lak) to the projection data is performed in which domain?
    a) Spatial domain
    b) Temporal domain
    c) Frequency domain
    d) Angular domain

3.  A medical physicist needs to calculate the Percent Depth Dose (PDD) at 12.5 cm depth, but only has measured data at 10 cm and 15 cm. Which mathematical technique would be most appropriate to estimate the PDD at 12.5 cm?
    a) Fourier Transform
    b) Linear Interpolation
    c) Numerical Integration
    d) Solving a differential equation

4.  The process of converting raw k-space data into a viewable image in Magnetic Resonance Imaging (MRI) primarily involves which mathematical operation?
    a) Matrix inversion
    b) Convolution
    c) Inverse Fourier Transform
    d) Differentiation

5.  Representing the rotation of a linear accelerator gantry from 0 degrees to 90 degrees can be efficiently performed using:
    a) Scalar multiplication
    b) A rotation matrix
    c) Numerical integration
    d) Root finding algorithm

**Answers:** 1-c, 2-c, 3-b, 4-c, 5-b

---
*End of Section 7.1*
