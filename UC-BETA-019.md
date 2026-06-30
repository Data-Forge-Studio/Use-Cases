# UC-BETA-019 — Cash-Secured Put Scanner

**Timeframe:** Ongoing

## Thesis

Systematically writing cash-secured puts on quality stocks at a price level below the current market — a level at which the stock would genuinely be wanted as a holding — generates premium income while effectively setting a limit order with built-in compensation for the wait. This use case is the entry mechanism that feeds directly into the broader wheel strategy, but can also be applied as a standalone income approach independent of the full wheel cycle.

## Entry Signal

Implied volatility rank at or above the 40th percentile, a genuinely desirable stock on the existing watchlist, and an expiration window of 30 to 45 days. The strike selected must represent a price the position would be comfortable owning the underlying shares at if assigned — this should never be treated as a pure premium-collection exercise divorced from genuine interest in the stock.

## Exit Rules

The put is closed for a profit at 50% of maximum premium capture, or allowed to expire worthless if price remains above the strike through expiration. If assigned, the position immediately transitions into the covered call phase of the broader wheel strategy.


---

*This document is for informational and educational purposes only and does not constitute financial advice. It does not take into account your personal financial situation, objectives, or risk tolerance. Always conduct your own research and consult a qualified financial advisor before making investment decisions.*
