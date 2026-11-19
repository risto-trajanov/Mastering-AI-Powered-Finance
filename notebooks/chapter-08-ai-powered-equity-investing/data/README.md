# Bundled market data for Chapter 7

Both files were retrieved from Yahoo Finance via `yfinance` on 2026-09-21 and
are pinned so the chapter reproduces.

`prices_2019_2024.csv` holds adjusted closes for the 52-name universe plus the
SPY benchmark, 2019-01-02 to 2023-12-29.

`fundamentals_snapshot.csv` holds trailing P/E, P/B, ROE, debt-to-equity,
market cap, dividend yield, beta and profit margin for the 52 names, **as of
2026-09-21**.

The fundamentals matter most. They are a *current* snapshot with no historical
as-of date, so the original code re-fetched whatever the market looked like on
the day the reader ran it. Every downstream result inherited that: the factor
ranking, the selected names, the expected-return vector, the optimizer weights
and the risk-limit output would all differ from the book. Pinning the snapshot
makes the printed walkthrough stable and gives the figures an explicit date,
which a point-in-time discipline requires anyway.

Note the snapshot is still *later* than the 2019-2023 price window, so it must
not be treated as point-in-time data for that period. The chapter says so, and
the backtest deliberately passes `fundamentals=None` and selects on lagged
price factors only, so it is unaffected either way.

To pull current data instead, set `REFRESH_MARKET_DATA=1`.
