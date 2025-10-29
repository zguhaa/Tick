# Tick

**Competitive social platform for Solana traders.**  
XP, ranks, and real-time trading duels that turn on-chain activity into a game.

---

## TL;DR
- **What:** Social + Gaming layer for traders on Solana.
- **Core loop:** Trade → earn XP → climb ranks → win duels → unlock badges.
- **Why:** Trading is lonely/opaque. Tick makes it **engaging, social, measurable**.

---

## Problem
On-chain trading is fragmented and hard to measure. No persistent identity/reputation for retail traders, no fair “skill expression”, and no reason to stay active during low volatility.

## Solution
**Ranked XP progression** and **time-boxed trading duels**. Users connect a wallet, join a duel (1h/4h/24h), and compete on **PnL or ROI** using on-chain data. Results are verifiable; XP fuels global **leaderboards**, **leagues**, and **seasonal rewards**.

---

## MVP Scope (Hackathon)
- Wallet connect (Phantom/Backpack).
- Profile with XP, rank, recent duels.
- Create/accept **duel** (time window + metric: PnL% or absolute PnL).
- Read-only on-chain indexing (no custody).
- Global leaderboard (weekly/seasonal).
- Anti-abuse v1: wallet lock per duel, min activity threshold, duplicate-wallet check.

> Trading execution: at MVP — **external** (Axiom/any terminal).  
> Next step — **in-app trade routing** (Jupiter) to become a lightweight terminal.

---

## Next After MVP
- In-app swap (Jupiter Aggregator).
- **NFT badges** (soul-bound or semi-transferable) for leagues/titles.
- Seasonal **quests** and squad battles.
- Public API: `/profiles/:wallet`, `/duels/:id`, `/leaderboards`.
- Fraud prevention v2: multi-wallet heuristics, on-chain identity links.

---

## Architecture (proposed)
