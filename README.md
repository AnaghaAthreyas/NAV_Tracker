# Portfolio Net Asset Value Tracker

**Author:** Anagha Athreyas
**Tools:** Python, yfinance, pandas, openpyxl

---

## What This Project Is

When you invest money in a fund, the fund manager needs to calculate the value of the fund every single day. This daily value is called the Net Asset Value — it tells you exactly how much the fund is worth after accounting for all holdings and costs.

This project automates that entire calculation process from scratch using real live market data.

---

## Why I Built It

In fund accounting roles at firms like BNY, State Street, and JPMorgan, one of the core daily responsibilities is calculating Net Asset Value for client funds — checking that the numbers are accurate, flagging anything unusual, and producing a report for review.

I built this project to understand and replicate that workflow hands-on, using real market data and institutional logic.

---

## What the Project Does

- Pulls live closing prices for 8 stocks across North America, Europe, and Asia Pacific using Yahoo Finance
- Calculates daily Gross Asset Value — total market value of all positions plus cash
- Accrues fund expenses daily using a configurable annual expense ratio (default 0.75%)
- Calculates Net Asset Value and Unit Price for each trading day
- Flags exception days where Net Asset Value moves more than 2% — rated HIGH or MEDIUM severity
- Exports a formatted 3-sheet Excel management report

---

## Output Report

| Sheet | Contents |
|---|---|
| NAV History | Daily Gross Asset Value, Net Asset Value, Unit Price, Daily Return, Exception Flag |
| Positions Snapshot | Holdings with current price, market value, unrealized Profit and Loss |
| Exception Log | Days where Net Asset Value moved beyond the review threshold with severity rating |

---

## Setup

Open nav_tracker.ipynb in Jupyter Lab and run all cells in order.

pip install yfinance pandas openpyxl

---

## Portfolio Configuration

Edit the PORTFOLIO dictionary in Cell 2 to change stocks, shares, and cost basis. All fund parameters including expense ratio, units issued, and exception threshold are also configurable in the same cell.
