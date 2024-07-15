# Bond Yield Calculator

## Overview

The Bond Yield Calculator is a Python project designed to compute bond yield metrics, specifically spot rates and forward rates, from given par rates. This project is inspired by a question from the CFA (Chartered Financial Analyst) exam that focuses on the concepts of spot and forward rates in fixed income analysis.

## Case Study

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

## Installation

To use this project, ensure you have Python installed along with the necessary libraries. You can install the required packages using:

```bash
pip install numpy
