# Bond Yield Calculator

## Overview

The Bond Yield Calculator is a Python project designed to compute bond yield metrics, specifically spot rates and forward rates, from given par rates. This project is inspired by a question from the CFA (Chartered Financial Analyst) exam that focuses on the concepts of spot and forward rates in fixed income analysis.

## Case Study from CFA level 2 study material

In this project, we analyze the following data from a hypothetical bond market:

### Exhibit 1: Current Par and Spot Rates

| Maturity    | Par Rate | Spot Rate |
|-------------|----------|-----------|
| One year    | 2.50%    | 2.50%     |
| Two years   | 2.99%    | 3.00%     |
| Three years | 3.48%    | 3.50%     |
| Four years  | 3.95%    | 4.00%     |
| Five years  | 4.37%    | ?         |

### Questions

1. Based on Exhibit 1, the five-year spot rate is closest to:
   - A. 4.40%
   - B. 4.45%
   - C. 4.50%

2. Based on Exhibit 1, the forward rate of a one-year loan beginning in three years is closest to:
   - A. 4.17%
   - B. 4.50%
   - C. 5.51%

This project computes the missing five-year spot rate and the forward rate for a one-year loan starting in three years, providing insights into fixed income securities.

## Features

- **Spot Rate Calculation**: Computes spot rates from given par rates using the bootstrapping method.
- **Forward Rate Calculation**: Calculates the forward rate for a specified future loan period based on spot rates.

Calculates the forward rate for a loan starting at a specified future time and for a specified tenure.

- **Parameters**: 
  - `from_now` (int): The number of years from now when the loan begins.
  - `tenure` (int): The duration of the loan in years.
  - `spot_rate` (list of floats): The list of calculated spot rates.

- **Returns**: 
  - `forward_rate` (float): The calculated forward rate.

## Usage

```python
import numpy as np

par_rate = [2.50, 2.99, 3.48, 3.95, 4.37]

spot_rate = cpt_spot_rate(par_rate)
print(spot_rate)
print(f"The {spot_rate[-1]} is the 5th year spot rate that is missing in exhibit 1")

from_now = 3
tenure = 1
print(f"{from_now}y from now {tenure}y loan's forward rate is {cpt_forward_rate(from_now, tenure, spot_rate)}%")


# Do join my telegram chanel

