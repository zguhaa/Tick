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

Frontend (Next.js + Tailwind)
└─ Wallet Adapter (Phantom/Backpack)
└─ UI State (Zustand)

Index/Backend
└─ Helius APIs for tx parsing & prices
└─ Supabase/Postgres for profiles/duels/XP
└─ CRON jobs to settle duels & recalc XP

Contracts (later)
└─ Minimal program for duel registry & SBT badges


**Tech Stack**
- **TS/Next.js**, **Tailwind**, **Solana Wallet Adapter**
- **Supabase/Postgres**, **Helius**
- **Jupiter** (quotes/swaps; post-MVP)
- (opt) Cloudflare Workers

---

## Scoring
- **PnL** = Σ(exits − entries) over duel window (whitelisted mints).
- **ROI%** = PnL / capital used (capped).
- **XP** = base per duel + win/streak/league bonus; seasonal decay.

---

## Anti-Abuse (v1)
- Duel-locked wallet; cool-down.
- Min trade count / volume threshold.
- Detect hot-wallet hopping (recent transfer graph).
- Public match logs + verifiable settlement.

---

## 2-Week Hackathon Plan
**D1–3**: Auth, profiles, DB schema, leaderboard skeleton  
**D4–7**: Duel create/join, timers, result worker, XP calc  
**D8–10**: Leaderboards, profiles, anti-abuse basics  
**D11–12**: Polish, seed data, demo script  
**D13–14**: Landing, pitch deck, video

---

## Screens / Demo
- `/docs/wireframes/landing.png`
- `/docs/wireframes/duel-flow.png`
*(placeholders; will update during hackathon)*

---

## Team
**ZgCrypto (Founder/Product, BizDev, Growth)** — experience in meme-markets, trader psychology, community building.

---

## Links
- Twitter (soon): `https://x.com/tick_sol`
- One-pager: `/docs/Tick_OnePager.pdf` (WIP)
- Colosseum submission: (add link)

---

## License
TBD (MIT planned after hackathon).

