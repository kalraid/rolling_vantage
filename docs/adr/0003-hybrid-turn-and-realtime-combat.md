---
status: accepted
---

# Masters are turn-based, Natials fight in real time

A Run hosts 1 player Master plus 7 NPC Masters free-for-all over Territory on a single grid (closer to Dice of Afterimage's original 8-player race than a VM-style duel). Resolving 8 Masters' turns strictly sequentially each round was judged too slow. Full real-time for everything was rejected because it would dissolve the Dice Pool's core identity — a deliberate once-per-turn allocation — into a reflex/APM game.

The resolution: Masters keep discrete turns and Dice Pool allocation (movement, MP charge, Reinforce). Natials do not move or fight on the Master's turn — they act continuously in real time against a Command (destination, attack target, skill priority) that the Master can reissue at any time. When hostile Natials meet, combat resolves automatically as a Skirmish (auto-rolled dice + stats), not as a player-allocated Contest. A Contest still exists, but only for the Master's own deliberate actions (their move landing on a hostile tile, or a directly-spent die) — see [[CONTEXT.md]] for the Contest vs. Skirmish distinction.

## Considered Options

- Strict sequential turns for all 8 Masters, NPC turns auto-resolved/fast-forwarded (kept the existing single-resolution-mechanic design, rejected for still feeling slow and for making the free-for-all read as sequential rather than simultaneous).
- Full real-time for both Masters and Natials — rejected: breaks the "one allocation choice per turn is the strategic core" identity established earlier in the project.

## Consequences

Two separate combat resolution mechanics (Contest, Skirmish) now need independent balancing, and Skirmish's "auto-rolled dice + stats" formula is undesigned. NPC Master AI (task: Grill 적 AI 설계) now also has to produce Natial Commands, not just Dice Pool allocation, for all 7 NPCs.
