# Discrete Probability Distributions

An interactive educational web app for the Statistics and Skill Lab (undergraduate AIML). It lets students explore how discrete probability distributions behave, starting with the **Binomial distribution**.

Plain HTML, CSS and JavaScript. No installation, build step or libraries needed.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The lab application (Home page + Binomial module) |
| `homework.html` | Homework Exercise 1 (Binomial) and Exercise 2 (Poisson), kept separate from the lab app |

## Run it

Open `index.html` (or `homework.html`) in any modern browser by double-clicking it.

To publish on GitHub Pages: **Settings → Pages → Deploy from branch → `main` / root**. The app is then available at `https://<your-username>.github.io/<repo-name>/`.

## Lab application (`index.html`)

Header navigation: **Home** and **Binomial**. Poisson and Geometric are listed on the Home page as "Coming soon".

### Binomial module

X ~ Binomial(n, p) is the number of successes in n independent trials, each with success probability p.

- **Inputs:** number of trials `n` (default 20) and probability of success `p` (default 0.35). `n` must be a positive integer and `p` must be between 0 and 1. The selected values are displayed clearly.
- **Statistics cards:**

  | Statistic | Formula |
  |-----------|---------|
  | Mean | `np` |
  | Variance | `np(1-p)` |
  | Standard deviation | `sqrt(np(1-p))` |
  | Second moment E[X²] | `Variance + Mean²` |
  | Skewness | `(1-2p) / sqrt(np(1-p))` |

  For the defaults n = 20, p = 0.35 the app verifies mean = 7 and variance = 4.55.
- **PMF calculator:** enter `k` (0 ≤ k ≤ n) to get `P(X=k) = C(n,k) p^k (1-p)^(n-k)`, with the substituted formula and a one-line explanation.
- **CDF calculator:** enter `k` to get `P(X <= k)` and `P(X > k) = 1 - P(X <= k)`.
- **PMF bar chart:** probabilities for X = 0, 1, ..., n, with a dashed vertical line at the mean and a hover tooltip (`X = value`, `P(X=value) = probability`). It updates automatically when `n` or `p` changes.

## Homework (`homework.html`)

**Exercise 1: Binomial, n = 15, p = 0.6**

| Question | Result |
|----------|--------|
| Mean | 9 |
| Variance | 3.6 |
| P(X = 9) | 0.206598 |
| P(X ≤ 10) | 0.782722 (so P(X > 10) = 0.217278) |
| Highest probability | k = 9 (about 0.2066), the tallest bars are at k = 8 to 10 |

Inference: the distribution has a single peak at the mean, is slightly left-skewed because p > 0.5, and about 78% of outcomes are 10 successes or fewer.

**Exercise 2: Poisson, λ = 6**

| Question | Result |
|----------|--------|
| Mean | 6 |
| Variance | 6 |
| P(X = 8) | 0.103258 |
| P(X ≤ 5) | 0.445680 |

The page also compares the Poisson PMF for λ = 2, 6 and 10. As λ increases, the distribution shifts right, becomes wider (σ = √λ), its peak gets lower, and its shape becomes more symmetric and bell-like.

## Formulas used

- Binomial: `P(X=k) = C(n,k) p^k (1-p)^(n-k)`, mean `np`, variance `np(1-p)`
- Poisson: `P(X=k) = e^(-λ) λ^k / k!`, mean `λ`, variance `λ`

## Author

Name:Krish Kuamr Ravi Das
Roll number: 26UG1BYAI402-T
Guide: Sanjay M
