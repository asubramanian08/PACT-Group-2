# <p style="text-align:center"> **PACT Homework 3** </p>
1. <br>

    * a) Markov's inequality states: $P(X \ge a) \le \frac{E(X)}a$.

        Let $X$ be a random variable where $P(X = x) = \begin{cases} 1/2 & x = 5 \\ 1/2 & x = 5 \end{cases}$

        (Incorrectly) applying Markov's inequality, $P(X \ge 1) \le \frac{E(X)}{1}$. Since $E(X) = 0$, this implies that $P(X \ge 1) 0$. This is not true since $P(X = 5) = 1/2$.

        This is an example of how markov's bound can't be applied to negative random variables.
    * b) Given that $Z$ is a r.v. such that, $P(Z \ge -10)=1$ and $E(Z) = 0$. Let $Y = Z + 10$ meaning $E(Y) = 10$. Applying Markov's on $Y$:
        $$P(Y \ge 15) \le \frac{E(Y)}{15} \le \frac{10}{15} \le \frac23$$

        Since $P(Z \ge 5) = P(Y \ge 15)$, we know $P(Z \ge 5) \le \frac23$.
2. Let $X$ be the random variable for the sum off all $200$ dice. We want to find $P(X > 800)$. Applying Chebyshev's: $P(X > 800) \le P(|X - 700| \ge 101) \le \frac{\text{Var}(X)}{101^2}$. Since $X = \sum_{i=1}^{200} X_i$ and $\text{Var}(X_i) = \frac{35}{12}$, $\text{Var}(X) = 200 \times \frac{35}{12} = \frac{1750}{3}$. Substituting in, $\frac{\text{Var}(X)}{101^2} = \frac{1750}{3 \times 10201} \approx 0.057$.
3. $P(5 \le X \le 15) = 1 - P(X < 5) + P(X > 15) = 1 - P(|X - 10| > 5)$ Applying Chebyshev's, $P(5 \le X \le 15) \ge  1 - \frac{\text{Var}(X)}{5^2}$. Since its given that $\text{Var}(X) = 15$, $P(5 \le X \le 15) \ge 1 - \frac{15}{25} \ge \frac25$.
4. <br>

    * a) Using Markov's:

        $$P(X \ge 135000) \le \frac{E(X)}{135000} \le \frac{100000}{135000} \le \frac{20}{27}$$
    * b) Let $X$ be a random variable so that $P(X = s) = \begin{cases} \frac{20}{27} & s = 135000 \\ \frac{7}{27} & s = 0 \end{cases}$. Here, $E(X) = \frac{20}{27} \times 135000 + \frac7{27} \times 0 = 100000$. Thus the above bound is tight since $P(X \ge 135000) = \frac{20}{27}$.
    * c) Let $Y$ be a random variable so that $Y = X - 70000$. We know that $Y$ is non-negative since $P(X \ge 70000) = 1$. Note: Since $E(X) = 100000$, we know that $E(Y) = E(X) - 70000 = 30000$. Applying Markov's: $P(X \ge 135000) = P(Y \ge 65000) \le \frac{E(T)}{65000} \le \frac{30000}{65000} \le \frac{6}{13}$.

        Consider when: $P(X = s) = \begin{cases} \frac{6}{13} & s = 135000 \\ \frac{7}{13} & s = 70000 \end{cases}$. Here $E(X) = 100000$ and $P(X \ge 135000) = \frac{6}{13}$, when proves that the bound is tight.
    * d) Given that the standard deviation of $X$ is $5$, we know that $\text{Var}(X) = 25$. Again, let $Y = X - 70000$. The same observation as in part c) can be applied to $Y$. In addition, we know $\text{Var}(X) = \text{Var}(Y) = 25$. Applying Chebyshev's: $P(X \ge 135000) = P(Y \ge 65000) \le P(|Y - 30000| \ge 35000) \le \frac{\text{Var}(Y)}{35000^2} \le \frac{25}{35000^2} \le \frac1{49e6}$.
5. <br>

    * a) Let $X_i$ be a random variable that is $1$ or $0$ depending on weather or not the $i^\text{th}$ edge is in the max cut. Using linearity of expectation: $E(X) = \sum_i E(X_i) = \sum_i P(X_i = 1) = \sum_i \frac12$. Let $m$ be $|E|$, or the number of edges. Since $m \ge \text{OPT}$, $E(X) = \frac{m}2 \ge \frac{\text{OPT}}2$.
    * b - d) Not sure how to answer these questions.
    * e) Run the algorithm until the answer received is $\ge \frac{49}{100} \text{OPT}$. The expected number of iterations is $51$ since $p \ge \frac{1}{51}$.
6. Let $S$ be the event that the merchant is sleazy and $H$ be the event that it is honest. Note: $P(S) + P(H) = 1$. Then,

    $$P(X = 1) = P(X = 1 \cap S) + P(X = 1 \cap H) \\
    = P(S)P(X = 1 \mid S) + P(H)P(X = 1 \mid H) \\
    = 0.9 \times \frac1{20} + 0.1 \times \frac1{1000} \\
    = \frac{451}{10^4}$$
    
    Note that $P(Y=1)$ also $= \frac{451}{10000}$ for the exact same reason as above.

    $$P(X = 1 \cap Y = 1) = P(X = 1 \cap Y = 1 \cap S) + P(X = 1 \cap Y = 1 \cap H) \\
    = P(S)P(X = 1 \cap Y = 1 \mid S) + P(H)P(X = 1 \cap Y = 1 \mid H) \\
    = 0.9 \times \left(\frac1{20}\right)^2 + 0.1 \times \left(\frac1{1000}\right)^2 \\
    = \frac{2251}{10^7}$$

    Since $P(X = 1)P(Y = 1) \neq P(X = 1 \cap Y = 1)$, we know that $X$ and $Y$ are not independent.
7. Let $X$ be the random variable denoting how many students show up for the test. We want to find $P(X \le 50)$:

    $$P(X \le 50) = 1 - P(X = 51) + P(X = 52)$$

    Since each student has a $90\%$ chance of showing up:

    $$P(X \le 50) = 1 - \binom{52}{51}(0.95)^{51}0.05^1 - \binom{52}{52}(0.95)^{52}0.05^0 \\
    = 1 - (52)(0.95)^{52}(0.05) - (0.95)^52 \\
    \approx 0.741$$
8. Not sure, read the solution.