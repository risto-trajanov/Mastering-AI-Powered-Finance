# Bundled market data for Chapter 2

`prices_2020_2024.csv` is a fixed snapshot of daily OHLCV for AAPL, MSFT and
GOOGL, auto-adjusted, covering 2020-01-02 to 2024-12-31. Retrieved from Yahoo
Finance via `yfinance` on 2026-09-21.

It is bundled for two reasons.

First, `auto_adjust=True` back-adjusts the entire price history every time a
dividend or split occurs, so any adjusted close printed in the book drifts
permanently after publication. The drift is already measurable.

Second, Yahoo serves that back-adjusted history at float32 precision and its
adjustment factor varies slightly between requests, so even two downloads of
the same window can differ in the last digits.

Neither effect matters economically, but both prevent the printed statistics
from reproducing. Pinning the snapshot fixes them.

To pull current data instead, set `REFRESH_MARKET_DATA=1`. Expect the printed
statistics to differ from the book.
