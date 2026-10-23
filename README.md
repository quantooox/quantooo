# Quantooo: an open quant research lab

**[quantooo.com](https://quantooo.com)** is a free quant research lab for learning how quantitative investing really
works. It scores US (S&P 100) and India (Nifty 50) stocks from 0 to 100 with every calculation step shown, tests
machine learning models with walk-forward backtests and a sealed holdout, and keeps a live track record that is
fingerprinted and timestamped on Bitcoin before the market opens.

## What's here

- **[Discussions](https://github.com/quantooox/quantooo/discussions)**: comments on the site's
  [Learn articles](https://quantooo.com/learn) appear here (one thread per article), plus questions, ideas and critique.
- **Track record**: every day's scores are fingerprinted (SHA-256) and timestamped on the Bitcoin blockchain
  (OpenTimestamps) *before* the market opens, so they can't be changed afterwards. Download and verify them on the
  [track record page](https://quantooo.com/track-record).

## What we found so far

- 12 models, from simple rules to LSTM and GRU networks, tested walk-forward: none ranked stocks reliably by
  next-month return ([model leaderboard](https://quantooo.com/models)).
- The score's sealed final test year came out significantly negative, and we published it
  ([research](https://quantooo.com/research)).
- Forecasting risk works better than forecasting direction
  ([forecasting volatility](https://quantooo.com/learn/forecasting-volatility)).
- A one-year live challenge runs until October 2027: can rule-based portfolios beat their benchmarks?
  ([model portfolios](https://quantooo.com/portfolios)).

## The track record in this repo

[`track_record/`](track_record) holds every published score file, copied here nightly:

| Folder / file | What it is |
|---|---|
| `scores/` | US (S&P 100) scores, one CSV per trading day, with its OpenTimestamps proof (`.ots`) |
| `scores-in/` | India (Nifty 50) scores, same format |
| `preregistration/` | Rules of the one-year challenge, registered before the first trade |
| `ledger.csv` | Date, file name, SHA-256 fingerprint and publication time of every file |
| `CORRECTIONS.md` | Every correction we have made, and why |

**Check a file yourself:** compute its SHA-256 (`sha256sum track_record/scores/2026-10-20.csv` on Linux or macOS,
`certutil -hashfile <file> SHA256` on Windows) and compare it with the row in `ledger.csv`. To check the Bitcoin
timestamp, open the `.ots` file at [opentimestamps.org](https://opentimestamps.org) together with the CSV.
Model-specific files are kept private; the ledger still lists their fingerprints.

Every formula is published on [The math](https://quantooo.com/method). The code that runs the site is private.

## Quant topics covered

Plain-language articles, each backed by tests published on the site:

| Topic | Article |
|---|---|
| Getting started in quant | [What is quant research? A beginner's guide](https://quantooo.com/learn/what-is-quant-research) · [Quant glossary: 30 terms](https://quantooo.com/learn/quant-glossary) · [Free quant tools and data](https://quantooo.com/learn/free-quant-tools-and-data) |
| Quant backtesting | [Quant backtesting checklist: 12 checks](https://quantooo.com/learn/quant-backtesting-checklist) |
| Quant investing in India | [Testing a stock score on the Nifty 50](https://quantooo.com/learn/quant-investing-india-nifty-50) |
| Machine learning for stock prediction | [Can machine learning predict stock returns? We tested 12 models](https://quantooo.com/learn/can-machine-learning-predict-stock-returns) |
| Backtesting pitfalls | [Look-ahead bias](https://quantooo.com/learn/look-ahead-bias) · [Overfitting](https://quantooo.com/learn/overfitting-in-backtesting) · [Survivorship bias](https://quantooo.com/learn/survivorship-bias) · [Trading costs](https://quantooo.com/learn/trading-costs-in-backtests) |
| Backtest methodology | [Walk-forward testing](https://quantooo.com/learn/walk-forward-testing) · [Sealed holdout](https://quantooo.com/learn/sealed-holdout) |
| Factor investing | [Does momentum investing still work?](https://quantooo.com/learn/does-momentum-investing-work) |
| Evaluating signals | [Information coefficient (IC)](https://quantooo.com/learn/information-coefficient) |
| Volatility forecasting | [HAR, GARCH, machine learning and the VIX compared](https://quantooo.com/learn/forecasting-volatility) |

New articles every week, including a weekly summary of the biggest score moves.

## Start here

- [Can machine learning predict stock returns? We tested 12 models](https://quantooo.com/learn/can-machine-learning-predict-stock-returns)
- [What is look-ahead bias in backtesting?](https://quantooo.com/learn/look-ahead-bias)
- [Overfitting in backtesting, explained with a real example](https://quantooo.com/learn/overfitting-in-backtesting)
- [Beginner's guide to the site](https://quantooo.com/guide)

---

*Free and educational. Not investment advice, not a recommendation to buy or sell anything. Results are hypothetical,
not a claim of returns.* Contact: contact@quantooo.com
