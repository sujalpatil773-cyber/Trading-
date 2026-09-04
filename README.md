# FluxTrade — AI Crypto Market Studio

A polished browser-based crypto charting workspace with:

- Real Binance Spot historical candles via public market-data REST.
- Real-time Binance kline updates via WebSocket.
- TradingView Lightweight Charts for the financial chart surface.
- Client-side EMA, SMA, RSI, VWAP, Bollinger Bands and MACD calculations.
- Smooth glass UI, responsive layout and animated AI panel.
- OpenRouter-powered Chart Agent with tool calling.
- AI tools for reading chart state, changing symbol/timeframe, adding/removing indicators and drawing price levels.
- Local-only API key storage for testing.

## Run

Open `index.html` in a modern browser, or serve the folder with any static server.

1. Choose a Binance Spot symbol.
2. Choose a timeframe.
3. The chart loads historical candles from Binance and continues from its WebSocket stream.
4. Open **API key** and paste an OpenRouter key locally.
5. Ask the Chart Agent to analyze or manipulate the chart.

## Important security note

The browser-side OpenRouter key is intentionally a local testing mechanism. It must **not** be used as the production security model. A public deployment should send AI requests through a backend/serverless endpoint with the secret stored in an environment variable.

## Data sources

The app uses Binance public market data endpoints and `data-stream.binance.vision` for market-data WebSockets. No private Binance API key is required for the chart.

## Charting

The chart is powered by TradingView Lightweight Charts. Public deployments should retain the required TradingView attribution.

## AI

The default model parameter is `openrouter/auto`. The UI displays the model actually returned by OpenRouter for each completed response. Tool calls are executed by the browser; the model itself only requests the structured tool operation.

## Scope

This is the first polished foundation. It deliberately does not place live orders or connect to private exchange account data. Trade ideas are analysis only and should be treated as hypothetical scenarios, not guaranteed outcomes.
