UC-DELPHI-001: Autonomous Prediction-Market Paper Trader

*Documented 2026-07-11 | Designed this session — not yet built*

# ① IDENTITY

| **Use Case ID** | UC-DELPHI-001 |
| --- | --- |
| **Use Case Name** | Delphi — Prediction-Market Paper Trader |
| **Team** | Execution |
| **Asset Class** | Prediction markets — real, confirmed scope: Canada-focused Polymarket markets |
| **Asset(s)** | Not fixed — filtered to Polymarket's existing Canada category (53 real markets confirmed via research) |
| **Strategy Type** | Hybrid — real slippage tracking where data allows, simple win/loss otherwise |
| **Expected Hold Duration** | Until real market resolution — not actively price-monitored the way the other three traders are |
| **Initial Status** | DESIGNED — thesis prompt drafted, monitoring cadence intentionally on hold |
| **Created Date** | 2026-07-11 |
| **Created By** | Robert |

# ② THESIS

Prometheus already scores Polymarket odds but never actually acts on them — it reports, it doesn't trade. Delphi closes that gap, taking Prometheus's existing real estimates and turning them into an actual decision.

One real, important caveat: Robert doesn't yet have legal, Canadian-accessible prediction-market API access — no CIRO-approved product has launched, though Wealthsimple's is pending. Delphi's build proceeds regardless, using whatever data is currently reachable, but its real monitoring cadence stays deliberately open until that access exists.

Robert was direct about one more thing: every candidate Delphi passes on needs a real, specific reason on record, not a placeholder. Prediction markets often present many simultaneous candidates, so this "trades not taken" ledger carries real weight here in a way it doesn't for the other three traders.

# ③ REAL MECHANISM (as designed)

Reframes "invalidation" for predictions specifically — not a price stop, but the real implied probability moving against the thesis before resolution. Routes through Arbiter only on real ENTER decisions; SKIP decisions with their mandatory reason are tracked in a separate, dedicated table, deferred until this sprint actually starts.

# ④ REAL, DRAFTED OUTPUT FORMAT

Full draft prompt already built — see `delphi_thesis_prompt_draft.md`. Includes `position_side` (YES/NO), a mandatory `skip_reason` when the decision is SKIP, and `asset_specific_context.real_slippage_data_available`, which determines which half of the hybrid paper-trading design applies to a given trade.

# ⑤ REAL BUILD NOTES / DEPENDENCIES

Depends on Arbiter. Confirmed, real dependency on the Reddit sentiment feature — Delphi does pull from it, scoped to Canada-focused Polymarket, Kalshi, and r/sportsbook communities. `trading.delphi_skipped_candidates` deferred until this sprint starts. Real monitoring cadence deliberately left open pending Canadian data access.

# ⑥ HOW ROBERT INTERACTS WITH THIS

| **See Delphi's theses and skips** | Entries posted to `#signals`; skipped candidates tracked separately once built |
| --- | --- |
| **Confirm a trade happened** | Real paper position visible via `trading.open_positions` |

# ⑦ REAL, LIVE VERIFICATION STATUS

Designed, thesis prompt drafted, monitoring cadence intentionally left open. Real project plan places this as Sprint 5, the last of the four.
