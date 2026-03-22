# ONYX
### Caribbean Intelligence Terminal — v12.0

> Closed-loop open-source intelligence aggregation platform for Caribbean regional monitoring. Built for OECS member states, IMPACS, and designated national security ministries.

---

## Overview

ONYX is a sovereign OSINT terminal that aggregates real-time data from a hardened node manifest spanning 10+ OECS nations. It ingests live RSS feeds, government portals, law enforcement communications, and legislative sources — runs them through a proprietary signal filtering engine — and surfaces actionable intelligence in a unified, authenticated dashboard.

Deployed as a single production-grade HTML file. No framework dependencies. No build step. Runs anywhere.

---

## Regions Covered

| Region | Sources |
|---|---|
| 🇱🇨 Saint Lucia | RSLPF / GOVT.LC, Saint Lucia News Online, NEMO, OPM, Legislations, St Lucia Times RSS, The Voice SLU RSS, St Lucia Star RSS |
| 🇹🇹 Trinidad & Tobago | Trinidad Express, TT Guardian, Newsday TT |
| 🇯🇲 Jamaica | Jamaica Gleaner, Jamaica Observer |
| 🇧🇧 Barbados | Nation News, Barbados Today |
| 🇬🇾 Guyana | Stabroek News, Kaieteur News |
| 🇦🇬 Antigua & Barbuda | Antigua Observer, Daily Observer, ABS Live |
| 🇩🇲 Dominica | Dominica News Online, The Sun Dominica, Dominikavibes |
| 🇬🇩 Grenada | Now Grenada, Loop News Grenada |
| 🇰🇳 St. Kitts & Nevis | SKN News Online, IWN SVG |
| 🇻🇨 St. Vincent & the Grenadines | IWNSVG, Searchlight, Vincentian News |

---

## Core Features

**Intelligence Engine**
- Closed-loop node manifest — 8 SLU-linked sources + multi-region expansion
- Sovereign Scrubber™ — proprietary signal filtering engine with relaxed and strict pass modes
- ONYX Threat Score Engine™ — automated CRIT / WARN / INFO signal classification
- HUMINT / SIGINT manual entry module for operator-sourced intelligence
- Audit log with timestamped entry tracking

**Economic Pulse**
- ECCB-anchored SLU Macro Index (2024–2026)
- Real-time KPI display: GDP growth, tourism inflow, inflation, fiscal stability
- Source-attributed data from STATS.GOV.LC and ECCB-CENTRALBANK.ORG

**Persistence & Sync**
- IndexedDB primary storage with localStorage fallback
- Supabase cross-device sync — configurable via Settings
- Session-scoped feed caching with configurable auto-sweep intervals

**Security**
- SHA-256 credential hashing
- 3-attempt lockout on failed authentication
- Configurable credential rotation
- Operator role management via Settings

**Design System**
- Obsidian & Bone aesthetic — `#000000` base, `#F0F0F0` bone, JetBrains Mono throughout
- Sub-pixel border system (`0.5px`) with layered depth
- Responsive — collapses gracefully to single-column on mobile

---

## Tech Stack

- **Runtime**: Vanilla JS — zero dependencies, zero build tooling
- **Storage**: IndexedDB + localStorage + Supabase (optional)
- **Auth**: SHA-256 client-side hashing
- **Data**: RSS 2.0 parsing + HTML scraping via proxy relay (AllOrigins / ScraperAPI slot)
- **Typography**: JetBrains Mono (Google Fonts)
- **Deployment**: Single `.html` file — serve from any static host, Pi, or open locally

---

## Deployment

```bash
# Serve locally
npx serve .

# Or open directly in browser
open onyx-v12.html
```

For Pi deployment, serve via any lightweight HTTP server (e.g. `http-server`, `serve`, or `nginx`).

---

## Architecture

```
onyx-v12.html
├── Login & SHA-256 Auth
├── Boot Sequence
├── App Shell
│   ├── Top Bar — Region Selector + Live Status
│   ├── Panel Nav — Feed / Econ Pulse / Alerts / Watch / Nodes / Threat Matrix / Audit / Settings
│   ├── Feed Panel — Live intelligence stream per region
│   ├── Econ Pulse — ECCB macro indicators
│   ├── Nodes Panel — Node health monitor (8 linked)
│   ├── Threat Matrix — Signal severity grid
│   ├── Audit Log — Full entry history
│   └── Settings — Agency config, sweep intervals, Supabase sync, credential rotation
├── Persistence Layer (IDB + localStorage)
├── Sovereign Scrubber Engine
├── Node Sweep Engine
└── Status Bar — Live node count, sweep state, UTC clock
```

---

## Legal

All data ingested by ONYX is sourced from publicly accessible web pages and RSS feeds. ONYX does not access, store, or process any classified, private, or personally identifiable information beyond what is already in the public domain. Aggregation is conducted under fair dealing provisions applicable in OECS jurisdictions for purposes of news monitoring and security analysis.

---

*ONYX Systems © 2026 — Caribbean Intelligence Grid*
