# Section 7.2: Statistics and Biostatistics

## Learning Objectives

Upon completion of this section, the learner should be able to:

1.  **Calculate and interpret** common descriptive statistics (mean, median, mode, standard deviation, variance) for medical physics data.
2.  **Identify and describe** key probability distributions (Binomial, Poisson, Normal) and **recognize** their applications in modeling medical physics phenomena (e.g., radioactive decay, image noise).
3.  **Explain** the principles of inferential statistics, including hypothesis testing, p-values, and confidence intervals.
4.  **Select and interpret** appropriate statistical tests (t-tests, ANOVA, chi-squared) for comparing groups or analyzing categorical data in medical physics contexts.
5.  **Define and interpret** correlation and linear regression analysis for exploring relationships between variables.
6.  **Discuss** fundamental statistical considerations in experimental design, data collection, and analysis relevant to medical physics research and quality assurance.
7.  **Define** sensitivity, specificity, and **recognize** the purpose of Receiver Operating Characteristic (ROC) analysis in evaluating diagnostic performance.

## Introduction

Statistics and biostatistics provide the essential tools for collecting, analyzing, interpreting, and drawing conclusions from data in medical physics. Whether evaluating the performance of an imaging system, assessing the significance of dose differences between treatment plans, monitoring quality control metrics, or interpreting clinical trial results, statistical methods are indispensable. This section covers fundamental concepts ranging from descriptive statistics and probability distributions to inferential testing and regression analysis, emphasizing their practical application in medical physics research, clinical practice, and quality assurance. Understanding these principles allows physicists to critically evaluate evidence, design robust experiments, and make data-driven decisions.

## Descriptive Statistics: Summarizing Data

Descriptive statistics summarize and describe the main features of a dataset.

*   **Measures of Central Tendency:** Describe the center of a distribution.
    *   **Mean (Average):** Sum of all values divided by the number of values. Sensitive to outliers.
        *   *Formula:* μ (population) or x̄ (sample) = Σx / N
    *   **Median:** The middle value when data are ordered. Less sensitive to outliers than the mean.
    *   **Mode:** The most frequently occurring value in the dataset.
*   **Measures of Dispersion (Variability):** Describe the spread or variability of data.
    *   **Range:** Difference between the maximum and minimum values. Highly sensitive to outliers.
    *   **Variance (σ² or s²):** Average of the squared differences from the mean. Measures the average spread around the mean.
        *   *Population Variance:* σ² = Σ(x - μ)² / N
        *   *Sample Variance:* s² = Σ(x - x̄)² / (n - 1) (Using n-1 provides an unbiased estimate of the population variance).
    *   **Standard Deviation (σ or s):** Square root of the variance. Provides a measure of spread in the original units of the data. Approximately 68% of data falls within ±1 SD, 95% within ±2 SD, and 99.7% within ±3 SD for a normal distribution.
    *   **Coefficient of Variation (CV):** Ratio of the standard deviation to the mean (CV = s / x̄), often expressed as a percentage. Useful for comparing variability between datasets with different means or units.

*   **Solved Example: Linac Output Constancy**
    *   **Problem:** Daily output measurements for a linac over 5 days are: 1.002, 0.995, 1.008, 0.991, 1.004 (relative to baseline). Calculate the mean, median, sample standard deviation, and CV.
    *   **Solution:**
        1.  **Order data:** 0.991, 0.995, 1.002, 1.004, 1.008
        2.  **Mean (x̄):** (0.991 + 0.995 + 1.002 + 1.004 + 1.008) / 5 = 5.000 / 5 = 1.000
        3.  **Median:** The middle value is 1.002.
        4.  **Sample Variance (s²):**
            *   Differences from mean: -0.009, -0.005, 0.002, 0.004, 0.008
            *   Squared differences: 0.000081, 0.000025, 0.000004, 0.000016, 0.000064
            *   Sum of squared differences = 0.000190
            *   s² = 0.000190 / (5 - 1) = 0.000190 / 4 = 0.0000475
        5.  **Sample Standard Deviation (s):** s = √s² = √0.0000475 ≈ 0.00689
        6.  **Coefficient of Variation (CV):** CV = (s / x̄) * 100% = (0.00689 / 1.000) * 100% ≈ 0.69%
        7.  **Answer:** Mean = 1.000, Median = 1.002, Standard Deviation ≈ 0.0069, CV ≈ 0.69%. This indicates low variability around the mean output.

## Probability Distributions: Modeling Randomness

Probability distributions describe the likelihood of different outcomes for random variables.

*   **Binomial Distribution:** Models the number of 

successes" in a fixed number (n) of independent trials, each with the same probability of success (p).
    *   *Formula:* P(X=k) = [n! / (k!(n-k)!)] * p^k * (1-p)^(n-k)
    *   *Use:* Modeling binary outcomes (e.g., pass/fail QA tests, presence/absence of artifact) in a set number of trials.
*   **Poisson Distribution:** Models the number of events occurring in a fixed interval of time or space, given the average rate (λ) of occurrence. Events occur independently.
    *   *Formula:* P(X=k) = (λ^k * e^-λ) / k!
    *   *Use:* Modeling radioactive decay counts in a detector over a fixed time, number of noise spikes in an image region, number of incident particles on a detector.
    *   *Property:* For large λ, the Poisson distribution approximates the Normal distribution. The standard deviation is √λ.
*   **Normal (Gaussian) Distribution:** The ubiquitous bell-shaped curve, characterized by its mean (μ) and standard deviation (σ).
    *   *Formula (Probability Density Function):* f(x) = [1 / (σ√(2π))] * e^(-(x-μ)² / (2σ²))
    *   *Use:* Modeling continuous variables that tend to cluster around a central value, such as measurement errors, variations in beam output (often assumed normal for analysis), distribution of pixel values in some image regions.
    *   *Central Limit Theorem:* States that the distribution of sample means approaches a normal distribution as the sample size increases, regardless of the original population distribution. This is fundamental to many inferential statistical methods.

*   **Solved Example: Poisson Distribution for Decay Counts**
    *   **Problem:** A radioactive source produces an average of λ = 4 counts per second in a detector. What is the probability of observing exactly k = 0 counts in a 1-second interval?
    *   **Solution:**
        1.  Use the Poisson probability formula: P(X=k) = (λ^k * e^-λ) / k!
        2.  Substitute k = 0 and λ = 4:
            P(X=0) = (4^0 * e^-4) / 0!
        3.  Recall that any number raised to the power of 0 is 1, and 0! (zero factorial) is 1.
            P(X=0) = (1 * e^-4) / 1 = e^-4
        4.  Calculate e^-4 ≈ 0.0183
        5.  **Answer:** The probability of observing exactly 0 counts in a 1-second interval is approximately 0.0183 or 1.83%.

## Inferential Statistics: Drawing Conclusions from Data

Inferential statistics uses sample data to make inferences or draw conclusions about a larger population.

*   **Hypothesis Testing:** A formal procedure for deciding between two competing hypotheses about a population parameter.
    *   **Null Hypothesis (H₀):** A statement of no effect or no difference (e.g., the mean output is unchanged, there is no difference between two plans).
    *   **Alternative Hypothesis (H₁ or Hₐ):** The statement we suspect is true (e.g., the mean output has changed, there is a difference).
    *   **Test Statistic:** A value calculated from sample data used to decide between H₀ and H₁.
    *   **P-value:** The probability of observing a test statistic as extreme as, or more extreme than, the one calculated, *assuming the null hypothesis is true*. A small p-value (typically < 0.05) provides evidence against H₀.
    *   **Significance Level (α):** A pre-determined threshold (commonly 0.05) for rejecting H₀. If p-value < α, reject H₀.
*   **Confidence Intervals (CI):** A range of values estimated from sample data that is likely to contain the true population parameter (e.g., mean, proportion) with a certain level of confidence (e.g., 95%).
    *   *Interpretation:* A 95% CI means that if we repeated the sampling process many times, 95% of the calculated intervals would contain the true population parameter.
    *   *Formula (approximate for large sample mean):* x̄ ± Z*(s/√n), where Z is the Z-score for the desired confidence level (e.g., 1.96 for 95%).
*   **Common Statistical Tests:**
    *   **t-tests:** Used to compare means.
        *   *One-sample t-test:* Compares a sample mean to a known population mean or hypothesized value.
        *   *Two-sample t-test (Independent):* Compares the means of two independent groups (e.g., dose to OAR in Plan A vs. Plan B for different patient groups).
        *   *Paired t-test:* Compares the means of the same group under two different conditions (e.g., linac output before and after maintenance).
    *   **Analysis of Variance (ANOVA):** Compares the means of three or more groups.
    *   **Chi-Squared (χ²) Tests:** Used for analyzing categorical data.
        *   *Goodness-of-Fit Test:* Tests if observed frequencies match expected frequencies from a hypothesized distribution.
        *   *Test for Independence:* Tests if two categorical variables are associated (e.g., is image quality rating associated with the type of reconstruction algorithm used?).

*   **Solved Example: One-Sample t-test**
    *   **Problem:** The established baseline mean output for a linac is μ₀ = 1.000 cGy/MU. After maintenance, 10 measurements yield a sample mean x̄ = 1.015 cGy/MU with a sample standard deviation s = 0.010 cGy/MU. Is there statistically significant evidence (at α = 0.05) that the mean output has changed?
    *   **Solution:**
        1.  **Hypotheses:**
            *   H₀: μ = 1.000 (Mean output has not changed)
            *   H₁: μ ≠ 1.000 (Mean output has changed - two-tailed test)
        2.  **Significance Level:** α = 0.05
        3.  **Calculate Test Statistic (t):**
            *   t = (x̄ - μ₀) / (s / √n)
            *   t = (1.015 - 1.000) / (0.010 / √10)
            *   t = 0.015 / (0.010 / 3.162) = 0.015 / 0.00316 ≈ 4.74
        4.  **Determine Degrees of Freedom (df):** df = n - 1 = 10 - 1 = 9
        5.  **Find P-value:** Using a t-distribution table or software with df = 9, find the probability of getting a t-statistic as extreme as ±4.74. For t = 4.74 and df = 9, the two-tailed p-value is very small (p < 0.001).
        6.  **Compare P-value to α:** Since p < 0.001 is less than α = 0.05, we reject H₀.
        7.  **Conclusion:** There is statistically significant evidence to suggest that the mean linac output has changed after maintenance.

## Correlation and Regression: Exploring Relationships

These methods analyze the relationship between two or more variables.

*   **Correlation:** Measures the strength and direction of a *linear* association between two continuous variables.
    *   **Pearson Correlation Coefficient (r):** Ranges from -1 to +1.
        *   r = +1: Perfect positive linear relationship.
        *   r = -1: Perfect negative linear relationship.
        *   r = 0: No linear relationship.
    *   **Important Note:** Correlation does not imply causation.
*   **Linear Regression:** Models the linear relationship between a dependent (outcome) variable (Y) and one or more independent (predictor) variables (X).
    *   **Simple Linear Regression:** Y = β₀ + β₁X + ε
        *   β₀: Intercept (value of Y when X=0).
        *   β₁: Slope (change in Y for a one-unit change in X).
        *   ε: Error term.
    *   **Coefficient of Determination (R²):** The proportion of the variance in the dependent variable that is predictable from the independent variable(s). Ranges from 0 to 1.
    *   **Use:** Predicting one variable from another (e.g., predicting detector reading based on dose), modeling trends (e.g., change in beam output over time).

*   **Conceptual Example: Dose vs. Detector Reading**
    *   **Scenario:** A physicist measures the reading of a detector at various known dose levels.
    *   **Analysis:**
        1.  Plot detector reading (Y) vs. dose (X).
        2.  Calculate the correlation coefficient (r) to quantify the strength of the linear relationship (expect r close to +1 for a good detector).
        3.  Perform linear regression to find the best-fit line: Reading = β₀ + β₁ * Dose.
        4.  The slope (β₁) represents the detector sensitivity (reading per unit dose). The intercept (β₀) ideally should be close to zero (zero reading at zero dose).
        5.  R² indicates how well the linear model fits the data (e.g., R² = 0.999 means 99.9% of the variation in readings is explained by the dose).

## Statistical Considerations in Experimental Design

Proper statistical planning *before* data collection is crucial for obtaining meaningful results.

*   **Clear Objectives/Hypotheses:** Define precisely what question the experiment aims to answer.
*   **Sample Size Calculation:** Determine the number of measurements or subjects needed to have sufficient statistical power (probability of detecting a real effect if it exists).
*   **Randomization:** Assigning subjects or experimental units to groups randomly to minimize bias.
*   **Control Groups:** Including a group that does not receive the intervention being tested, for comparison.
*   **Blinding:** Concealing group assignments from subjects or researchers to prevent bias (if applicable).
*   **Appropriate Variables:** Choosing relevant and accurately measurable variables.
*   **Data Management Plan:** Planning how data will be collected, recorded, and stored securely.

## Introduction to Diagnostic Test Evaluation

Statistics are used to evaluate the performance of diagnostic tests or classifiers.

*   **Sensitivity:** The probability that a test correctly identifies individuals *with* the condition (True Positive Rate). Sens = TP / (TP + FN)
*   **Specificity:** The probability that a test correctly identifies individuals *without* the condition (True Negative Rate). Spec = TN / (TN + FP)
*   **Receiver Operating Characteristic (ROC) Analysis:** A graphical plot illustrating the diagnostic ability of a binary classifier system as its discrimination threshold is varied. Plots Sensitivity (True Positive Rate) vs. 1 - Specificity (False Positive Rate).
    *   **Area Under the Curve (AUC):** A measure of the overall performance of the test. AUC = 1 indicates a perfect test; AUC = 0.5 indicates a test no better than chance.
    *   *Use:* Comparing the performance of different diagnostic tests or image analysis algorithms.

## Conclusion

Statistical literacy is a core competency for medical physicists. Descriptive statistics allow for the concise summary of complex data, while probability distributions provide models for understanding inherent randomness in physical processes like radioactive decay and signal detection. Inferential statistics, including hypothesis testing and confidence intervals, enable physicists to draw meaningful conclusions from experimental data and quality assurance measurements, distinguishing real effects from random variation. Correlation and regression help quantify relationships between variables, essential for calibration and modeling. Furthermore, applying statistical principles during experimental design ensures that research and evaluations are conducted rigorously and efficiently. An understanding of concepts like sensitivity, specificity, and ROC analysis is vital for evaluating and implementing diagnostic tools. Ultimately, biostatistics empowers medical physicists to interpret data critically, contribute to evidence-based practice, and ensure the quality and safety of medical procedures involving radiation and imaging.

## ABR-Style Assessment Questions

1.  Daily QA measurements of linac output constancy over a month show a mean of 1.00 cGy/MU and a standard deviation of 0.015 cGy/MU. Assuming a normal distribution, approximately what percentage of measurements would be expected to fall between 0.970 cGy/MU and 1.030 cGy/MU?
    a) 68%
    b) 95%
    c) 99%
    d) 99.7%

2.  A detector measures background counts following a Poisson distribution with an average rate of 2 counts per minute. What is the probability of measuring exactly 3 counts in a one-minute interval?
    a) e⁻² / 3!
    b) (2³ * e⁻²) / 3!
    c) (3² * e⁻³) / 2!
    d) e⁻³ / 2!

3.  A study compares the mean dose to the heart using two different VMAT planning techniques (Technique A vs. Technique B) on the same 20 patients. Which statistical test is most appropriate for determining if there is a significant difference in mean heart dose between the two techniques?
    a) Independent two-sample t-test
    b) Paired t-test
    c) One-way ANOVA
    d) Chi-squared test for independence

4.  A p-value of 0.03 is obtained when testing the null hypothesis that a new imaging filter does not change the average signal-to-noise ratio (SNR). Using a significance level of α = 0.05, what is the appropriate conclusion?
    a) Reject H₀; there is significant evidence the filter changes SNR.
    b) Fail to reject H₀; there is not significant evidence the filter changes SNR.
    c) Accept H₀; the filter definitely does not change SNR.
    d) The result is inconclusive.

5.  A linear regression analysis yields the equation: Y = 5.0 + 2.0*X, with an R² value of 0.81. What percentage of the variance in Y is explained by X?
    a) 20%
    b) 50%
    c) 81%
    d) 90%

**Answers:** 1-d (The range 0.970 to 1.030 represents Mean ± 2*SD, which encompasses approx. 95% of data for a normal distribution. Correction: The range is Mean ± 0.030, which is Mean ± 2*SD (2*0.015=0.030). So 95% is correct. Let me re-evaluate. Ah, the question asks for 0.970 to 1.030, which is mean +/- 0.030. Since SD=0.015, this range is mean +/- 2*SD. Thus, 95% is the correct answer. Let me correct the provided answer key. The original answer 'd' (99.7%) corresponds to +/- 3*SD. The correct answer should be b) 95%.), 2-b (Using Poisson formula P(k) = (λ^k * e^-λ) / k! with λ=2, k=3), 3-b (Data are paired because the same patients are used for both techniques), 4-a (Since p-value 0.03 < α 0.05, we reject the null hypothesis), 5-c (R² directly represents the proportion of variance explained, so 0.81 corresponds to 81%).

**Corrected Answers:** 1-b, 2-b, 3-b, 4-a, 5-c

---
*End of Section 7.2*
