# Traversal — Game Rules (tournament reference)

> **Translation notice:** this document is the English translation of the French original, [`traversal-rules.md`](../traversal-rules.md). **The French version is authoritative**: in the event of any discrepancy or question of interpretation, it prevails over this translation.
>
> **Scope:** game rules only (the tournament rules — pairings, timings, refereeing, etc. — are covered separately).
> **Convention:** passages marked **⏳ [PB-xx]** refer to an item still open in the register.

---

## Contents

0. [Order of precedence of sources](#0-order-of-precedence-of-sources)
1. [Overview and objective](#1-overview-and-objective)
2. [The board](#2-the-board)
3. [The pieces](#3-the-pieces)
4. [Setup](#4-setup)
5. [Playing a turn](#5-playing-a-turn)
6. [Movement](#6-movement)
7. [Combat](#7-combat)
8. [Exiting and scoring](#8-exiting-and-scoring)
9. [End of the game and victory](#9-end-of-the-game-and-victory)
10. [Quick reference](#10-quick-reference)
11. [Glossary](#11-glossary)

---

## 0. Order of precedence of sources

If sources disagree, they apply in the following order:

1. **how the online game actually works** (its technical implementation);
2. **these rules**;
3. **the official "How to Play" page** on traversalgame.com.

---

## 1. Overview and objective

| Item | Value |
|---|---|
| Players | 2 |
| Pieces per player | 6 (2 of each type) |
| Board | 10 × 10 grid of squares with varying heights |
| Piece types | 3 (Explorer, Vanguard, Sentinel) |

**Objective:** move your pieces across the board and **exit them off the edge opposite** your starting row. Each piece that exits scores points equal to its **Strength**.

**Standard end of game:** as soon as **two pieces in total** have exited (whether they belong to the same player or to different players), the player with the higher score wins.

**Special victory:** if the **very first** piece to exit (counting both players) is a **Sentinel**, its owner wins immediately.

---

## 2. The board

### 2.1 Grid and coordinates

- The board is a **10 × 10** grid.
- **Columns**: **A to J**, from left to right as seen from Player 1's (red) side.
- **Rows**: **1 to 10**; row **1** is Player 1's starting row (bottom) and row **10** is Player 2's (top).
- **A1** is the bottom-left square and **J10** the top-right square (from Player 1's point of view).

### 2.2 Heights

- Every square has a whole-number **height** between **0 and 36** (theoretical limits). In practice, the difference between the lowest and highest square on a board is about 8 to 10 units.
- **Terrain constraint:** two orthogonally adjacent squares differ in height by at most **2 units**. No square is therefore impassable.

### 2.3 Generation and terrain modes

- Every game is played on a board generated so that neither side gets any significant advantage.
- For a physical edition, the site's **Board Generator** can produce a board.
- A terrain mode may be chosen before the game, for example:

| Mode | Terrain style |
|---|---|
| Random | Balanced variety of terrain |
| Mountains | Dramatic central peaks |
| Valleys | Deep basins bordered by ridges |
| Highlands | Mountains and valleys combined |
| Woods | Mostly flat, gentle hills |
| Desert | Flat expanses, occasional peaks |

> The choice of mode and the fairness of the board are matters for the tournament rules.

---

## 3. The pieces

### 3.1 Attributes

- **Movement (M)**: the movement-point budget a piece has each turn, equal to the **number of sides of its base**.
- **Strength (S)**: combat power and points scored on exit, equal to the **number of points on top** of the piece.
- For every piece, **M + S = 6**.

| Piece | Shape | Movement | Strength | Points on exit | Special ability |
|---|---|:-:|:-:|:-:|---|
| **Explorer** | Pentagonal cone | 5 | 1 | 1 | Special moves (§ 6.4) |
| **Vanguard** | Diamond wedge | 4 | 2 | 2 | Charge: +1 when attacking (§ 7.5) |
| **Sentinel** | Triangular prism | 3 | 3 | 3 | Instant victory if first piece to exit (§ 9.1) |

---

## 4. Setup

### 4.1 Sides

| Player | Colour | Starting row | Exits via | Plays |
|---|---|:-:|---|---|
| Player 1 | Red | 1 | the edge beyond row 10 | **first** |
| Player 2 | Blue | 10 | the edge beyond row 1 | second |

### 4.2 Placing the pieces

Each player places their 6 pieces on columns **C to H** of their starting row:

| Column | C | D | E | F | G | H |
|---|---|---|---|---|---|---|
| Piece | Sentinel | Vanguard | Explorer | Explorer | Vanguard | Sentinel |

- Player 1: **C1 to H1**.
- Player 2: **C10 to H10**.
- Columns A, B, I and J of each starting row stay empty.

```
            A   B   C   D   E   F   G   H   I   J
          ┌───┬───┬───┬───┬───┬───┬───┬───┬───┬───┐
      10  │   │   │ S │ V │ E │ E │ V │ S │   │   │   Player 2 (blue)
          ├───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤
     9…2  │             intermediate rows            │
          ├───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤
       1  │   │   │ S │ V │ E │ E │ V │ S │   │   │   Player 1 (red)
          └───┴───┴───┴───┴───┴───┴───┴───┴───┴───┘

  S = Sentinel   V = Vanguard   E = Explorer
  Player 1 exits at the top (beyond row 10), Player 2 at the bottom (beyond row 1).
```

---

## 5. Playing a turn

Players take turns, starting with **Player 1**. On their turn, the active player:

1. chooses **exactly one** of their pieces;
2. makes **one move** with that piece:
   - a **normal move** to an empty square (§ 6.1 to 6.3);
   - a **special move**, if the piece is an Explorer (§ 6.4);
   - an **attack**: a move whose destination is occupied by an enemy piece (§ 7);
   - an **exit from the board** to score (§ 8);
3. their turn **ends** immediately after that move.

**Obligation to move:** a player **must** make a legal move every turn. Passing is not allowed. Unused Movement is lost.

**No legal move:** a player who has **no legal move** on their turn (all their pieces are blocked, only losing attacks are available, or they have no pieces left on the board) **loses the game**.

---

## 6. Movement

### 6.1 Principle: a move is defined by its destination square

- A piece moves **orthogonally** (forward, backward, left, right), one square at a time. It never moves diagonally, except through the Explorer's special move.
- A move is defined solely by its **destination square**. A square is **reachable** if there is an orthogonal path to it:
  - that does not pass through **any piece** (friendly or enemy);
  - whose **total cost** (§ 6.2) is **less than or equal to** the piece's Movement.
- The piece may change direction along the way. The exact path taken does not matter: only the cost of the cheapest path to the destination counts.
- **The destination cannot be the starting square**: a null move is forbidden. (On a later turn, the piece may return to a square it occupied before.)

### 6.2 Cost of a step

**Cost of a step = |height difference| + 1.** Climbing and descending cost the same.

| Height difference | Cost |
|:-:|:-:|
| 0 (flat) | 1 |
| 1 | 2 |
| 2 | 3 |

**Example** (path 2 → 2 → 4 → 3 → 1): 1 + 3 + 2 + 3 = **9 points**.

### 6.3 Summary of what is forbidden

1. Passing through a piece, friendly or enemy.
2. Ending the move on the starting square.
3. Ending on a square occupied by a friendly piece.
4. Exceeding the Movement budget.

### 6.4 The Explorer's special moves

Each turn, **instead of** a normal move, an Explorer may make **one** of the following two special moves, from the square it occupies at the start of the turn. They use no Movement and **ignore terrain**.

| Special move | Description | Conditions |
|---|---|---|
| **Diagonal step** | 1 square diagonally | Allowed even if both orthogonal squares beside it are occupied |
| **Straight leap** | 2 squares in one orthogonal direction | The **intermediate square must be empty** (no jumping over a piece) |

- The destination must be **empty** or occupied by an **enemy piece**, in which case the special move is an **attack** (§ 7).
- A special move cannot be combined with a normal move.
- A special move may take the Explorer **off the board** (§ 8.2).

**Example:** an Explorer surrounded orthogonally (S = Sentinel, V = Vanguard, O = empty square) can still move diagonally to any O square:

```
  O  S  O
  V  E  V
  O  S  O
```

---

## 7. Combat

### 7.1 Principle

An **attack** is a move whose **destination is occupied by an enemy piece**. The attacker does not need to be adjacent to the target at the start of the turn:

- **normal move:** the target's square must be reachable under § 6.1. The step **into the target's square** costs |Δh| + 1 like any other step and counts against the Movement budget;
- **Explorer:** a diagonal step or a leap (§ 6.4) may also end on an enemy piece.

*Example:* two enemy Explorers on flat ground. If the first can reach the second's square for 5 Movement points or fewer, it may attack it (Strength 1 against 1: the attack succeeds).

### 7.2 Resolution

1. Work out the **attacker's effective Strength** (§ 7.3) and the **defender's** (§ 7.4).
2. Compare them:
   - **Attacker ≥ Defender** → the defender is **captured**, permanently removed from the game, and **the attacker takes its square**;
   - **Attacker < Defender** → the attack is **forbidden**: the move is not legal.
3. The attack **ends the turn**.

> An attack can never fail: only winning (or tied) attacks are legal moves.

### 7.3 Attacker's effective Strength

**Attacker = Base Strength + Height modifier + Allies + Charge (Vanguard)**

All modifiers **stack**.

| Modifier | Condition | Effect |
|---|---|:-:|
| **Height** | Square occupied by the attacker **at the start of the turn** is **higher** than the target's square | **+1** |
| | … is **lower** than the target's square | **−1** |
| | … is the same height | 0 |
| **Allies** | Each **other** piece of the attacker **orthogonally adjacent to the target** | **+ its Base Strength** |
| **Charge** | Vanguard only, see § 7.5 | **+1** |

- The height modifier is always **±1**, however large the difference.
- It compares the square where the turn started with the target's square, not the square crossed just before the target.
- Allies contribute only their **Base Strength**, with no modifiers.

### 7.4 Defender's effective Strength

**Defender = Base Strength + Support**

| Modifier | Condition | Effect |
|---|---|:-:|
| **Support** | Each friendly piece of the defender **orthogonally adjacent to the defender** | **+1** per piece, whatever its Strength |

The defender has no height modifier of its own: terrain only matters through the attacker's modifier.

### 7.5 The Vanguard's Charge

A Vanguard gains **+1 attack Strength** if, and only if, the **cost of the cheapest path** to the target's square is **exactly 4**.

- The cost includes the step into the target's square.
- It is calculated on the **actual board**: terrain **and** the pieces on it (which block the way).
- The bonus is **automatic**. If the cheapest path costs 1, 2 or 3, there is no bonus, even if a detour costing 4 exists.

### 7.6 Official examples

**Example 1 — High-ground advantage**

| | Attacker: red Vanguard | Defender: blue Vanguard |
|---|:-:|:-:|
| Base Strength | 2 | 2 |
| Height (turn started higher than the target) | +1 | — |
| Support (1 blue Sentinel orthogonally adjacent) | — | +1 |
| **Effective Strength** | **3** | **3** |

Result: 3 ≥ 3 → the blue Vanguard is captured and the red Vanguard takes its square. A supporting Sentinel only adds +1.

**Example 2 — Combined assault**

| | Attacker: red Explorer | Defender: blue Sentinel |
|---|:-:|:-:|
| Base Strength | 1 | 3 |
| Ally (red Vanguard orthogonally adjacent to the target) | +2 | — |
| **Effective Strength** | **3** | **3** |

Result: 3 ≥ 3 → the blue Sentinel is captured. The Explorer, which started 3 squares away on flat ground (cost 3 ≤ 5), takes its square.

---

## 8. Exiting and scoring

### 8.1 Exiting with a normal move

- A piece on its **last row** (row 10 for Player 1, row 1 for Player 2) may **exit the board** over the edge opposite its own side.
- Exiting **always costs exactly 1 Movement point**, whatever the height of the square.
- A piece may reach the last row, move along it and exit **in the same turn**, if its budget allows.
- Exiting is **optional** and **ends the turn**.
- A piece can never leave the board over the side edges or over its own starting edge.

### 8.2 The Explorer exiting with a special move

An Explorer may also exit:

- with a forward **leap** from the second-to-last row (the intermediate square, on the last row, must be empty) or from the last row;
- with a forward **diagonal step** from the last row.

### 8.3 Points

The exiting piece is removed from play and the player scores its **Base Strength**:

| Piece | Points |
|---|:-:|
| Explorer | 1 |
| Vanguard | 2 |
| Sentinel | 3 |

---

## 9. End of the game and victory

The conditions are checked after every move, **in the following order**.

### 9.1 Sentinel special victory (immediate)

If a **Sentinel** is the **very first piece** in the game (counting both players) to exit, its player **wins immediately**. If another piece has already exited, the Sentinel simply scores 3 points.

### 9.2 Standard victory (2nd piece exited)

As soon as the **second piece** in the game exits, the game stops:

- each player's score = the sum of the Base Strengths of their exited pieces;
- the **higher score** wins;
- if the scores are **tied**, the game is a **draw**.

| 1st exit | 2nd exit | Score P1 – P2 | Result |
|---|---|:-:|---|
| P1 Sentinel | — | 3 – 0 | P1 wins immediately |
| P1 Explorer | P2 Sentinel | 1 – 3 | P2 wins |
| P1 Vanguard | P2 Vanguard | 2 – 2 | Draw |
| P1 Explorer | P1 Vanguard | 3 – 0 | P1 wins |
| P1 Vanguard | P1 Sentinel | 5 – 0 | P1 wins |

### 9.3 Loss for lack of a legal move

A player who has no legal move at the start of their turn **loses** (§ 5). This includes a player who has no pieces left on the board.

This rule only applies if the game continues. If the move that removes a player's last piece ends the game (their Sentinel exits first, or their piece is the 2nd to exit), the result is the one given by § 9.1 or 9.2.

*Example:* Player 1 has only a Sentinel left and no piece has exited yet. It exits: Player 1 wins immediately (§ 9.1), even though they have no pieces left.

### 9.4 200-move limit

- A **move** is one player's action. The limit is **200 moves in total**, i.e. 100 per player. The game stops after the 200th move, played by Player 2.
- If that 200th move triggers an end of game under § 9.1 to 9.3, that result applies.
- Otherwise, the result is decided as follows:
  1. the **higher score** wins (at this point, at most one piece has exited);
  2. if **neither player has scored**: the player whose most advanced piece is **closest to its exit**, counted in rows still to cross (ignoring terrain), wins;
  3. if the distances are equal: the player whose most advanced piece has the **higher Strength** wins ⏳ [PB-24];
  4. if the Strengths are equal: the game is a **draw**.

**Repetition:** there is no repetition rule. Moving back and forth, for example to reach the 200-move limit, is a legitimate strategy.

---

## 10. Quick reference

```
ORDER       Player 1 (red, row 1) starts · 1 piece → 1 move → end of turn · no passing
            no legal move = loss

COORDINATES columns A–J, rows 1–10, A1 bottom left (red side)
SETUP       C–H: S V E E V S   (P1 on row 1, P2 on row 10)

MOVE        orthogonal · step cost = |Δh| + 1 · a move is defined by its destination
            cheapest path ≤ M · no passing through pieces · destination ≠ starting square

EXPLORER (M5 S1)  either: 1 diagonal (even between 2 pieces) OR leap of 2 (middle square empty)
            terrain ignored · may attack and exit with these moves

VANGUARD (M4 S2)  +1 when attacking if the cheapest path (terrain + pieces) to the target costs exactly 4

SENTINEL (M3 S3)  1st piece of the game to exit → instant victory

ATTACK      = move ending on an enemy piece (the entry step is paid) · the attacker takes the square
            Att = S + height (turn's starting square vs target: +1 / 0 / −1)
                    + Σ base S of other allies orthogonally adjacent to the target + 1 Vanguard charge
            Def = S + 1 per ally orthogonally adjacent to the defender
            Att ≥ Def → capture · Att < Def → illegal move

EXIT        from the last row, fixed cost 1 · optional · same turn possible

END         Sentinel exits 1st → victory · 2nd piece exits → higher score (tie = draw)
            200 moves in total → score > rows remaining > Strength > draw
```

---

## 11. Glossary

| Term | Definition |
|---|---|
| **Adjacent** | Orthogonally neighbouring: the square directly in front, behind, left or right. Diagonals do not count. |
| **Allies** | When attacking: the attacker's other pieces orthogonally adjacent to the target. |
| **Base Strength** | The piece's printed Strength (1, 2 or 3), before any modifier. |
| **Charge** | The Vanguard's +1 attack bonus (§ 7.5). |
| **Effective Strength** | Strength after combat modifiers are applied. |
| **Exit edge** | The edge of the board opposite a player's starting row, over which their pieces leave to score. |
| **Last row** | Row 10 for Player 1, row 1 for Player 2. |
| **Move** | A player's action during their turn (normal move, special move, attack or exit). |
| **Movement** | A piece's movement-point budget for one turn. |
| **Reachable square** | An empty or enemy-occupied square that can be reached by an orthogonal path without passing through any piece, for a total cost ≤ Movement. |
| **Support** | When defending: the defender's friendly pieces orthogonally adjacent to it (+1 each). |
