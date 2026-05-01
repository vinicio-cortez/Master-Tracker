# Projects — Active & Completed
> Last Updated: April 23, 2026

## 🟢 ACTIVE

### Merlyn Trading Engine (Cortez Capital)
- **Status:** Production, paper trading
- **Stack:** Python, yFinance, OpenBB, Streamlit, NinjaTrader, Discord
- **Completed:** ICT pattern detection, MTF confluence, backtesting, Apex bridge, dashboard, Elite signals
- **Next:** Futures roll detection, FRED parsing fix, chart refinement, collect trade data

### Academia FuturosCapital
- **Status:** Pre-revenue, build phase
- **Focus:** Trading education, signal distribution, content pipeline
- **Next:** Content creation, subscription tiers

### Cortez Digital (SEO/Web Agency)
- **Status:** Active, outreach phase
- **Services:** SEO audits, web dev, AI services
- **Next:** Land first client, Carlos partnership materials

## ✅ COMPLETED

- Elite Signal Ecosystem (Apr 20-23)
- Streamlit Dashboard (Apr 22)
- Apex/NinjaTrader CSV Bridge (Apr 21)
- Backtesting Engine (Apr 20)
- 7-Layer Protection Stack (Apr 21)
- Data Aggregator + Macro Checklist (Apr 23)

## 🔜 UPCOMING

- Vault organization
- Papá's Scalper Module (1m/5m bot)
- Subscription infrastructure
- First $1k revenue

## After-Session Fixes (2026-05-01)

### Economic Calendar News Guard
- Fix timezone comparison: make both `datetime.now()` and API event time UTC-aware
- Add maximum blackout of 45 minutes to prevent stuck timer
- Fix "0 min after" display message
- Clear `.pyc` cache after fix to ensure changes take effect
- Re-enable news guard after testing

### Daily Summary Syntax Warning
- Fix invalid escape sequence `\$` on main.py line 543

### Duplicate Process Issue
- Investigate why nohup spawns child main.py process
