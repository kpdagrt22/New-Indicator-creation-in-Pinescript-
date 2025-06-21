# New-Indicator-creation-in-Pinescript-
The goal is to evaluate strategy robustness and improve real-time trading performance through parameter optimization over multiple rolling time windows.



Objectives
Implement a full Walk Forward Analysis (WFA) framework in Pine Script (v5 or v6 preferred).

Automatically divide the dataset into training (in-sample) and testing (out-of-sample) windows.

Optimize strategy parameters on the training set.

Apply the best parameters on the corresponding test set and record performance metrics.

Generate a performance summary and equity curve over all test sets combined.

Strategy Logic
- Entry Conditions
Long Entry:

Price closes above the upper Bollinger Band.

Parabolic SAR is below the price (trend confirmation).

Short Entry:

Price closes below the lower Bollinger Band.

Parabolic SAR is above the price.

- Exit Conditions
Trailing Stop: Exit when price crosses the Parabolic SAR line.

- Walk Forward Setup
Inputs:
training_period_bars: Number of bars used for training (e.g., 500).

testing_period_bars: Number of bars used for testing (e.g., 100).

step_forward_bars: Number of bars to roll forward each WFA iteration (e.g., 100 or smaller).

Parameters to Optimize:
Bollinger Band Length (BB_length)

Bollinger Band StdDev Multiplier (BB_mult)

SAR Start (SAR_start)

SAR Increment (SAR_increment)

SAR Max (SAR_max)

Desired Output per WFA Cycle:
Training range and testing range

Optimal parameter set (based on net profit, profit factor, etc.)

Test set performance:

- Net Profit

- Max Drawdown %

- Profit Factor

- Win Rate

- Sharpe Ratio (optional)

Output Requirements
Cumulative equity curve for all test periods

Tabular or visual output of each WFA cycle’s:

Time range

Optimized parameters

Performance metrics

A composite performance score using user-defined weightings (e.g.):
Total Score = NetProfit * 1 + Drawdown% * 5 + Profit Factor * 3 + Win Rate * 2
Technical Constraints
Pine Script v6 preferred (modular, optimized for performance).

Code mut respect TradingView’s script size and array memory limits.

Code should be modular and easily replaceable with different strategies in the future.

Deliverables
Fully working Pine Script source code (.pine file)

Comments and documentation within the code

Setup instructions and guide to adjust strategy logic or inputs

Minor revisions or bug fixing during testing period

