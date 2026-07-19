# Crypto Intelligence

*9 active monitoring strategies in this area.*

## What we monitor

Digital asset markets across major and mid-cap tokens, covering
price behaviour, trading activity, capital movement on and off exchanges, market
structure, and the balance between the largest assets and the rest of the market.

Coverage extends beyond price. Positioning and accumulation patterns, momentum and
trend behaviour, market-wide risk appetite, and the qualitative commentary of
established analysts are all tracked, so that a move can be read in context rather
than in isolation.

## Why it matters

Crypto markets run continuously, react faster than traditional
markets, and are driven as much by positioning and sentiment as by fundamentals.
A meaningful move frequently begins before it is visible in price — in capital
leaving exchanges, in accumulation by large holders, in a shift in what the market
is willing to hold overnight.

Continuous automated monitoring exists to catch those shifts without depending on
someone watching. It also imposes consistency: the same conditions are assessed
the same way at 3am as at midday, which is difficult to sustain manually in a
market that never closes.

## Signal output

Output is deliberately coarse. Three states are published:

| State | Meaning |
| --- | --- |
| **BUY** | Conditions align and conviction cleared the required floor. |
| **WATCH** | Something of interest is developing but has not met the bar. |
| **AVOID** | Conditions argue against exposure, or a prior thesis has broken. |

No numeric scores, target levels or stop levels are published. A state is a
summary of a judgement, not an instruction, and it is not investment advice.

## How signals are governed

Every signal passes through the same controls before it reaches anyone:

- **Position limits.** Hard caps on the size of any single position, on how many
  positions may be open at once, and on how much exposure any one asset class may
  carry. These are enforced automatically, not by convention.
- **Conviction floor.** A signal below the required conviction level is not
  issued. The floor rises when the wider market regime is unfavourable.
- **Exit plan required.** No entry is accepted without a defined exit.
- **Duplicate suppression.** Repeat signals on the same asset within a short
  window are collapsed to the highest-conviction one, so a noisy condition cannot
  flood the output.
- **Human approval for rule changes.** The operating thresholds above can only be
  changed through a recorded proposal that a person approves. Nothing tunes
  itself silently, and every active parameter traces back to an approved change.

## Performance note

Outcome tracking is **in development and no performance figures are published.**

Signals are recorded with their entry conditions and evaluated over time, but the
pairing of entries to resolved outcomes was only recently implemented, and a
minority of use cases currently carry the calibrated exit levels needed to
resolve a result. Until a meaningful sample of resolved outcomes exists, any
win-rate figure would be an artefact of the measurement rather than a description
of performance.

We would rather publish nothing than publish a number that cannot be defended.
Performance reporting will appear here when the underlying sample supports it.

---

Part of the DataForgeStudio.xyz intelligence platform. Not investment advice.
