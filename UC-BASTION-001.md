UC-BASTION-001: Autonomous Stock Paper Trader

*Documented 2026-07-11 | Designed this session — not yet built*

# ① IDENTITY

| **Use Case ID** | UC-BASTION-001 |
| --- | --- |
| **Use Case Name** | Bastion — Autonomous Equity Paper Trader |
| **Team** | Execution |
| **Asset Class** | US and Canadian equities |
| **Asset(s)** | Not fixed — scans real candidates, matching Cipher's own scan-and-score model |
| **Strategy Type** | Swing-style, matching Cipher's proven horizon — exact parameters TBD at build time |
| **Expected Hold Duration** | Days, market-hours-gated |
| **Initial Status** | DESIGNED — thesis prompt drafted, market-hours monitoring designed |
| **Created Date** | 2026-07-11 |
| **Created By** | Robert |

# ② THESIS

No dedicated, autonomous stock trader currently exists. Bastion adapts Cipher's exact thesis-synthesis pattern — Volta on technicals, Sentinel on sentiment, Atlas on macro, Contrarian pressure-testing the case — for equities, with one real addition crypto never needs: earnings risk. An approaching earnings date is treated as a hard gate, not just another data point. Conviction drops automatically unless the thesis explicitly is an earnings play, closing off the accidental scenario where Bastion holds straight through a report it never meant to be exposed to.

# ③ REAL MECHANISM (as designed)

Same five-input synthesis pattern as Cipher, routed through Arbiter (UC-ARBITER-001) before any position opens. Market-hours monitoring checks whether the market is genuinely open fresh on every scheduler tick rather than relying on a pre-computed window — a deliberate choice made after tracing the exact bug shape that silently broke `BetaPipeline` earlier this session. A dedicated check also runs in the first fifteen minutes after open, the real point of highest risk for a position that sat overnight with no way to react to anything.

# ④ REAL, DRAFTED OUTPUT FORMAT

Full draft prompt already built — see `bastion_thesis_prompt_draft.md`. Matches Cipher's exact JSON shape (bull case, bear case, entry trigger, invalidation, target and stop percentages, conviction, decision, reason) plus a shared `asset_specific_context.earnings_risk_flag`.

# ⑤ REAL BUILD NOTES / DEPENDENCIES

Depends on Arbiter existing. Open question: confirm `pipeline_earnings.py` already has days-to-earnings and last EPS beat/miss in an easily queryable form. Market-hours design already complete — see `bastion_market_hours_design.md`.

# ⑥ HOW ROBERT INTERACTS WITH THIS

| **See Bastion's theses** | Posted to `#signals`, matching Cipher's existing pattern, once built |
| --- | --- |
| **Confirm a trade happened** | Real paper position visible via `trading.open_positions` |

# ⑦ REAL, LIVE VERIFICATION STATUS

Designed, thesis prompt drafted, market-hours monitoring designed. Real project plan places this as Sprint 2, right after Arbiter.
