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


# Discrete Probability Distributions

Lab Program 2 - SDAV Lab (Sem 3)
Name: Krish Kumar Ravidas

Web app for Binomial, Poisson and Geometric distributions. You enter the values and it shows mean, variance, std dev, E[X²], skewness, PMF, CDF and a bar graph.

## How to run
Open index.html in a browser. Thats it.

---

## Use Case 1 - Manufacturing Quality Control

**Binomial n=20, p=0.05**
- mean = 1
- variance = 0.95
- P(X=2) = 0.1887
- graph is skewed to the right, most bars at 0 and 1 defects

- <img width="1026" height="380" alt="image" src="https://github.com/user-attachments/assets/8d1f0a34-5ead-46c9-9cb7-867f32b81175" />


**Changed p to 0.10**
- mean becomes 2, P(X=2) = 0.2852
- graph shifts right and gets wider

<img width="1026" height="380" alt="image" src="https://github.com/user-attachments/assets/2e5e1b14-46d9-4afe-8720-8179361a8db8" />



**Poisson λ=5**
- P(X=3) = 0.1404
- Binomial(100, 0.05) gives 0.1396 so almost the same, Poisson works as approximation when p is small

- <img width="1026" height="380" alt="image" src="https://github.com/user-attachments/assets/c5e59099-a956-4a3c-8065-952f1f7a78d3" />


**Geometric p=0.05**
- mean = 20 inspections
- P(X=1) = 0.05
- bars keep going down, long tail on the right

**Inference:** defects are rare at p=0.05 (about 1 per batch of 20). If p doubles the defects go up a lot, so the defect rate needs monitoring.
<img width="1026" height="380" alt="image" src="https://github.com/user-attachments/assets/8237b4ae-ed89-4cc0-95ad-73886080b4bd" />


---

## Use Case 2 - Cloud Ops and Cybersecurity

Data: 1200 requests, 27 failed so p = 27/1200 = 0.0225. 36 alerts in 12 intervals so λ = 3.

**Binomial n=100, p=0.0225**
- mean = 2.25
- variance = 2.1994
- P(X=3) = 0.2026
- P(X≤3) = 0.8112

- <img width="1026" height="380" alt="image" src="https://github.com/user-attachments/assets/ce2f1da7-2733-4e49-b8bb-3e099acf9a7c" />


**Poisson λ=3**
- P(X=0) = 0.0498, P(X=1) = 0.1494, P(X=2) = 0.2240, P(X=3) = 0.2240
- P(X=5) = 0.1008
- P(4 or more) = 0.3528

**Comparing λ = 2, 3, 5**
- bigger λ means graph moves right and gets flatter and wider
- P(5 or more alerts): λ=2 → 0.0527, λ=3 → 0.1847, λ=5 → 0.5595

- <img width="1026" height="380" alt="image" src="https://github.com/user-attachments/assets/224ef814-f4a1-4d53-8c5e-b91f33eef5e5" />


**Geometric p=0.8**
- mean = 1.25
- P(X=1) = 0.8, P(X=2) = 0.16, P(X=3) = 0.032
- P(success within 3 tries) = 0.992

- <img width="1026" height="380" alt="image" src="https://github.com/user-attachments/assets/12283333-43b4-4bfd-be35-e2ae3aeaf416" />


**Inference:**
- 6 or more alerts in 10 min only happens about 8% of the time so it can be used as a threshold
- more than 3 failures in 100 requests is about 19%, so its normal. Only very high counts (7+) need investigating
- 3 retries is enough since 99.2% succeed by then
- p=0.8 is just assumed, in a real outage retries are not independent so it can be wrong

---
