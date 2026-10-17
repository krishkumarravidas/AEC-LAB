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

-<img width="1024" height="372" alt="image" src="https://github.com/user-attachments/assets/76ab512d-7bf1-4858-822c-37dacd360ce3" />
 


**Changed p to 0.10**
- mean becomes 2, P(X=2) = 0.2852
- graph shifts right and gets wider

-<img width="1024" height="372" alt="image" src="https://github.com/user-attachments/assets/95c748ae-4c3f-4816-bd87-a03f7d87aaa1" />


**Poisson λ=5**
- P(X=3) = 0.1404
- Binomial(100, 0.05) gives 0.1396 so almost the same, Poisson works as approximation when p is small

- <img width="1024" height="372" alt="image" src="https://github.com/user-attachments/assets/fb0df606-9459-4aac-ba13-a69d5a51ece5" />


**Geometric p=0.05**
- mean = 20 inspections
- P(X=1) = 0.05
- bars keep going down, long tail on the right

**Inference:** defects are rare at p=0.05 (about 1 per batch of 20). If p doubles the defects go up a lot, so the defect rate needs monitoring.
- <img width="1024" height="372" alt="image" src="https://github.com/user-attachments/assets/86be3c59-6208-46c5-abe9-c5f25b9d375c" />



---

## Use Case 2 - Cloud Ops and Cybersecurity

Data: 1200 requests, 27 failed so p = 27/1200 = 0.0225. 36 alerts in 12 intervals so λ = 3.

**Binomial n=100, p=0.0225**
- mean = 2.25
- variance = 2.1994
- P(X=3) = 0.2026
- P(X≤3) = 0.8112

- <img width="1024" height="372" alt="image" src="https://github.com/user-attachments/assets/1d1e731c-ce8c-4b7c-a0a1-f9af5369f08c" />


**Poisson λ=3**
- P(X=0) = 0.0498,P(X=1) = 0.1494, P(X=2) = 0.2240, P(X=3) = 0.2240
- <img width="1024" height="372" alt="image" src="https://github.com/user-attachments/assets/bc4d1c28-6188-4349-a197-26721d38d231" />

- P(X=5) = 0.1008
- P(4 or more) = 0.3528

**Comparing λ = 2, 3, 5**
- bigger λ means graph moves right and gets flatter and wider
- P(5 or more alerts): λ=2 → 0.0527
- <img width="1024" height="372" alt="image" src="https://github.com/user-attachments/assets/ebae22cc-5c8e-405b-b578-556c4a8e247d" />
 - λ=3 → 0.1847
- <img width="1024" height="372" alt="image" src="https://github.com/user-attachments/assets/d9e2271e-471f-4b4f-9ac7-23c495c16e73" />
 - λ=5 → 0.5595
 - <img width="1024" height="372" alt="image" src="https://github.com/user-attachments/assets/a85d40f8-f745-4751-8654-26d64b09f18d" />


- 

**Geometric p=0.8**
- mean = 1.25
- P(X=1) = 0.8, P(X=2) = 0.16, P(X=3) = 0.032
- P(success within 3 tries) = 0.992

- <img width="1024" height="372" alt="image" src="https://github.com/user-attachments/assets/952cfbf1-2778-4dd4-8a22-f056ea820cc5" />


**Inference:**
- 6 or more alerts in 10 min only happens about 8% of the time so it can be used as a threshold
- more than 3 failures in 100 requests is about 19%, so its normal. Only very high counts (7+) need investigating
- 3 retries is enough since 99.2% succeed by then
- p=0.8 is just assumed, in a real outage retries are not independent so it can be wrong

---
