# FluxTrade — BTC Tier-1 Quant Research Terminal

FluxTrade is a browser-first quantitative research and paper-trading terminal built around **real public Binance market data**. The current branch upgrades the original charting foundation into a multi-signal intraday research surface.

## Live data

The frontend consumes Binance public REST/WebSocket feeds for:

- Historical and streaming Spot candles.
- 20-level order-book snapshots.
- Aggregate trades.
- USD-M funding and open interest.
- USD-M liquidation (`forceOrder`) events.

The application never fabricates a value when a feed is unavailable.

## Quant engine

The browser computes a practical research ensemble from live data:

- Multi-scale momentum.
- EMA trend state.
- RSI.
- Realized volatility.
- Volume expansion ratio.
- Rolling fair value and residual z-score for mean reversion.
- 20-level order-book imbalance.
- Microprice.
- Spread proxy.
- Regime classification.
- Weighted alpha ensemble.
- Conservative transaction-cost filter.
- Risk-aware entry, stop and target proposal.

These are **research heuristics**, not a claim of institutional profitability. The numerical weights should be calibrated and validated out-of-sample before any real-money use.

## UI

The terminal includes research views for Overview, Market Microstructure, Alpha Engine, Regime Engine, Stat Arb, Cross Exchange, Derivatives, Volatility, Backtest, Paper Trading and Model Lab, plus a live order-flow sidebar.

## Run

This is a static frontend. Open `index.html` directly or serve the repository with any static HTTP server. A backend is intentionally not required for the current public-data prototype.

## Safety

The current deployment is **paper/research only**. It does not submit exchange orders or use private exchange account credentials. Price levels and signals are hypothetical outputs from the displayed model.

## Production roadmap

For a production Tier-1 system, move the data and quantitative engine server-side and add exchange adapters, persistent time-series storage, Redis/event streaming, calibrated impact/slippage models, walk-forward backtesting with purged/embargoed validation, portfolio optimization, execution simulation, model monitoring, authentication and secrets management.
