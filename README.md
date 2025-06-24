# 📘 Covered Call Strategy Backtest – NIFTY 50 (2000–2023)
📌 Objective
This project performs a **monthly covered call backtest on the NIFTY 50 index, where a new ATM (At-the-Money) call option is sold each month.** The strategy evaluates performance over time based on historical price movements.

## 🧠 Concepts Covered
### Covered call strategy logic

### Monthly rolling P&L tracking

### Black-Scholes option pricing

### Performance metrics: Total return, CAGR, drawdown, win rate

### 🛠️ Technologies Used
Python
Pandas
NumPy
yFinance
SciPy.stats (for normal CDF)
Math (for Black-Scholes formula)

### 🔁 Strategy Logic
📥 Fetch historical daily closing prices for NIFTY 50 from Yahoo Finance (^NSEI).

🗓️ Every 21 trading days (approx. 1 month):

Capture the start price (S0)

Set strike price = S0 (ATM)

Calculate the expiry price (ST) after 21 days

### 📊 Option Premium:

Use Black-Scholes Formula to compute the call premium.

Inputs: S0, K, T, r, σ

### 💰 Payoff at Expiry:

payoff = max(ST - K, 0) (standard call option payoff)

### 🧾 Total P&L:

P&L Index = ST - S0

P&L Option = premium - payoff

Total P&L = Index + Option

### 📈 Strategy Performance Metrics
Total Return: Sum of all Total P&L / initial capital

Annualized Return (CAGR): Compounded annual return based on rolling performance

Maximum Drawdown: Peak-to-trough decline in cumulative P&L

Win Rate: % of months with positive Total P&L

### 💡 Sample Output

📊 Covered Call Backtest Results (NIFTY 50 - 2023):
[Shows monthly P&L data with columns like: S0, ST, Premium, Payoff, Total P&L]

### 📈 Strategy Performance:
**Total Return: 258.16%**
**Annualized Return: 9.77%**
**Max Drawdown: ₹4239.62**
**Win Rate: 77.91%**
**📌 Notes
Strike Price: ATM (S0)**

No transaction costs or slippage included

Volatility assumed constant across period (historical realized vol)

No position adjustments or early exit based on Greeks

Ideal for understanding the baseline P&L of a naive covered call strategy

🔮 Possible Extensions
Add Greeks (Delta, Vega, Gamma) to track exposure

Introduce dynamic strike selection (OTM, ITM)

Include volatility regime filters

Add rolling hedging adjustments

Run with different indices (e.g., Bank Nifty, S&P 500)
