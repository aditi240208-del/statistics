
## Experiments 

### 1. Statistics Basics
The marks array is used to calculate the mean, max, min, and standard deviation. The table of student marks is created using the pandas library, and the bar chart is created using Matplotlib.

**Observations:**
-  If you increase a mark, this will normally increase the mean, and if you decrease a mark, this will normally decrease it.
- The highest and lowest change when a new highest or lowest mark is put in.
- Standard deviation depends on how spread out the marks are.
- Changing table marks changes bar heights and changes the mean.
  
### 2. Coin-Toss Simulation (Experimental) 
Python random module is used to generate random values and to choose random outcomes. In this experiment, it can be used to simulate coin tosses by randomly choosing between heads and tails.

The NumPy (numpy) library is for calculating math and working with arrays. It includes functions such as np.random.choice() for making random selections and np.mean() for calculating the average of numerical values.

**Observations:**
- The estimated probability may vary a lot with a small number of tosses.
- With more tosses, the estimate will move closer to the theoretical probability of 0.5.
- The result is random, so it will not necessarily get closer with every increase in the number of tosses.
  
### 3. Dice-Roll Probability
Random dice rolls are used to estimate the probability of outcomes and events, such as rolling a six, an even number, or a number greater than three.

**Observations:**
- A small number of rolls gives an estimate far from the theoretical probability.
- More rolls generally produce a probability nearer to the theoretical probability.
- For a fair die, the theoretical probability of rolling any one specified face is 1/6.
- Changing the number of dice rolls affects how closely the experimental probability approaches the theoretical probability.
- A plot shows how the cumulative probability of getting Heads changes over 10,000 simulated coin tosses compared with the theoretical probability of 0.5.
- The logarithmic horizontal axis helps display changes across both small and large numbers of tosses.

### 4. Conditional Probability
Probability calculations are performed using student and language preference data, sports events involving cricket and football, and outcomes from coin tosses and dice rolls.

**Observations:**
- An increase in the number of favorable events while keeping the number of events constant will increase the probability of the event.
- Conditional probability is the probability of an event happening when another event has already taken place.
- For events A and B, the general formula is P(A | B) = P(A ∩ B) / P(B), provided P(B) > 0.
- The addition rule is P(A ∪ B) = P(A) + P(B) - P(A ∩ B).

### 5. Bayes' Theorem
Calculate the probability of having a disease when the test comes out positive and the probability of an email being spam, provided the email has the word "offer".

**Observations:**
- The final probability depends on the initial probability and the available evidence.
- A positive test does not automatically mean a person has the disease, as the initial probability and false-positive rate also affect the result.
- For the email classification, changing the initial probability of spam or the conditional probabilities changes the probability that the email is spam.

### 6. Binomial Distribution
The plot in the notebook shows the probability mass function (PMF) for a binomial random variable with n = 20 trials and probability of success p = 0.5.
**Observations:**
- n determines the number of trials and the possible number of successes between 0 and n.
- p determines the probability of success in each trial.
- If p = 0.5, the distribution will be symmetric about n/2.

### Conclusion
These experiments show how Python can be used in statistics to simulate random events, estimate probabilities, visualize distributions, and apply conditional probability and Bayes' theorem. Changing the input data, trial count, or probability parameters shows how the results respond to different conditions.
