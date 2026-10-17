# Discrete Probability Distributions — Binomial, Poisson & Geometric

## Overview
This Jupyter Notebook explores three discrete probability distributions: Binomial, Poisson, and Geometric. It calculates statistical measures and probabilities, and uses graphs to show how the distributions behave.

## Libraries Used
- **NumPy (`numpy`)**: Creates numerical arrays and generates random observations for simulations.
- **Matplotlib (`matplotlib.pyplot`)**: Creates bar charts and line plots to visualize probability distributions.
- **SciPy (`scipy.stats`)**: Provides distribution functions for calculating probabilities, means, variance, moments, skewness, and cumulative probabilities.

A fixed random seed (`np.random.seed(42)`) is set to make random simulation results reproducible when the same sequence of operations is run.

## 1. Binomial Distribution
The Binomial distribution models the number of successes in a fixed number of independent trials when each trial has the same probability of success.

**Parameters used:**
- Number of trials: `n = 20`
- Probability of success: `p = 0.35`

**Calculations performed:**
- Mean
- Variance
- Second moment, `E[X²]`
- Skewness
- Cumulative probability of at most 10 successes, `P(X ≤ 10)`
- Probability of exactly 7 successes, `P(X = 7)`

The notebook plots the probability mass function (PMF) as a bar chart and marks the mean with a dashed vertical line.

### Observations
- The mean is `np = 20 × 0.35 = 7`, so the expected number of successes is 7.
- The PMF shows the probabilities for each possible number of successes from 0 to 20.
- The bars around the mean represent the more likely success counts, while probabilities become smaller toward the extremes.
- The cumulative probability `P(X ≤ 10)` represents the chance of getting 10 or fewer successes.

## 2. Poisson Distribution
The Poisson distribution models the number of events occurring in a fixed interval when the average event rate is represented by `λ`.

**Values used:** `λ = 1, 3, 5, 10`

For each value of `λ`, the notebook:
- Creates a Poisson distribution.
- Generates 5,000 random observations.
- Compares the theoretical mean with the mean calculated from the simulated observations.
- Plots the PMFs for the different values of `λ` on the same graph.

### Observations
- The theoretical mean of a Poisson distribution is equal to `λ`.
- The simulated mean may differ slightly from the theoretical mean because the observations are random.
- As the number of simulated observations increases, the simulated mean will generally tend to be closer to the theoretical mean.
- Increasing `λ` shifts the distribution toward larger event counts and increases its spread.

## 3. Geometric Distribution
The Geometric distribution models the trial number on which the first success occurs, assuming independent trials with a constant probability of success.

**Parameter used:** `p = 0.3`

**Calculations performed:**
- Mean, `1/p`
- Probability that the first success occurs on the first trial, `P(X = 1)`
- Probability that the first success occurs after the fifth trial, `P(X > 5)`

The notebook plots the PMF for trial numbers from 1 to 19.

### Observations
- The mean is `1/p`, which is approximately `3.3333` for `p = 0.3`.
- The probability of success on the first trial is `0.3`.
- The probability decreases as the required trial number increases because success must not occur on any earlier trial.
- A larger success probability would make an early first success more likely and reduce the expected number of trials.

## Conclusion
The notebook demonstrates how the Binomial, Poisson, and Geometric distributions describe different types of discrete random outcomes. Numerical calculations and graphs help compare probabilities, understand expected values, and observe how distribution shapes change with their parameters.

## How to Run
1. Open the notebook in Jupyter Notebook, JupyterLab, or another compatible notebook environment.
2. Ensure that `numpy`, `matplotlib`, and `scipy` are installed.
3. Run the code cells in order.
4. Review the printed results and the generated graphs.

Install the required libraries if needed:

```bash
pip install numpy matplotlib scipy
```
