# Section 7.1: Mathematics Relevant to Medical Physics (Revised)

## Learning Objectives

Upon completion of this section, the learner should be able to:

1.  **Describe** the fundamental concepts of differential and integral calculus and **apply** them to model physical processes in medical physics, such as radioactive decay and radiation attenuation.
2.  **Explain** the role of linear algebra, including vectors and matrices, in representing medical images and geometric transformations in radiotherapy.
3.  **Perform** basic matrix operations and **discuss** their application in image processing and reconstruction.
4.  **Define** the Fourier Transform and **explain** its significance in medical imaging modalities like MRI and CT, including the concept of k-space and the Convolution Theorem.
5.  **Identify** common numerical methods (interpolation, integration, root finding, Monte Carlo) and **describe** their use in approximating solutions for complex problems in dose calculation, treatment planning, and simulation.
6.  **Recognize** different coordinate systems (Cartesian, polar, spherical) and **explain** the importance of coordinate transformations in radiotherapy treatment planning and delivery.
7.  **Solve** basic problems applying these mathematical concepts to practical medical physics scenarios.

## Introduction

Mathematics serves as the essential language and analytical framework underpinning the field of medical physics. It enables the precise description, modeling, and quantitative analysis of complex physical phenomena encountered in diagnostic imaging, nuclear medicine, and radiation therapy. From the exponential nature of radioactive decay and radiation attenuation, through the matrix manipulations inherent in digital image processing, to the sophisticated algorithms used for image reconstruction and treatment plan optimization, a robust understanding of core mathematical principles is indispensable. This section provides a detailed review of key mathematical areas—calculus, linear algebra, Fourier analysis, numerical methods, and coordinate systems—emphasizing their practical application and illustrating concepts with detailed, solved examples relevant to the medical physicist.

## Calculus: The Mathematics of Change and Accumulation

Calculus provides powerful tools for analyzing systems where quantities change continuously. It encompasses differentiation (measuring rates of change) and integration (measuring accumulation or total effect).

### Differentiation

Differentiation finds the instantaneous rate at which one quantity changes with respect to another. The derivative of a function f(x) with respect to x, denoted as f'(x) or df/dx, represents the slope of the function at point x.

*   **Concept:** Measures how rapidly a function's value changes at a specific point.
*   **Key Applications:**
    *   **Radioactive Decay:** The rate of decay of radioactive nuclei (dN/dt) is proportional to the number of nuclei present (N): dN/dt = -λN. The negative sign indicates a decrease in N over time, and λ is the decay constant.
    *   **Radiation Attenuation:** The rate of change in intensity (I) of a narrow monoenergetic photon beam as it passes through a small thickness (dx) of material is proportional to the intensity: dI/dx = -μI, where μ is the linear attenuation coefficient.
    *   **Dose Gradients:** Finding the rate of change of dose with distance helps identify regions of rapid dose fall-off (penumbra) or locate dose maxima/minima within a treatment plan.

*   **Solved Example: Radioactive Decay Rate**
    *   **Problem:** A sample contains 1x10^12 atoms of Iodine-131 (I-131), which has a decay constant (λ) of approximately 0.086 day⁻¹. What is the initial decay rate (activity) in disintegrations per day?
    *   **Solution:**
        1.  The decay rate is given by |dN/dt| = λN.
        2.  Substitute the given values: N = 1x10^12 atoms, λ = 0.086 day⁻¹.
        3.  Calculate the rate: |dN/dt| = (0.086 day⁻¹) * (1x10^12 atoms) = 8.6x10^10 atoms/day.
        4.  **Answer:** The initial decay rate (activity) is 8.6x10^10 disintegrations per day.

### Integration

Integration is the reverse process of differentiation. It is used to find the total accumulation of a quantity when its rate of change is known, often represented as the area under a curve.

*   **Concept:** Sums up infinitesimal contributions to find a total quantity.
*   **Key Applications:**
    *   **Total Activity/Remaining Nuclei:** Integrating the decay rate equation dN/dt = -λN from time 0 to t yields the formula for the number of nuclei remaining: N(t) = N₀e^(-λt).
    *   **Total Dose:** Integrating the dose rate over the treatment time gives the total dose delivered.
    *   **Integral Dose:** Integrating the dose over a volume gives the total energy deposited in that volume.
    *   **Beam Intensity:** Integrating the attenuation equation dI/dx = -μI from thickness 0 to x yields the formula for transmitted intensity: I(x) = I₀e^(-μx).

*   **Solved Example: Radiation Attenuation**
    *   **Problem:** A monoenergetic photon beam with initial intensity I₀ = 1000 units passes through 5 cm of material with a linear attenuation coefficient μ = 0.15 cm⁻¹. What is the intensity I(x) after passing through the material?
    *   **Solution:**
        1.  The formula for transmitted intensity is I(x) = I₀e^(-μx).
        2.  Substitute the given values: I₀ = 1000 units, μ = 0.15 cm⁻¹, x = 5 cm.
        3.  Calculate the exponent: -μx = -(0.15 cm⁻¹)(5 cm) = -0.75.
        4.  Calculate the transmitted intensity: I(5 cm) = 1000 * e^(-0.75).
        5.  Using a calculator, e^(-0.75) ≈ 0.472.
        6.  I(5 cm) = 1000 * 0.472 = 472 units.
        7.  **Answer:** The intensity after passing through 5 cm of the material is 472 units.

### Differential Equations

These are equations that involve functions and their derivatives. They are fundamental for modeling dynamic systems.

*   **Concept:** Relate a function to its rate(s) of change.
*   **Key Applications:**
    *   **First-Order ODEs:** Describe processes like radioactive decay (dN/dt = -λN) and simple attenuation (dI/dx = -μI).
    *   **Systems of ODEs:** Can model multi-compartment systems or Bateman equations for decay chains.
    *   **Partial Differential Equations (PDEs):** Used in more complex modeling, such as the heat equation for thermal effects (e.g., RF heating in MRI, HIFU) or approximations to the Boltzmann transport equation for advanced dose calculations.

## Linear Algebra: The Mathematics of Vectors and Spaces

Linear algebra provides the framework for handling multi-dimensional data and transformations, crucial for image representation, processing, and geometric operations in radiotherapy.

### Vectors and Matrices

*   **Vectors:** Quantities possessing both magnitude and direction. Represented as arrows or ordered lists of numbers (components). Used for positions, displacements, forces, velocities, and gradients.
*   **Matrices:** Rectangular arrays of numbers arranged in rows and columns. Used to represent:
    *   **Images:** A digital image is a matrix where each element represents a pixel's intensity or color.
    *   **Transformations:** Operations like rotation, scaling, and translation can be represented by matrices.
    *   **Systems of Equations:** Coefficients of linear equations can be arranged in a matrix.

### Matrix Operations

Matrices can be added, subtracted, multiplied by scalars, and multiplied together under specific rules.

*   **Matrix Multiplication:** Used to apply transformations or combine operations. If A is an m x n matrix and B is an n x p matrix, their product C = AB is an m x p matrix where C_ij = Σ(A_ik * B_kj) for k=1 to n.
*   **Transpose (Aᵀ):** Rows become columns and columns become rows.
*   **Inverse (A⁻¹):** For a square matrix A, its inverse A⁻¹ (if it exists) satisfies AA⁻¹ = A⁻¹A = I (identity matrix). Used for solving systems of linear equations (Ax = b => x = A⁻¹b) and reversing transformations.

*   **Key Applications:**
    *   **Geometric Transformations:** Rotation matrices are used to calculate dose distributions relative to rotated gantry/collimator/couch angles.
    *   **Image Processing:** Convolution filters (kernels) are small matrices applied across an image.
    *   **Image Reconstruction:** Iterative reconstruction algorithms (CT, PET, SPECT) often involve solving large systems of linear equations represented in matrix form.
    *   **Inverse Planning (IMRT/VMAT):** Optimization involves solving matrix equations to find beamlet intensities that best match the desired dose distribution.

*   **Solved Example: Rotation Matrix in 2D**
    *   **Problem:** A point P is located at coordinates (x, y) = (10, 5). If the coordinate system is rotated counter-clockwise by an angle θ = 30 degrees, what are the new coordinates (x', y') of the point P relative to the rotated axes?
    *   **Solution:**
        1.  The 2D counter-clockwise rotation matrix R(θ) is:
            ```
            [ cos(θ)  sin(θ) ]
            [ -sin(θ) cos(θ) ]
            ```
            Note: This matrix transforms the *coordinates* of a fixed point when the *axes* are rotated counter-clockwise. Alternatively, rotating the *point* counter-clockwise uses `[cos(θ) -sin(θ); sin(θ) cos(θ)]`.
        2.  Calculate the trigonometric values for θ = 30°: cos(30°) = √3/2 ≈ 0.866, sin(30°) = 1/2 = 0.5.
        3.  The rotation matrix is approximately:
            ```
            [ 0.866  0.500 ]
            [ -0.500 0.866 ]
            ```
        4.  The new coordinates (x', y') are found by matrix multiplication: [x'; y'] = R(θ) * [x; y].
            ```
            [ x' ] = [ 0.866  0.500 ] [ 10 ]
            [ y' ]   [ -0.500 0.866 ] [  5 ]
            ```
        5.  Calculate x': x' = (0.866 * 10) + (0.500 * 5) = 8.66 + 2.50 = 11.16.
        6.  Calculate y': y' = (-0.500 * 10) + (0.866 * 5) = -5.00 + 4.33 = -0.67.
        7.  **Answer:** The new coordinates of point P relative to the rotated axes are approximately (11.16, -0.67).

## Fourier Analysis: Decomposing Signals into Frequencies

Fourier analysis allows complex signals or functions to be represented as a sum (or integral) of simple sine and cosine waves of different frequencies. The Fourier Transform (FT) is the mathematical tool that converts a signal from its original domain (e.g., time or space) into the frequency domain.

*   **Concept:** Any complex waveform can be built by adding together simple sinusoidal waves.
*   **Fourier Transform (FT):** Maps a function f(t) (time domain) or f(x) (spatial domain) to its frequency representation F(ω) or F(k).
    *   *Continuous FT:* F(ω) = ∫ f(t) e^(-iωt) dt
    *   *Inverse FT:* f(t) = (1/2π) ∫ F(ω) e^(iωt) dω (Normalization factors may vary)
    *   *Discrete FT (DFT) / Fast FT (FFT):* Versions used for digital signals and images.
*   **Frequency Domain:** Represents the signal in terms of the amplitude and phase of its constituent frequencies.
*   **Key Applications:**
    *   **MRI:** The fundamental principle of MRI involves acquiring signals in the spatial frequency domain (k-space). The FT is essential to transform this k-space data into the spatial domain image we see.
    *   **CT Reconstruction:** Filtered Back-Projection (FBP) uses the Fourier Slice Theorem. Projections are 1D FT'd, filtered in the frequency domain (by multiplying with a ramp filter, |k|), inverse FT'd, and then back-projected.
    *   **Image Filtering:** Applying filters in the frequency domain (multiplying the FT of the image by a filter function) can efficiently perform operations like noise reduction (low-pass filter) or edge enhancement (high-pass filter).
*   **Convolution Theorem:** A cornerstone of signal processing. It states that convolution in one domain (e.g., spatial) is equivalent to pointwise multiplication in the other domain (e.g., frequency), and vice versa.
    *   FT{f(x) * g(x)} = F(k) ⋅ G(k)
    *   FT{f(x) ⋅ g(x)} = (1/2π) F(k) * G(k)
    *   This theorem dramatically simplifies convolution operations (like applying a smoothing filter or calculating dose using convolution algorithms) by transforming them into simpler multiplications in the frequency domain using FFTs.

*   **Conceptual Example: MRI k-space**
    *   **Concept:** In MRI, gradient magnetic fields encode spatial information into the frequency and phase of the detected signal. Each acquired data point corresponds to a specific spatial frequency (kx, ky) in k-space.
    *   **Process:**
        1.  The MRI scanner systematically acquires data points covering a region of k-space.
        2.  This k-space data represents the 2D Fourier Transform of the object being imaged.
        3.  Applying a 2D Inverse Fourier Transform to the k-space data reconstructs the image in the spatial domain.
        4.  **Key Insight:** Low spatial frequencies (center of k-space) determine overall image contrast and brightness, while high spatial frequencies (periphery of k-space) determine fine details and edges.

## Numerical Methods: Approximating Solutions

Many problems in medical physics are too complex for exact analytical solutions. Numerical methods use computational algorithms to find approximate solutions.

*   **Concept:** Using discrete steps and iterative calculations to approximate solutions.
*   **Key Methods & Applications:**
    *   **Interpolation/Extrapolation:** Estimating values between (interpolation) or beyond (extrapolation) known data points.
        *   *Linear Interpolation:* Simple estimation assuming a straight line between points. y = y₁ + (x - x₁)(y₂ - y₁)/(x₂ - x₁).
        *   *Higher-Order Interpolation:* Uses polynomials (e.g., spline interpolation) for smoother results.
        *   *Use:* Estimating beam data (PDD, TMR, output factors) for non-measured field sizes, depths, or distances; resampling images.
    *   **Numerical Integration (Quadrature):** Approximating the value of a definite integral (area under a curve).
        *   *Methods:* Trapezoidal rule (approximates area using trapezoids), Simpson's rule (uses parabolic segments).
        *   *Use:* Calculating Dose Volume Histograms (DVHs), calculating total energy deposited, evaluating complex dose distributions.
    *   **Root Finding:** Finding solutions to equations of the form f(x) = 0.
        *   *Methods:* Bisection method (repeatedly narrows interval known to contain a root), Newton-Raphson method (iteratively improves guess using tangent lines).
        *   *Use:* Solving implicit equations in shielding calculations or beam modeling.
    *   **Solving Differential Equations:** Approximating solutions numerically.
        *   *Methods:* Euler method (simple first step), Runge-Kutta methods (more accurate), Finite Difference methods (discretize space/time).
        *   *Use:* Advanced dose calculation algorithms, modeling dynamic physiological processes.
    *   **Monte Carlo (MC) Methods:** Using random number generation to simulate stochastic processes.
        *   *Process:* Simulate the paths and interactions of millions/billions of individual particles (photons, electrons) through patient geometry.
        *   *Use:* Gold standard for accurate dose calculation (especially in heterogeneous media), detector response simulation, shielding design verification, brachytherapy dose calculations.

*   **Solved Example: Linear Interpolation**
    *   **Problem:** Measured PDD values for a beam are 85.0% at 5 cm depth (d₁) and 75.0% at 10 cm depth (d₂). Estimate the PDD at 7 cm depth (d) using linear interpolation.
    *   **Solution:**
        1.  The formula for linear interpolation is: PDD(d) = PDD(d₁) + (d - d₁)[PDD(d₂) - PDD(d₁)] / (d₂ - d₁).
        2.  Identify the values: d₁ = 5 cm, PDD(d₁) = 85.0%; d₂ = 10 cm, PDD(d₂) = 75.0%; d = 7 cm.
        3.  Calculate the difference in depths: d₂ - d₁ = 10 cm - 5 cm = 5 cm.
        4.  Calculate the difference in PDDs: PDD(d₂)
(Content truncated due to size limit. Use line ranges to read in chunks)