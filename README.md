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

## 3-Week Development Roadmap

### Week 1 — Core Setup & Prototype
- Project structure setup (frontend + backend base).  
- Wallet connection (Phantom / Backpack).  
- Static profile pages (XP, rank, basic layout).  
- Mock duel data (JSON-based simulation).  
- Landing page with project concept and visuals.  

*Goal:* Have a working UI prototype with wallet connect and static duel preview.

---

### Week 2 — Logic & Leaderboards
- Database integration (Supabase or Firebase).  
- Create & join duel flow (mock logic for now).  
- XP / rank calculation system (client-side simulation).  
- Global leaderboard (real-time display from DB).  
- Profile activity history.  

*Goal:* Demonstrate full core loop — wallet connect → duel → XP update → leaderboard.

---

### Week 3 — Demo Polish & Expansion Prep
- Visual polishing, animations, mobile layout.  
- Add early anti-abuse logic (wallet lock, cooldown).  
- Prepare demo script + video walkthrough.  
- Create one-pager & investor-ready presentation.  
- Setup dev environment for future on-chain logic (Jupiter integration later).  

*Goal:* MVP-ready prototype and full visual demo for Colosseum review.

---

**Note:**  
All on-chain data (PnL, ROI) will be mocked in the MVP.  
Real blockchain integration (Helius/Jupiter APIs) planned post-hackathon.

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

