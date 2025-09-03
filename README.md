# heston-lsv-convergence-in-time
# Calibrated Heston-type LSV Model - Strong convergence in time

This repository contains Python code that simulates a **calibrated Heston-type Local Stochastic Volatility (LSV) model** and studies the **strong convergence in time** of the Euler--Maruyama time discretisation scheme.

## Overview

The code simulates a **calibrated Heston-type Local Stochastic Volatility (LSV) model**, where the squared volatility process follows **Cox–Ingersoll–Ross (CIR) dynamics**. To approximate the conditional expectation, it uses the **Nadaraya–Watson kernel estimator**.

Instead of relying on real market data, the code generates a synthetic **market implied volatility surface** using **already calibrated Heston parameters** obtained from an FX market. From this, a **Dupire local volatility surface** is generated and extended via **bicubic interpolation and extrapolation**.

The implementation uses **QuantLib**, an open-source library for quantitative finance, for model construction (Heston), curve setup, pricing engines, path generation, and building both implied and local volatility surfaces.

The main goal is to investigate **strong convergence in time of the Euler--Maruyama time discretisation scheme** and analyse the convergence rate under different sets of model parameters.


## Features

- Artificial market surface from calibrated Heston parameters
- Dupire local volatility surface generation
- Euler-Maruyama scheme for stock price process
- Full truncation Euler scheme for variance positivity
- Nadaraya-Watson kernel regression to approximate conditional expectation
- Strong convergence in time of the Euler--Maruyama time discretisation scheme

## Requirements

- Python 3.9+
- numpy
- pandas
- matplotlib
- scipy
- seaborn
- scikit-learn
- QuantLib

Install dependencies with:
pip install -r requirements.txt

## Usage

Run the simulation:
python convergence_in_time.py

You can also import the functions into another Python script:
from convergence_in_time import run_experiment
results = run_experiment(do_plot=True)

## Output

- Local volatility surface plots
- Implied volatility surface plots
- Plots of "market prices" over strikes for fixed maturity
- Plots illustrating the strong convergence in time of the Euler--Maruyama time discretisation scheme

## License

This project is licensed under the MIT License – see the LICENSE file for details.

