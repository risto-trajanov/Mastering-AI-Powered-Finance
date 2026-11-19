# Bundled market data for Chapter 6

`spy_2015_2024.csv` is a fixed snapshot of SPY daily OHLCV, auto-adjusted,
covering 2015-01-02 to 2024-12-30. Retrieved from Yahoo Finance via `yfinance`
on 2026-09-21.

It is bundled because the chapter's printed numbers cannot otherwise be
reproduced. Yahoo serves back-adjusted history at float32 precision and its
adjustment factor shifts slightly between requests: consecutive downloads of
the identical window returned an opening close of both `169.2675018310547` and
`169.26756286621094`. Those differences are far too small to matter
economically, but they change feature values enough to move gradient-boosted
and random-forest split points, which shifted the reported XGBoost CAGR by more
than a percentage point between runs.

Buy-and-hold stays stable across those runs because it is a smooth function of
the prices, not because `Open` is fixed: the open drifts by the same relative
magnitude as the close. So a check on the benchmark does not detect this. The
model rows, which depend on tree split points, are what drift.

To pull current data instead, set `REFRESH_MARKET_DATA=1`. Expect the model
rows to differ from the book.
