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

## Backtest Findings (2026-05-01)

### Key Insights
- **LONG vs SHORT**: 46/46 LONG wins (100%) vs 0/16 SHORT wins (0%). RL agents correctly blocking shorts.
- **Confidence**: MEDIUM 95.8% win rate. LOW 0%. LOW = guaranteed loss.
- **Two-Stage Trail**: +$4,800 improvement over original. 100% profitable in Monte Carlo.
- **MTF Data**: Only 2 trades have MTF scores saved. Need to enrich paper_trades.json.

### Action Items
- Save MTF score and bias with every trade in _save_closed_trade
- Increase RL agent short-blocking threshold (currently agents vote 0/2 on shorts)
- Consider momentum fallback only for MEDIUM confidence, never LOW

## Final Backtest Results (2026-05-01)

### Two-Stage Trail Validation
- **62 trades tested, 1000 Monte Carlo simulations**
- **100% probability of profit**
- **+$4,800 average P&L** (vs -$179.75 original)
- **96.8% win rate** (vs 74.2% original)

### Optimal Parameters (Confirmed)
- Activation: 0.25R
- Trail Distance: 1.5x ATR
- TP Multiplier: 2.0x ATR
- Stage 2 trigger: 1R profit (tightens trail by 50%)

### LONG vs SHORT
- LONGS: Original +$380 → With Trail +$3,679 (+3,299)
- SHORTS: Original -$560 → With Trail +$1,119 (+1,679)
- Both 100% profitable in Monte Carlo

### Data Enrichment
- _save_closed_trade now captures: stop, target, confidence, confluence_score, setup_type, bias, mtf_consensus, market_regime
