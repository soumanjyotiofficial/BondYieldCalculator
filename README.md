# BondYieldCalculator
A Python script for calculating bond yield metrics, including spot rates and forward rates, from given par rates. This project is particularly useful for finance professionals and students preparing for exams such as the CFA.

# Features

- **Calculate Spot Rates**: Compute spot rates from given par rates using bootstrapping.
- **Calculate Forward Rates**: Compute forward rates based on spot rates.

## Exhibit 1: Current Par and Spot Rates

| Maturity  | Par Rate | Spot Rate |
|-----------|----------|-----------|
| One year  | 2.50%    | 2.50%     |
| Two years | 2.99%    | 3.00%     |
| Three years | 3.48%  | 3.50%     |
| Four years | 3.95%   | 4.00%     |
| Five years | 4.37%   | 4.45% (computed) |

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/BondYieldCalculator.git
    ```
2. Navigate to the project directory:
    ```bash
    cd BondYieldCalculator
    ```
3. Ensure you have `numpy` installed:
    ```bash
    pip install numpy
    ```

## Usage

### Calculating Spot Rates

To calculate spot rates from the given par rates:

```python
import numpy as np

par_rate = [2.50, 2.99, 3.48, 3.95, 4.37]

def cpt_spot_rate(par_rate):
    spot_rate = []
    for a in par_rate:
        if len(spot_rate) == 0:
            spot_rate.append(round(par_rate[0] / 100, 4))
        else:
            cpn = [round(par_rate[len(spot_rate)] / 100, 4) for a in range(len(spot_rate) + 1)]
            cpn[-1] = cpn[-1] + 1
            LHS = 1
            iter = 0
            for cf, sr in zip(cpn[:-1], spot_rate):
                iter += 1
                LHS -= round(cf / (1 + sr) ** iter, 6)
            RHS = round(((cpn[-1] / LHS) ** (1 / len(cpn)) - 1), 6)
            spot_rate.append(RHS)
    spot_rate = list((np.array(spot_rate)*100).round(2))
    return spot_rate

spot_rate = cpt_spot_rate(par_rate)
print(spot_rate)
