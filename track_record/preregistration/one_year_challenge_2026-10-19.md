# Pre-registration: one-year live test of the model portfolios

Registered 20 Oct 2026, before any live result is known. This file is fingerprinted (SHA-256) in `track_record/ledger.csv`
and timestamped with OpenTimestamps, so it cannot be changed without that showing. Hypothetical paper trading, for research
and education; not a claim of returns and not investment advice.

## Question
Over one year of live, rule-based paper trading, do the score-based portfolios do better than their benchmarks?

## Period
From the first rebalance, at the open on **19 Oct 2026**, to the close on **19 Oct 2027**: about 252 trading days.
Scores come only from the published, fingerprinted daily files. Nothing is back-filled.

## Portfolios and their benchmarks (rules as published on the Portfolios page; score version v1)
| Portfolio | Rule | Benchmark(s) |
|---|---|---|
| Long-only top 10 | Weekly: the 10 highest scores, equal weight | S&P 500 (SPY); equal-weight universe |
| Long-short | Weekly: long the top 10%, short the bottom 10%, equal weight, dollar-neutral | Zero (cash); random long-short of the same size |
| Risk-managed S&P 500 | Weekly: SPY sized to 16% yearly volatility using the E1 forecast, at most 1.5× | S&P 500 buy-and-hold |

Every portfolio rebalances at the open of the first trading day of each week, with 5 bp costs on traded value.

## What counts as "better" (decided now)
1. **Simple:** higher total return after costs than the benchmark over the full year.
2. **Strict:** a higher Sharpe ratio, with a one-sided block-bootstrap p-value below 0.05 for the difference (20-day blocks,
   2,000 draws). One year is short, so passing (1) without (2) will be reported as "no reliable evidence either way".
3. **Concentration:** the share of profit from the top three stocks is reported. A result that depends on one or two stocks
   is called that.

## Expectation (stated in advance)
Our research found no reliable ability of the score to rank stocks; on the sealed holdout it ranked them backwards. We
therefore expect the long-only and long-short portfolios **not** to beat their benchmarks reliably. The risk-managed
portfolio uses the one forecast that tested better than its benchmark (S&P 500 volatility), but even there the research
found no reliable gain in returns.

## Rules for the year
- No changes to the rules, weights or score version during the year. A change would start a new, separately reported
  portfolio, and this one would continue unchanged.
- Data or publishing errors go in the public corrections log, with their effect on results.
- The results are published on the site whatever they are: monthly progress, and a final report after 19 Oct 2027.

## Not covered
India (Nifty 50) has no portfolios yet. If they are added later, they get their own pre-registration before their first
trade.
