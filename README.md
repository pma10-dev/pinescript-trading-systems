# pinescript-trading-systems

TradingView Pine Script indicators, signals, alerts, and systematic trading logic.

![Indicator example](images/SPY_img.png)

---

## Overview

A curated collection of TradingView Pine Script (v5) indicators, signal generators, alerts, and systematic trading logic designed for visual validation, backtesting, and alert-driven automation.

This repository follows a professional trading development workflow:

**indicator-first → signal confirmation → alerts → strategy conversion**

---

## Objectives

- Build non-repainting, bar-confirmed trading signals
- Separate signal logic from execution logic
- Enable clean alerts suitable for webhook-based automation
- Provide a solid foundation for strategy backtesting
- Maintain readable, reusable, and production-grade Pine Script

---

## Design Principles

All scripts in this repository adhere to the following principles:

1. Pine Script v5 only  
2. Bar-close confirmation (`barstate.isconfirmed`)  
3. No repainting  
4. Explicit state handling (flat / long / short)  
5. Indicator logic reusable in strategies  
6. Alert logic identical to plotted signals  

This ensures consistency between:

- Visual signals  
- Alerts  
- Backtest results  
- Automation behavior  

---

## Indicator-First Development Approach

The workflow used in this repository:

1. **Indicator**
   - Visual signals
   - Signal validation
   - False-positive reduction
2. **Alerts**
   - Bar-confirmed alerts
   - Optional webhook-ready JSON payloads
3. **Strategy**
   - Convert indicator logic to `strategy()`
   - Backtest without rewriting core logic

This approach avoids curve-fitting and reduces logic divergence.

---

## Alerts & Automation

Scripts are designed to support alert-based automation, including webhook integration.  

Example alert payload:

```json
{
  "action": "BUY",
  "symbol": "{{ticker}}",
  "price": "{{close}}",
  "timeframe": "{{interval}}"
}

Disclaimer
This repository is provided for educational and research purposes only:
No financial advice is given
Past performance does not guarantee future results
Use at your own risk
Always test on paper trading before live deployment

License
MIT License

You are free to:
Use
Modify
Share
With appropriate attribution.

Roadmap
Planned additions include:
Multi-timeframe confirmation examples
ATR-based risk filters
Position sizing logic
Strategy optimization examples
Alert-to-broker integration patterns

Author
Martin Abastos
Focused on systematic trading, signal engineering, and automation-ready market logic.