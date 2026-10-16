# Statistics and Probability Experiments

## Overview
This Jupyter Notebook (`statistics.ipynb`) contains Python programs for exploring basic statistics, probability, random experiments, conditional probability, Bayes' theorem, and the binomial distribution.

## Requirements
- Python 3
- Jupyter Notebook or JupyterLab
- NumPy
- Pandas
- Matplotlib
- SciPy

Install the required libraries if they are not already installed:

```bash
pip install numpy pandas matplotlib scipy
```

## How to Run
1. Open `statistics.ipynb` in Jupyter Notebook or JupyterLab.
2. Run the cells from top to bottom.
3. Change the input values or parameters in a cell.
4. Run that cell again to observe how the output changes.

## Experiments Included

### 1. Descriptive Statistics
A marks array is used to calculate the mean, maximum, minimum, and standard deviation. Pandas is also used to create a table of student marks and Matplotlib displays them as a bar chart.

**What to observe when values change:**
- Increasing a mark usually increases the mean; decreasing a mark usually decreases it.
- The maximum and minimum change when a new highest or lowest mark is entered.
- Standard deviation changes according to how spread out the marks are.
- Changing the marks in the table changes the bar heights and may change the mean.

### 2. Coin-Toss Simulation and Experimental Probability
The notebook simulates coin tosses and estimates the probability of getting heads.

**What to observe when the number of tosses changes:**
- With a small number of tosses, the estimated probability can vary a lot.
- With more tosses, the estimate will generally tend to move closer to the theoretical probability of 0.5.
- The result is random, so it will not necessarily get closer with every increase in the number of tosses.
- Re-running a simulation can produce a different result unless a random seed is fixed.

### 3. Dice-Roll Probability
Random dice rolls are used to estimate the probability of outcomes and events, such as rolling a six, an even number, or a number greater than three.

**What to observe when the number of rolls changes:**
- A small number of rolls can give an estimate far from the theoretical probability.
- More rolls generally produce a more stable estimate.
- For a fair die, the theoretical probability of rolling any one specified face is `1/6`.
- Changing the event condition changes which rolls count as successes and therefore changes the estimated probability.

### 4. Basic, Joint, and Conditional Probability
Examples use student and language-preference counts, as well as events involving cricket and football. Other cells calculate probabilities for events defined on coin tosses and dice rolls.

**What to observe when probabilities or counts change:**
- Increasing the number of outcomes in an event while keeping the total fixed increases that event's probability.
- Conditional probability depends on the event being conditioned on.
- For events A and B, the general formula is `P(A | B) = P(A ∩ B) / P(B)`, provided `P(B) > 0`.
- The addition rule is `P(A ∪ B) = P(A) + P(B) - P(A ∩ B)`. The intersection must be subtracted to avoid counting shared outcomes twice.

### 5. Law of Large Numbers
A plot tracks the cumulative simulated probability of heads across 10,000 tosses and compares it with the theoretical value of 0.5.

**What to observe:**
- The cumulative probability fluctuates more at the beginning.
- As the number of tosses increases, the estimate generally settles nearer to 0.5.
- The logarithmic horizontal axis makes it easier to view both early and later tosses.

### 6. Bayes' Theorem
Two examples estimate the probability of a disease given a positive test and the probability that an email is spam given that it contains the word “offer”.

**What to observe when values change:**
- The posterior probability depends on the prior probability and the likelihoods.
- A positive test does not automatically mean the person has the disease; the prior probability and false-positive rate also matter.
- For the email example, changing the spam prior or either conditional likelihood changes the calculated probability that the email is spam.

### 7. Binomial Distribution
The notebook plots the probability mass function (PMF) for a binomial random variable using `n = 20` trials and success probability `p = 0.5`.

**What to observe when parameters change:**
- `n` controls the number of trials and the possible number of successes, from `0` to `n`.
- `p` controls the chance of success on each trial.
- When `p = 0.5`, the distribution is symmetric around `n/2`.
- When `p` is below 0.5, probability tends to be concentrated at lower success counts; when `p` is above 0.5, it tends to be concentrated at higher success counts.
- Increasing `n` adds more possible success counts and changes the shape of the distribution.

## Important Notes
- Simulated probabilities can vary between runs. Treat them as estimates rather than exact theoretical values.
- In cells that use random simulations, results depend on the generated random sample. A fixed random seed makes a simulation reproducible.
- Review the conditional-probability input cell before relying on its result: its current expression `(a*b)/b` simplifies to `a` when `b` is nonzero, and does not calculate conditional probability in general. Use the joint probability `P(A ∩ B)` divided by `P(B)` instead.
- In the dice-frequency cell, the `print` statement is outside the loop, so it prints only the final face's count and probability. To display every face, indent the `print` statement inside the loop.

## Conclusion
These experiments demonstrate how Python can be used to calculate descriptive statistics, simulate random events, estimate probabilities, visualize distributions, and apply conditional probability and Bayes' theorem. Changing the input data, trial count, or probability parameters helps show how the results respond to different conditions.
