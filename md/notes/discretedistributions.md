# Discrete Probability Distributions

## Bernoulli Distribution

Let $X$ be a random variable that follows a Bernoulli distribution with success probability $p$, denoted $X \sim \mathrm{Bern}(p)$. Then, 

$$
\mathbb{P}(X = x) = \begin{cases}
p &, x = 0, \\
1 - p &, x = 1, \\
0 &, \text{otherwise.} 
\end{cases}
$$

$X$ models the outcome of a *Bernoulli trial*, that is, a trial with two possible outcomes: success or failure.

### Expectation

Let $X \sim \mathrm{Bern}(p)$. Then,

$$
\mathbb{E}(X) = p.
$$

### Variance

Let $X \sim \mathrm{Bern}(p)$. Then,

$$
\mathrm{Var}(X) = p(1 - p).
$$

## Binomial Distribution

Let $Y_{1}, \dots, Y_{n}$ be identically and independently distributed (i.i.d.) [Bernoulli](#bernoulli-distribution) random variables, denoted $Y_{1}, \dots, Y_{n} \sim \mathrm{Bern}(p)$. Then, 

$$
X = \sum_{k = 1}^{n} Y_{k}
$$ 

is a random variable that follows a binomial distribution with $n$ trials and sucess probability $p$, denoted $X \sim \mathrm{B}(n,p)$. $X$ models the number of successes of $n$ independent Bernoulli trials with success probability $p$. Furthermore, 

$$
\mathbb{P}(X = x) = \begin{cases}
\binom{n}{x} p^{x}(1-p)^{n-x} &, x = 0, \dots, n; \\
0 &, \text{otherwise.} 
\end{cases}
$$

### Expectation

Let $X \sim \mathrm{B}(n,p)$. Then,

$$
\mathbb{E}(X) = np.
$$

The easiest way to derive the expectation (and variance) of a binomial random variable is using that for the [Bernoulli random variable](#bernoulli-distribution).

### Variance

Let $X \sim \mathrm{B}(n,p)$. Then,

$$
\mathrm{Var}(X) = np(1 - p).
$$

## Geometric Distribution

Let $X$ be a random variable that follows a geometric distribution with success probability $p$, denoted $X \sim \mathrm{Geom}(p)$. Then, 

$$
\mathbb{P}(X = x) = \begin{cases}
p(1-p)^{x - 1} &, x \in \{ 1, 2, \dots \}, \\
0 &, \text{otherwise.} 
\end{cases}
$$

$X$ models the number of independent Bernoulli trials up to and including the first success.

### Expectation

Let $X \sim \mathrm{Geom}(p)$. Then, 

$$
\mathbb{E}(X) = \frac{1}{p}.
$$

#### Proof

By the definition of the expectation of a random variable,

$$
\mathbb{E}(X) = \sum_{x = 1}^{\infty} x\mathbb{P}(X = x).
$$

Then, using $\mathbb{P}(X = x) = p(1-p)^{x-1}$ for $x \in \{ 1, 2, \dots \}$,

\begin{align}
    \mathbb{E}(X) &= \sum_{x = 1}^{\infty} xp(1-p)^{x - 1} \\
    &= p \sum_{x = 1}^{\infty} x(1-p)^{x - 1} \\
    &= p \bigl( 1 + 2(1-p) + 3(1-p)^{2} + 4(1-p)^{3} + \dots \bigr) \\
    & \begin{aligned}
        &= p \Bigl( \bigl( 1 + (1-p) + (1-p)^{2} + (1-p)^{3} + \dots \bigr) \\ 
        & \quad + \bigl( (1-p) + (1-p)^{2} + (1-p)^{3} + (1-p)^{4} + \dots \bigr) \\ 
        & \quad + \bigl( (1-p)^{2} + (1-p)^{3} + (1-p)^{4} + (1-p)^{5} + \dots \bigr) \\
        & \quad + \dots \Bigr) 
    \end{aligned} \\
    & \begin{aligned}
        &= p \Bigl( \bigl( 1 + (1-p) + (1-p)^{2} + (1-p)^{3} + \dots \bigr) \\
        & \quad + (1-p)\bigl( 1 + (1-p) + (1-p)^{2} + (1-p)^{3} + \dots \bigr) \\
        & \quad + (1-p)^{2}\bigl( 1 + (1-p) + (1-p)^{2} + (1-p)^{3} + \dots \bigr) \\
        & \quad + \dots \Bigr ).
    \end{aligned}
\end{align}

We can factorise this expression by taking out $\bigl(1 + (1-p) + (1-p)^{2} + (1-p)^{3} + \dots \bigr)$, which gives

$$
\begin{align}
    \mathbb{E}(X)
    &= p \bigl( 1 + (1-p) + (1-p)^{2} + (1-p)^{3} + \dots \bigr) \bigl( 1 + (1-p) + (1-p)^{2} + (1-p)^{3} + \dots \bigr) \\
    &= p \left( \sum_{n=0}^{\infty} (1-p)^{n} \right)^{2}.
\end{align}
$$

Finally, since $\sum_{n=0}^{\infty} r^{n} = \frac{1}{1-r}$ for $|r| < 1$, 

$$
\begin{align}
    \mathbb{E}(X)
    &= p \left( \frac{1}{1 - (1 - p)} \right)^{2} \\
    &= \frac{1}{p}.
\end{align}
$$

## Poisson Distribution