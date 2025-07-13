# Option Pricing Methods in Computational Finance

This project demonstrates the implementation and comparison of various computational methods for exotic option pricing, including binary options, barrier options, and Heston model calibration. The project combines theoretical derivations with practical implementations using Monte Carlo simulation, finite difference methods, and analytical formulas.

## Project Structure

### Notebooks

- **`binary_options_pricing.ipynb`** - Binary/digital option pricing using Monte Carlo simulation and finite difference methods
- **`heston_model_calibration.ipynb`** - Heston stochastic volatility model calibration to SP500 implied volatility surfaces
- **`barrier_options_pricing.ipynb`** - Up-and-out barrier option pricing with discrete monitoring adjustments

### Data Files

- **`data/raw_ivol_surfaces.npy`** - Raw implied volatility surface data for SP500 options
- **`data/interp_ivol_surfaces.npy`** - Interpolated implied volatility surfaces for model calibration
- **`plots/`** - Directory containing generated plots and visualizations

## Key Features

### 1. Binary/Digital Options (`binary_options_pricing.ipynb`)

- **Monte Carlo Simulation**: Implementation of Euler and Milstein schemes for Geometric Brownian Motion
- **Finite Difference Methods**: Implicit and Crank-Nicolson schemes for solving the Black-Scholes PDE
- **Analytical Benchmarking**: Comparison with closed-form Black-Scholes solutions
- **Sensitivity Analysis**: Study of convergence and numerical stability

**Key Methods:**

- `simulate_gbm_paths()` - Monte Carlo path simulation
- `MS_binary_price()` - Binary option pricing via Monte Carlo
- `analytical_binary_price()` - Analytical Black-Scholes formula
- `implicit()` - Implicit finite difference solver
- `crank_nicolson()` - Crank-Nicolson finite difference solver

### 2. Heston Model Calibration (`heston_model_calibration.ipynb`)

- **Semi-Analytical Pricing**: Characteristic function approach for Heston model option pricing
- **Monte Carlo Simulation**: Quadratic Exponential (QE) scheme for Heston process simulation
- **Market Data Calibration**: Fitting Heston parameters to real SP500 implied volatility surfaces
- **Surface Visualization**: 3D plotting of implied volatility surfaces

**Key Methods:**

- `HestonPrice()` - Semi-analytical Heston option pricing using characteristic functions
- `simulate_heston_QE()` - Monte Carlo simulation with Quadratic Exponential scheme
- Surface plotting and comparison between market and model-implied volatilities
- Calibration optimization with error metrics

### 3. Barrier Options (`barrier_options_pricing.ipynb`)

- **Analytical Formulas**: Exact pricing for continuous monitoring up-and-out barrier options
- **Discrete Monitoring**: Adjustment techniques for realistic discrete barrier monitoring
- **Monte Carlo Validation**: Comparison between analytical and simulated prices
- **Convergence Analysis**: Study of discretization effects and Monte Carlo convergence

**Key Methods:**

- `analytical_barrier_option()` - Exact formula for continuously monitored barriers
- `analytical_barrier_option_adjusted()` - Discrete monitoring adjustment
- `mc_barrier_option_price()` - Monte Carlo pricing with discrete monitoring
- `convergence_analysis_timesteps()` - Analysis of time discretization effects

## Requirements

```python
numpy
scipy
matplotlib
dataclasses
typing
```

## Usage

1. **Binary Options**: Run `binary_options_pricing.ipynb` to compare Monte Carlo and finite difference methods
2. **Heston Calibration**: Execute `heston_model_calibration.ipynb` to calibrate the Heston model to market data
3. **Barrier Options**: Run `barrier_options_pricing.ipynb` to analyze barrier option pricing methods

## Key Insights

- Monte Carlo methods provide flexibility but require careful variance reduction
- Finite difference methods offer stability for PDE-based approaches
- Heston model captures volatility smile effects better than Black-Scholes
- Discrete monitoring adjustments are crucial for realistic barrier option pricing
- Proper calibration techniques are essential for practical model implementation
