# SignalCheckerHQ TradingView scripts

Free, open-source TradingView indicators and a strategy template (Pine Script v6). Each one shows the **real result after fees** next to the number traders usually see: a call's "+50%", a grid bot's "grid profit", a DCA bot's closed deals, a backtest run with zero fees.

Same scripts as on TradingView (search "SignalCheckerHQ"), same code, so anyone can read exactly how every number is counted.

| Script | What it answers | TradingView |
|---|---|---|
| [Call Checker](scripts/call-checker.pine) | A trade call (entry, stop, targets): did it fill, which came first, stop or target, and what was the result after fees on the margin used? | [open](https://www.tradingview.com/script/1YqJuSvg-Call-Checker-Real-Result-After-Fees/) |
| [Liquidation vs Stop](scripts/liquidation-vs-stop.pine) | At this leverage, does liquidation come before your stop? What's the highest leverage that keeps the stop safe? | [open](https://www.tradingview.com/script/o4j1Ke3E-Liquidation-vs-Stop-Leverage-Check/) |
| [Grid Bot Reality Check](scripts/grid-bot-reality-check.pine) | A grid bot's reported "grid profit" next to the real account result, with the open position and fees included | [open](https://www.tradingview.com/script/wQCQr5Im-Grid-Bot-Reality-Check-Bot-Profit-vs-Real-Result/) |
| [DCA Bot Reality Check](scripts/dca-bot-reality-check.pine) | Closed-deal profit vs the real result with the open deal, next to simply holding | [open](https://www.tradingview.com/script/wTaHVdqR-DCA-Bot-Reality-Check-Deal-Profit-vs-Real-Result/) |
| [Honest Backtest](scripts/honest-backtest.pine) (strategy) | A strategy test with realistic costs (0.1% commission, slippage, no leverage, 10% per trade), next to holding the same amount. Swap in your own rules; the costs and the table stay | [open](https://www.tradingview.com/script/TODO-Honest-Backtest/) |

## How to use

1. Open TradingView, then **Pine Editor**.
2. Paste the code of a script and click **Add to chart**. Or add the published version from the links above.
3. Set the inputs (entry, stop, targets, bot range, fees). Every input has a tooltip.

## Rules the scripts follow

- **Fees always count.** Default 0.1% per fill (a typical spot taker fee). Change it to match your exchange.
- **When the order inside a candle is unclear, the worse outcome counts** (the stop before the target).
- **No repainting.** Results use closed candles.
- Leveraged results are measured on the margin actually used, and liquidation is checked before the stop.

The full rules for every SignalCheckerHQ tool are on [how we count](https://signalcheckerhq.org/how-we-count/).

## Limits

These are analysis tools for past prices. They don't place trades, don't connect to exchanges and never need API keys. Results depend on the chart's data and timeframe; a lower timeframe gives a more exact replay. **Nothing here is financial advice.**

## Free browser tools

The same checks, without TradingView, run free in the browser at [signalcheckerhq.org/tools](https://signalcheckerhq.org/tools/).

## License

[Mozilla Public License 2.0](LICENSE), the default license for open-source scripts on TradingView. © SignalCheckerHQ.

Found a bug or a wrong number? Open an issue. Every reported mistake gets checked and, if it's real, fixed in both places.
