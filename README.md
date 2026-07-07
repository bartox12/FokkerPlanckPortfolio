# Modeling the Evolution of Wealth — a Fokker–Planck Approach to Portfolio Risk

Instead of simulating thousands of random price paths, this project propagates the **entire probability density** of portfolio wealth through time by numerically solving the **Fokker–Planck equation** — and derives goal-attainment probabilities, tail risk and allocation trade-offs directly from the density.

Course project for Partial Differential Equations.

## The idea

Wealth follows geometric Brownian motion, so its log is Gaussian and the exact density is known in closed form — a perfect benchmark. The Fokker–Planck equation for log-wealth has constant coefficients and is solved with finite differences; every numerical result is validated against the analytic solution.

## What the notebook covers

1. **Market model** — GBM wealth dynamics and base-case parameters
2. **Closed-form benchmark** — the exact log-normal law used for validation
3. **Finite-difference solvers** — explicit and Crank–Nicolson schemes in log-coordinates
4. **Validation** — max-norm error against the exact Gaussian over a 10-year horizon
5. **Convergence study** — spatial accuracy under grid refinement (2nd order for Crank–Nicolson)
6. **Monte-Carlo cross-check** — independent SDE simulation agrees with the PDE solution
7. **Density propagation** — how a near-point mass spreads and skews into the terminal log-normal
8. **Risk metrics by quadrature** — probability of reaching a wealth goal, 5th-percentile downside, expected shortfall
9. **Asset allocation** — equity/risk-free mix mapped to drift and volatility of the portfolio
10. **Risk–reward trade-off** — sweeping the equity weight to trace goal probability vs downside risk

## Setup

Requires [uv](https://docs.astral.sh/uv/):

    uv sync
    uv run jupyter lab fokker_planck_portfolio.ipynb

Dependencies: NumPy, SciPy, Matplotlib.

## Authors

Arche & Bartłomiej Mielcarz
