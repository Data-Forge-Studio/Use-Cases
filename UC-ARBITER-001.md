UC-ARBITER-001: Shared Portfolio Manager / Risk-Management Gate

*Documented 2026-07-11 | Designed this session — not yet built*

# ① IDENTITY

| **Use Case ID** | UC-ARBITER-001 |
| --- | --- |
| **Use Case Name** | Shared Risk-Management Gate for All Real Traders |
| **Team** | Execution — shared across Cipher, Bastion, Terra, Delphi |
| **Asset Class** | Asset-class-agnostic |
| **Asset(s)** | Not applicable — a shared service, not a trading soul itself |
| **Strategy Type** | N/A — a gating/sizing service, not a trade-generating role |
| **Expected Hold Duration** | N/A |
| **Initial Status** | DESIGNED |
| **Created Date** | 2026-07-11 |
| **Created By** | Robert, designed collaboratively this session |

# ② THESIS

Cipher currently uses a fixed, non-conviction-scaled position size with no real portfolio-level risk budget — confirmed via direct investigation. As the 4-trader system gets built, each new trader would otherwise need its own, separate sizing logic, and nothing would see real, aggregate exposure across asset classes.

Arbiter is the shared answer. Every trader's thesis routes through Arbiter before a position opens. Arbiter weighs the thesis against real, current portfolio context — how much is already committed, in what, and how many positions are already open — and returns an approved size or a rejection.

A rejected trader gets exactly one push-back attempt with additional reasoning, not unlimited retries. That distinction matters: it keeps Arbiter a genuine check rather than a formality a trader can simply outlast. Every decision, approved or rejected, gets logged with full context, feeding both Auditor's periodic review of Arbiter itself and each trader's own future reasoning.

# ③ REAL MECHANISM (as designed)

A trader builds a thesis through its own existing synthesis logic, then calls Arbiter with the thesis summary, asset class, symbol, conviction score, and a shared `asset_specific_context` object. Arbiter checks a real, unified view of current portfolio exposure by asset class before deciding. If rejected, the trader may push back once; whichever way Arbiter ultimately lands, the decision is recorded in `trading.risk_gate_decisions`.

# ④ REAL, DESIGNED OUTPUT FORMAT

Not a Discord-facing use case — Arbiter's output is a structured decision, not a posted message. Schema: `trading.risk_gate_decisions` (asset class, trader, symbol, thesis, conviction, portfolio context, initial and final decision with size and reasoning, whether a push-back occurred, and the eventual real outcome).

# ⑤ REAL BUILD NOTES / DEPENDENCIES

Requires two new tables: `trading.risk_gate_decisions` and a unified `trading.open_positions` table all four traders write to, plus an aggregate-exposure view built on top of it — already designed, see `risk_gate_schema_design.sql`. A planned `generate_risk_gate_governance_finding()` function will mirror Cipher's existing, proven `generate_skip_regret_finding()` pattern. Purely additive — nothing existing needs to change to support it.

# ⑥ HOW ROBERT INTERACTS WITH THIS

| **See Arbiter's decisions** | Query `trading.risk_gate_decisions` directly, or a future Discord summary |
| --- | --- |
| **Review Arbiter's own accuracy** | Via Auditor's periodic governance review, once built |

# ⑦ REAL, LIVE VERIFICATION STATUS

Designed, not built. Real project plan places this in Sprint 1, alongside Bastion.
