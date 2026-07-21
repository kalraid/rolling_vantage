# Rolling Vantage

A web game fusing Vantage Master V2's grid-based summoner tactics with Dice of Afterimage's dice-driven resolution into a single combat layer (not two separate stages).

## Language

**Master**:
A Faction's leader unit on the grid — allocates that Faction's Dice Pool each turn (movement, MP charge, Reinforce) and summons/commands its Natials. Not exclusively player-controlled: the player's Faction has a Master, each Contender's Faction has a Master, and a Wild Faction may or may not have one. A Master's HP reaching 0 eliminates that Faction: its held Territory immediately neutralizes (returns to unclaimed, contestable by anyone), and its surviving Natials are not despawned — they persist as a new/merged Wild Faction (leaderless, hostile-by-default obstacles). If the eliminated Faction is the player's own, the Run ends immediately for the player and their rank is scored as of that moment; other Factions' eliminations don't end the Run — it continues until its own end condition is met.
_Avoid_: Summoner, player character (ambiguous with Natial), NPC Master (use Contender instead)

**Faction**:
A group of units sharing allegiance on the grid — a Master (if any), its Natials, and any Territory it holds. Units from different Factions are hostile by default and trigger Contest/Skirmish on contact. A Run has the player's Faction, 7 Contender Factions, and one or more Wild Factions.
_Avoid_: Team, side, player (a Faction is the domain unit; "player" refers only to the human)

**Contender**:
One of the 7 CPU-controlled rival Factions competing against the player's Faction for Territory and ranking within a Run. A Contender's Master is drawn from the same roster the player unlocks with Meta GP — including Masters the player hasn't unlocked yet — so growing the roster also grows Contender variety, not just player options. Launch roster target: 12-16 Masters (a Run needs 8 simultaneously, so this keeps repeats within a single Run infrequent without demanding VM V2's full 27).
_Avoid_: NPC, AI player, enemy master

**Wild Faction**:
A Faction native to the map that does not compete in the Run's 8-way ranking (player + 7 Contenders). May consist of Natials only, or Natials led by a Master-equivalent leader. Hostile-by-default like any other Faction. When a ranked Faction is eliminated, its surviving Natials absorb into the nearest existing Wild Faction if one is nearby, or otherwise form a new one — this keeps the number of Wild Factions on a map from growing unbounded.
_Avoid_: Monster camp, neutral mob (the unit inside is still a Natial — Wild Faction describes ownership, not a different unit type)

**Natial**:
A spirit/monster unit summoned onto the grid by a Master, consuming MP to maintain.
_Avoid_: Monster, unit, creature, Ethereal (에테리얼 — used once in discussion as a synonym, canonical term stays Natial)

**MP**:
The resource spent to summon and maintain Natials. Charged each turn via Dice Pool allocation rather than a fixed formula. Each Master has an MP cap stat, and each Natial has its own upkeep coefficient drawn against that cap while summoned.
_Avoid_: Mana, magic points (keep MP as the canonical abbreviation)

**Base Stats**:
The fixed per-Master/per-Natial numbers the rest of the system builds on: HP (reaching 0 = defeat/removal), a movement modifier (added on top of the die value allocated to movement), and MP cap/upkeep coefficient (see MP). There is deliberately no separate attack/defense stat — Contest/Skirmish outcomes come from the die value plus Element matchup only, nothing else.
_Avoid_: Attributes (ambiguous with Element)

**Dice Pool**:
The set of N six-sided dice (D6, value 1-6) a Master rolls once at the start of their turn — D6 is the baseline die for both Contest and Skirmish resolution, used unless a specific Master's kit says otherwise (see open decision below). Individual die values are then allocated by the player across movement, MP charging, and combat resolution (Reinforce, or a direct Contest) for that turn — the allocation choice itself is the core strategic decision, not the roll. N has no upper cap — it scales directly and indefinitely with held Territory, which is a deliberate snowball risk to weigh during balancing (see task: Grill 밸런싱/플레이테스트).
_Avoid_: Dice roll (implies per-action rolling, which this project does not use), turn roll

**Territory**:
The single largest contiguous cluster of grid tiles a Faction holds — if a Faction holds multiple disconnected clusters, only the largest one counts, which rewards concentrated expansion over scattered land-grabbing. Tile size of this cluster directly sets that Faction's Dice Pool size (N) for their next turn — this is the sole driver of N, and N has no upper cap (see Dice Pool). An unclaimed (neutral) tile is claimed the instant a Faction's unit reaches it; a tile already held by a hostile Faction instead triggers a Contest/Skirmish on contact rather than an automatic claim.
_Avoid_: Mana stone, elemental zone (V2's original term; renamed since the elemental-charge-rate role is now fully replaced by the Dice Pool size role)

**GP**:
The game's currency, split into a Run-scoped balance and a permanent Meta GP balance. Run GP is earned by holding/expanding Territory and clearing event/treasure tiles (not by movement or Contest wins), and is spent on Natial summons, Dice Pool rerolls, healing, and Support Purchases. At Run end, a portion of remaining Run GP converts to Meta GP — a larger portion on success than on failure.
_Avoid_: Gold, gems (no other currency exists in this project)

**Meta GP**:
The permanent currency, carried across Runs and Chapters, that funds account-wide unlocks: new Masters/Natials, new Skills, and new Support Skills. Deliberately does not buy raw stat power — see [[docs/adr/0002-meta-progression-unlocks-not-stats]] for why.
_Avoid_: Gems, premium currency

**Event Tile**:
A grid tile that triggers an effect when a Faction unit reaches it. Types: reward (grants GP/resources), choice (a risk/reward decision prompt), trap (a penalty), Wild Faction encounter, scenario trigger (fires a Chapter's scripted story beat — any Faction, including Contenders, can trigger the mechanical consequence, e.g. a boss awakening; only the player sees the dialogue/text for it), and random teleport. Reward/choice/trap/encounter/teleport types are drawn from the Chapter's procedural part pool (see Run); scenario triggers are hand-placed as part of a map's authored frame, not procedurally generated.
_Avoid_: Encounter (reserve for the Wild Faction subtype specifically)

**Command Post**:
A grid tile type where a Master can make Requisitions. Requisitions (mercenary reinforcements, remote bombardment, and similar effects) are only available while occupying a Command Post — they are not available from a persistent menu.
_Avoid_: Shop, base (a Command Post is a tile on the same grid, not a separate screen)

**Requisition**:
A one-off, GP-purchased battlefield action bought at a Command Post — e.g. mercenary reinforcements, remote bombardment — consumed on use. Distinct from a Support Skill: a Requisition is a Run-scoped GP spend available to anyone at a Command Post, while a Support Skill is a permanent capability unlocked account-wide with Meta GP (see Meta GP). The two were previously conflated under one name ("Support Purchase") — kept separate now that both exist.
_Avoid_: Support Purchase (former name, now ambiguous with Support Skill), Support Skill

**Act**:
A group of consecutive Chapters. An Act's last Chapter is always a Core Chapter (see Chapter); every other Chapter in the campaign is a Normal Chapter.
_Avoid_: Arc (use Act as the canonical term)

**Chapter**:
A fixed, story-ordered unit of the single-player campaign, played in sequence. Two kinds: a **Normal Chapter** has no retry — when its Run fails, the campaign always proceeds directly to the next Chapter, no choice point. A **Core Chapter** is the last Chapter of an Act — when its Run fails, it's a full game failure: the campaign resets to Chapter 1 (roguelike-style), though Meta GP-funded unlocks (roster/Skills/Support Skills) persist across the reset.
_Avoid_: Stage, level (a Chapter contains multiple Runs, it is not a single battle)

**Run**:
One roguelike playthrough of a single continuous grid map within a Chapter, ending in either completion or defeat. The grid map doubles as both board (enemies, Territory, events, loot as tiles the Master moves across via Dice Pool movement) and battlefield (Contests happen in place, on the same grid, the instant a Master's move lands on a hostile tile) — there is no separate board screen and battle screen.
_Avoid_: Stage, attempt, level, dungeon

**Element**:
Each Master/Natial has one of four elements — Earth, Water, Fire, Sky — in the fixed cycle Earth beats Water beats Fire beats Sky beats Earth (ported from Vantage Master V2). In a Contest/Skirmish, the matchup tier (favorable / even / same-element / unfavorable) modifies the affected side's effective die value before the margin is computed, which shifts which margin tier (see Contest) the result lands in — element advantage doesn't deal separate damage, it pushes the roll toward a better outcome tier. V2's special case is kept: a Master's own attack always counts as favorable, its own defense always counts as even, regardless of the actual elements involved. V2's original flat modifiers (+4/+1/-1/-3.5) were sized for its own damage formula, not a 1-6 die — the modifier values here need to be rebalanced for the D6 scale (see task: Grill 밸런싱/플레이테스트).
_Avoid_: Attribute, affinity (Element is the canonical term)

**Contest**:
An opposed combat resolution between an attacker's allocated die and a defender's allocated die (or a fixed defense value if the defender chooses not to allocate one). The higher value wins; the margin between the two values tiers the outcome severity: a small margin deals HP damage only, a larger margin adds a special effect (knockback or stun) on top of damage, and a crit-threshold margin allows an instant kill. Skirmish uses this same margin-tiered outcome table. Triggered deliberately by a Master's own move landing on a hostile tile, or by a Master spending an allocated die directly — distinct from a Skirmish.
_Avoid_: Roll-off, duel

**Command**:
A standing order a Master issues to one of their Natials: a destination, an attack target, and a skill-use priority. Natials act on their Command autonomously and continuously in real time; a Command can be reissued at any time, not gated to the Master's own turn.
_Avoid_: Order, AI script

**Skirmish**:
The automatic combat resolution that fires when two hostile Natials (or a Natial and an enemy) meet during real-time Command execution. Uses auto-rolled dice plus stats — no player-allocated die, unlike a Contest. A Master can spend a Dice Pool die to Reinforce a specific Natial, boosting it in its next Skirmish this turn.
_Avoid_: Contest (reserve Contest for the Master-driven, deliberately-allocated version), auto-battle

**Reinforce**:
Spending an allocated Dice Pool die on a chosen Natial rather than on the Master's own movement or MP charge — buffs that Natial for its next Skirmish this turn only. This is what the "combat" slot of a Master's Dice Pool allocation now means when the Master isn't the one directly fighting.
_Avoid_: Buff (too generic outside this specific spend)

## Open decisions still in play

- Whether summon/special-ability checks also draw from the Dice Pool (currently excluded — those stay deterministic).
- Whether a defending Master needs their own reserved Dice Pool available on the opponent's turn (i.e., does defense draw from dice already spent this turn, or from a separate reserve?).
- Exact split of what carries over between Runs within a Chapter vs. what resets (Territory control resets per Run; Master roster/Skill/Support Skill unlocks persist via Meta GP — Run-to-Run state within a Chapter otherwise still unclear).
- Exact Run-success vs. Run-failure conversion ratio from Run GP to Meta GP (direction is set, numbers are not).
- A Run now hosts the player's Faction + 7 Contenders free-for-all over Territory on one grid, resolved round-by-round with simultaneous (blind-commit) turns rather than strict sequential turn order. When multiple units from different Factions converge on the same tile in the same round (only one unit can occupy/fight there at a time), they resolve in ascending order of travel distance to that tile — the closest unit fights first, the winner then fights the next-closest arrival, and so on (a resolution queue, not a single N-way brawl).
- How many Wild Factions exist per Run, whether they hold/contest Territory the same as Contenders do, and whether a Wild Faction's Master (if it has one) allocates a Dice Pool the same way a Contender's does.
- GP payout moves from binary success/failure to a ranking-based model (closer to Dice of Afterimage's original). A Run's end condition (goal-reach, round-limit, last-standing, etc.) and its ranking formula are both defined per map/Chapter rather than a single universal rule — this raises per-map authoring cost (each map needs its own end condition AND its own ranking formula) that Level Design (task: Grill 레벨디자인) needs to account for.
- Whether Reinforce requires the Master to be within some range/line of the target Natial, or can be spent on any of the Master's Natials anywhere on the grid.
- Grid size varies per map/scenario like end conditions and ranking formulas do (no fixed universal size). No min/max envelope has been set yet; the first prototype map targets a medium size (~20x20) for testing before any bound is locked in.
- Whether individual Masters get a signature die type (e.g., a D4 Master for low-variance consistency vs. a D8/D10 Master for high-variance ceiling) as a character-identity mechanic, instead of every Master using the D6 baseline — flagged as a hook for Character Design (task: Grill 캐릭터 디자인) rather than decided here.
