<h1 align="center">Stock Screener</h1>

<p align="center">
  <b>Daily-updated stock screeners with backtested returns.</b><br/>
  19 institutional-grade strategies. One API. Real numbers, not promises.
</p>

<p align="center">
  <a href="https://stock-screener-app-casssdf7wcjmwbp5fevysf.streamlit.app"><b>Live dashboard →</b></a>
  &nbsp;·&nbsp;
  <a href="https://rapidapi.com/stock-screener-stock-screener-default/api/stock-screener6"><b>Get the API →</b></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/stock-screener-click/stock-screener-dashboard"><b>Dashboard source →</b></a>
</p>

<p align="center">
  <a href="https://stock-screener-app-casssdf7wcjmwbp5fevysf.streamlit.app">
    <img src="https://github.com/stock-screener-click/stock-screener-dashboard/raw/main/docs/screenshot.png" alt="Stock Screener dashboard" width="720"/>
  </a>
</p>

---

## What you get

- **19 backtested screeners** — quality, value, momentum, dividend, GARP, fortress balance sheet, small-cap momentum, and more
- **Realized returns, not just lists** — every strategy ships with its actual 7d / 14d / 1m / 3m / 6m / 1y cohort returns
- **Daily refresh** — picks update once per day, automatically
- **Consensus picks** — see which tickers pass the most independent strategies on the same day
- **Per-ticker lookup** — for any symbol, see every screener that has ever picked it

## Quickstart

```bash
curl -H "X-RapidAPI-Key: $RAPIDAPI_KEY" \
     -H "X-RapidAPI-Host: stock-screener6.p.rapidapi.com" \
     "https://stock-screener6.p.rapidapi.com/tickers/popular?limit=10"
```

```python
import requests

r = requests.get(
    "https://stock-screener6.p.rapidapi.com/stock-screeners/performance",
    params={"window": "1m"},
    headers={
        "X-RapidAPI-Key": "YOUR_KEY",
        "X-RapidAPI-Host": "stock-screener6.p.rapidapi.com",
    },
    timeout=15,
)
for s in r.json()["screeners"][:5]:
    print(f"{s['short_name']:35s} {s['avg_return_pct']:+.2f}%  (n={s['n']})")
```

→ **[Get a free API key](https://rapidapi.com/stock-screener-stock-screener-default/api/stock-screener6)**

## Repos

| Repo | What it is |
|---|---|
| [**stock-screener-dashboard**](https://github.com/stock-screener-click/stock-screener-dashboard) | Streamlit dashboard — reference implementation, deployable in 2 minutes |
| [**stock-screener-python-quickstart**](https://github.com/stock-screener-click/stock-screener-python-quickstart) | ~30 lines of Python to get you from key → picks |

## Use cases

- 📈 **Daily trade ideas** — pull fresh candidates from a quality / value / momentum strategy each morning
- 🤖 **Trading bots** — wire `/tickers/latest` into your execution layer as the day's candidate universe
- 🏆 **Strategy leaderboard** — rank screeners by realized return and feature the top performer in a newsletter
- 🔬 **Quant research** — pull historical cohorts to study factor exposure, turnover, and sector drift
- 💬 **Discord / Slack bots** — post each morning's new picks into a channel
- 📓 **Trading journals** — auto-tag closed trades with the screeners they appeared in on entry

## Endpoints at a glance

```
GET /stock-screeners                              # list all 19 strategies
GET /tickers/latest?screener_id=...               # current picks
GET /tickers/popular                              # consensus watchlist
GET /tickers/{ticker}/screeners                   # reverse lookup
GET /stock-screeners/performance?window=1m        # leaderboard
GET /stock-screeners/performance/history          # forward returns over time
GET /stock-screeners/performance/leaderboard      # top individual tickers
```

Full docs on the [RapidAPI listing](https://rapidapi.com/stock-screener-stock-screener-default/api/stock-screener6).

---

<p align="center">
  <sub>For informational and research purposes only. Backtested returns are not a guarantee of future performance. Not investment advice.</sub>
</p>
