UC-TERRA-001: Autonomous Commodities Paper Trader

*Documented 2026-07-11 | Designed this session — not yet built*

# ① IDENTITY

| **Use Case ID** | UC-TERRA-001 |
| --- | --- |
| **Use Case Name** | Terra — Autonomous Commodities Paper Trader |
| **Team** | Execution |
| **Asset Class** | Commodities — oil, gold, silver, copper, agricultural |
| **Asset(s)** | Not fixed — builds on `UC-COMM-003`'s existing threshold detection |
| **Strategy Type** | Event-aware — distinguishes short-term/event-driven from long-term/structural theses |
| **Expected Hold Duration** | Varies by real time-horizon classification |
| **Initial Status** | DESIGNED — thesis prompt drafted |
| **Created Date** | 2026-07-11 |
| **Created By** | Robert |

# ② THESIS

Commodities already have threshold-based alerts through `UC-COMM-003`, but nothing that turns a signal into an actual, autonomously managed position. Robert's own example — oil moving on Strait of Hormuz tensions — is exactly the design problem Terra was built to solve: commodities move on real-world events in a way stocks and crypto simply don't, and a trading soul for this asset class has to know the difference between a headline and a trend. Terra doesn't just build a thesis, it labels why the thesis exists, and that label directly tightens or loosens its own stop and target distances.

# ③ REAL MECHANISM (as designed)

Adapts Cipher's pattern with one real addition: a field capturing the specific real-world driver behind a move, if one exists — a supply disruption, an OPEC+ decision, weather. Routed through Arbiter before any position opens. Reuses Bastion's exact market-hours design, adapted for commodities and futures' longer real trading hours.

# ④ REAL, DRAFTED OUTPUT FORMAT

Full draft prompt already built — see `terra_thesis_prompt_draft.md`. Matches Cipher's structure plus `asset_specific_context.time_horizon` and `asset_specific_context.real_world_driver`, with time horizon directly gating stop and target tightness in the prompt's own rules.

# ⑤ REAL BUILD NOTES / DEPENDENCIES

Depends on Arbiter and on Bastion's market-hours design existing. Open question, not yet decided: where `real_world_driver_summary` actually comes from — the Reddit sentiment feed once live, the existing RSS commodity feed, or a dedicated detection step of its own.

# ⑥ HOW ROBERT INTERACTS WITH THIS

| **See Terra's theses** | Posted to `#signals`, once built |
| --- | --- |
| **Confirm a trade happened** | Real paper position visible via `trading.open_positions` |

# ⑦ REAL, LIVE VERIFICATION STATUS

Designed, thesis prompt drafted. Real project plan places this as Sprint 4, after Bastion.
