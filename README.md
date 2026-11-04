# Panamax FFA paper book

A live paper trading book in Baltic Panamax 5TC (P5TC) forward freight agreements, run every week from **06 November 2026**.

Every Friday I publish a call: my view on where next month's Panamax market will settle, the position I take on it, and why. Each call is committed here before the market closes, so the record cannot be edited after the fact. When a month settles, the result is scored against the forward curve.

Paper trading only. No real money is involved.

## How the book works

**Instrument.** Monthly P5TC FFA, the contract cleared on EEX and SGX. It settles in cash against the average of the daily Baltic P5TC index over the month (five Panamax time charter routes, 82,500 dwt ship). Price in $/day, size in days. 30 days in one month is roughly one ship on hire for that month.

**Rules.**

| Rule | Setting |
| --- | --- |
| Contracts traded | Next month (M+1), occasionally M+2 |
| Position limit | 30 days per month, 60 days in total |
| Minimum edge to trade | My expected settlement must differ from the FFA price by more than $750/day |
| Sizing | 10, 20 or 30 days depending on conviction |
| Execution price | Baltic forward assessment for that Friday (mid-price, set at 17:30 London) |
| Cut-off | Call committed before 18:00 CET, so the fill price is unknown when the call is made |
| Execution cost | $125/day per trade, an assumption (half a typical bid-offer) |
| Stops | Each position has a stated invalidation level; book size halves if drawdown exceeds $100,000 |

## How to read the record

- `calls/` holds one file per Friday: market snapshot, view, trade, thesis, invalidation, review of past calls and a Black Sea note.
- `book/forecasts.csv` logs every weekly forecast, including weeks with no trade.
- `book/trades.csv` logs every trade and its result.

**Scoring.** The main measure is my forecast against the curve: for each settled month, was my expected settlement closer to the actual result than the FFA price was on the same day? Realised P&L (after costs), drawdown and hit rate come next. Twelve weeks is too short to prove skill statistically; the point of the record is the process and the quality of the reasoning.

## Data and caveats

- Official P&L is realised at settlement and uses the published monthly Baltic P5TC average.
- Weekly marks before settlement are estimates and are labelled as such.
- Baltic Exchange data is licensed, so full price histories are not published here. Only the specific prices used in each call are quoted.
- Backtest statistics used to set the risk limits come from LSEG Workspace data (January 2021 to November 2026), which also stays private.

## Author

Edoardo Dell'Osbel, MSc Management, HEC Lausanne.
