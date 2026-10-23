# Pre-registration: one-year live test of the India (Nifty 50) model portfolios

Registered 20 Oct 2026, before the first India trade. This file is fingerprinted (SHA-256) in `track_record/ledger.csv`
and timestamped with OpenTimestamps. Hypothetical paper trading, for research and education; not a claim of returns and
not investment advice.

## Question
Over one year of live, rule-based paper trading on the Nifty 50, do the score-based portfolios do better than their
benchmarks?

## Period
From the first rebalance after 19 Oct 2026, at the NSE open, for one year (about 250 trading days). Scores come only from
the published, fingerprinted India files (`scores-in/`, score version in-v1). Nothing is back-filled.

## Portfolios and their benchmarks
| Portfolio | Rule | Benchmark(s) |
|---|---|---|
| Long-only top 10 | Weekly: the 10 highest India scores, equal weight | Nifty 50 index; equal-weight Nifty 50 |
| Long-short | Weekly: long the top 10% (5 stocks), short the bottom 10% (5 stocks), dollar-neutral | Zero (cash); random long-short of the same size |

Every portfolio rebalances at the open of the first trading day of each week, with 5 bp costs on traded value. The Nifty 50
index (`^NSEI`) is the price benchmark. It is an index, so holding it here is hypothetical.

## What counts as "better" (decided now)
1. **Simple:** higher total return after costs than the benchmark over the year.
2. **Strict:** a higher Sharpe ratio, with a one-sided block-bootstrap p-value below 0.05 (20-day blocks, 2,000 draws).
   Passing (1) without (2) is reported as "no reliable evidence either way".
3. **Concentration:** the share of profit from the top three stocks is reported.

## Expectation (stated in advance)
India's sealed holdout showed no ranking skill (rank correlation +0.009, t = 0.21). We expect these portfolios **not** to
beat their benchmarks reliably. The simulated history flatters every Nifty portfolio, because it uses today's index
members, companies that joined the index because they grew (survivorship bias). The live year has no such bias.

## Rules for the year
- No changes to the rules, weights or score version during the year. A change would start a new, separately reported
  portfolio.
- Data or publishing errors go in the public corrections log.
- The results are published whatever they are.
