# Continuous Probability Distributions — Industry Applications

An interactive educational web application for undergraduate AIML students. It teaches three fundamental continuous probability distributions through real industry scenarios, with live calculations, input validation, and dynamic visualizations.

## Features

- **Single-file app** — everything runs from one `index.html`; no build step or install needed.
- **Three interactive modules**, each with an industry problem, the math, editable inputs, instant results, and a shaded chart.
- **Live updates** — every calculation and chart refreshes the moment you change an input.
- **Input validation** with clear error messages (e.g. σ must be positive, lower limit < upper limit).
- **Plain-language interpretations** of every result, written for beginners.

## Modules

| Module | Industry scenario | Key concepts |
|--------|-------------------|--------------|
| 1. Normal Distribution | Manufacturing quality control (shaft diameters) | PDF, CDF, specification limits, defect rate |
| 2. Exponential Distribution | Cloud request inter-arrival time | Mean = 1/λ, variance = 1/λ², memoryless property |
| 3. Central Limit Theorem | Warehouse processing time | Sample mean, standard error σ/√n, convergence to normal |

## Getting started

1. Save `index.html` anywhere on your machine.
2. Open it in any modern browser (Chrome, Edge, Firefox, Safari).
3. Use the tabs at the top to switch between the Home page and the three modules.

> **Note:** The app loads two libraries from a CDN, so an internet connection is required on first load:
> - [Chart.js](https://www.chartjs.org/) — renders the interactive charts
> - [MathJax](https://www.mathjax.org/) — typesets the mathematical formulas

## Module 1 — Normal Distribution (Manufacturing Quality Control)

A factory machines steel shafts with a target diameter of 10 mm. Shafts outside the specification limits are defective; the app predicts what fraction of production will be acceptable.

**Illustrative defaults:** μ = 10 mm, σ = 0.05 mm, lower limit = 9.90 mm, upper limit = 10.10 mm.

**Inputs:**
- Mean diameter μ (mm)
- Standard deviation σ (mm)
- Lower specification limit (mm)
- Upper specification limit (mm)
- Selected diameter x (mm)

**Calculations:**
- Probability density at a selected diameter
- P(lower ≤ X ≤ upper) — the acceptable fraction
- P(X < lower) — below the lower limit
- P(X > upper) — above the upper limit
- Expected percentage of defective products

**Formulas:**

\[ f(x) = \frac{1}{\sigma\sqrt{2\pi}}\, e^{-\frac{(x-\mu)^2}{2\sigma^2}} \]

\[ P(a \le X \le b) = \Phi\!\left(\frac{b-\mu}{\sigma}\right) - \Phi\!\left(\frac{a-\mu}{\sigma}\right) \]

**Visualization:** a bell-shaped density curve with the acceptable region shaded green and the two defective regions shaded red (below) and amber (above).

## Module 2 — Exponential Distribution (Cloud Request Inter-arrival Time)

A cloud server receives requests at a constant average rate; the app models the time between consecutive requests to help size the server and plan for bursts.

**Illustrative default:** λ = 12 requests per minute.

**Inputs:**
- Arrival rate λ (requests/min)
- Time threshold t (seconds)
- Conditional times t₂ and t₁ (seconds), with t₂ ≥ t₁

**Calculations:**
- Mean inter-arrival time = 1/λ
- Variance of inter-arrival time = 1/λ²
- P(T ≤ t) = 1 − e^(−λt)
- P(T > t) = e^(−λt)
- P(T > t₂ | T > t₁) = e^(−λ(t₂ − t₁))

Seconds and minutes are converted correctly before any calculation, and units are shown beside every result.

**Formulas:**

\[ f(t) = \lambda e^{-\lambda t}, \quad t \ge 0 \]

\[ P(T \le t) = 1 - e^{-\lambda t}, \qquad P(T > t) = e^{-\lambda t} \]

**Memoryless property:** the exponential distribution "forgets" the past — the probability of waiting at least another t₂ − t₁ seconds, given you have already waited t₁, equals the probability of waiting that long from the start.

**Model assumption:** the model assumes a constant-rate Poisson arrival process. Inter-arrival time is *not* the same as server response time.

## Module 3 — Central Limit Theorem (Warehouse Processing Time)

A warehouse processes orders whose individual times follow an arbitrary distribution. Averaging many orders makes the sample mean approximately normal, which lets the warehouse predict average processing time reliably.

**Illustrative defaults:** μ = 5 min, σ = 2 min, n = 30.

**Inputs:**
- Population mean μ (min)
- Population standard deviation σ (min)
- Sample size n

**Calculations:**
- Mean of the sample mean = μ
- Standard error = σ/√n
- Variance of the sample mean = σ²/n
- P(μ − σ/√n ≤ x̄ ≤ μ + σ/√n) ≈ 68%

**Formulas:**

\[ \text{Mean of } \bar{X} = \mu, \qquad \text{Std error} = \frac{\sigma}{\sqrt{n}} \]

\[ \bar{X} \sim N\!\left(\mu,\; \frac{\sigma^2}{n}\right) \quad \text{for large } n \]

**Key insight:** as n grows, the sampling distribution narrows around μ even when the population is not normal. With n ≥ 30, the normal approximation is typically excellent.

## How the math is implemented

The Normal CDF uses the standard Abramowitz & Stegun approximation for numerical stability. All interval probabilities are computed from the CDF, and chart shading is built from the density values between the relevant bounds.

## Project structure

```
├── index.html      # the entire application (HTML, CSS, and JavaScript)
└── README.md       # this file
```

## Dependencies

- **Chart.js 4.x** (CDN) — interactive charts
- **MathJax 3** (CDN) — math typesetting

No other libraries or build tools are required.

## License

Free to use for educational purposes.