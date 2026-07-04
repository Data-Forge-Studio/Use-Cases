# Use-Cases

A roster of which OpenClaw agents work on which trading use case category.

Each file here represents one real use case from the live use case registry and lists the agents actually involved in it, verified directly against the real pipeline code (which agent it calls, and which agent it reports results to), not inferred from the use case's theme or name.

## Structure

Files are named after their use case ID, for example `uc-alpha-001.md`, `uc-beta-012.md`, `uc-comm-003.md`. Every file follows the same shape:

- The use case ID and name
- **Core team** -- the agent that directly generates the analysis for this use case, confirmed via a real code call
- **Supporting team** -- agents confirmed to receive or contribute to this use case's output via a real, traceable code path
- **Status**, shown only when a use case is not currently active (for example, temporarily inactive)

## Naming convention

- `UC-ALPHA-*` -- crypto use cases
- `UC-BETA-*` -- equity use cases
- `UC-COMM-*` -- commodity use cases

The live registry has one additional entry not published here, a suspended use case that also references a real public figure by name; it is excluded regardless of any other consideration.

## What this repo does not contain

Trading logic, thesis statements, entry and exit rules, position sizing, and risk parameters are maintained privately and are not published here. This repo answers who works on this, not how the strategy works.

## Related repos

- [Agents](https://github.com/Data-Forge-Studio/Agents) -- full profile for every agent named here
- [Avatars](https://github.com/Data-Forge-Studio/Avatars) -- placeholder avatar images for each agent
