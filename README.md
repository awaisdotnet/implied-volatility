# Implied Volatility Calculator & Volatility Smile Visualisation

## Overview
A numerical implied volatility solver that works backwards from observed market option prices to extract the volatility implied by the market. Demonstrates where Black-Scholes assumptions break down in practice through volatility smile visualisation.

## Mathematical Foundation
Under Black-Scholes, implied volatility should be constant across all strikes. In reality, markets price options with a volatility smile or skew — higher implied volatility for out-of-the-money options. This phenomenon is one of the most well-documented failures of the BSM model.

The implied volatility σ* is found by solving:

C_market = BSM(S, K, T, r, σ*)

using the Brent numerical root-finding method (SciPy), which brackets the solution between near-zero and 1000% volatility and narrows it down until convergence.

## Results
| Strike | Market Price | Implied Vol |
|--------|-------------|-------------|
| 95     | £10.50      | 10.41%      |
| 100    | £8.50       | 14.75%      |
| 105    | £7.00       | 17.43%      |
| 110    | £5.50       | 18.63%      |
| 115    | £4.50       | 20.09%      |
| 120    | £3.50       | 20.74%      |

The upward skew confirms that BSM underprices out-of-the-money calls relative to market prices — a direct violation of the constant volatility assumption.

## Installation
```bash
pip install numpy matplotlib scipy
```

## Usage
```bash
python3 implied_volatility.py
```

## Technologies
- Python 3
- NumPy
- SciPy (Brent root-finding method)
- Matplotlib

## Related Project
Black-Scholes & Monte Carlo Options Pricing — github.com/awaisdotnet/options-pricing

## Author
Awais | University of Leicester | github.com/awaisdotnet
