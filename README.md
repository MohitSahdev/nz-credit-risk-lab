# NZ Credit Risk Lab

**Status: In progress (started November 2026)**

An end-to-end credit risk project, built the way a New Zealand Bank would do it: from raw loan data to a scorecard, stress testing, monitoring and regulation.

## Why I am building this
I have 10+ years of experience in operations and reporting, and an MBA in
Finance. I am now doing a Master of Applied Data Science at the University
of Canterbury, and I am building this lab to learn credit risk modelling
the way NZ banks do it.

## Planned modules
| # | Module | What it covers |
|---|---|---|
| 1 | PD scorecard | Logistic regression scorecard using WOE and IV |
| 2 | ML challenger | A machine learning model compared with the scorecard |
| 3 | Stress test and IFRS 9 ECL | Expected credit loss under different economic scenarios |
| 4 | Monitoring and live app | Drift checks (PSI) and a simple web app |
| 5 | RBNZ regulation assistant | A search tool for RBNZ rules using RAG |

## Data
Lendingclub accepted loans, 2007 to 2018 (Kaggle). The raw file is not stored in this repo. A script in "src/" builds the clean subset

## Repo structure
- "data/" raw and clean data (not committed)
- "notebooks/" analysis notebooks
- "src/" python scripts
- "reports/" charts and findings

## Progress
- [ ] Part 1: data and statistics foundations
- [ ] Module 1: PD scorecard
- [ ] Module 2: ML challenger
- [ ] Module 3: Stress test and IFRS 9 ECL
- [ ] Module 4: Monitoring and live app
- [ ] Module 5: RBNZ regulation assistant