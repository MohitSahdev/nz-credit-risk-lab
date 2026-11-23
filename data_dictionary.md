# Data dictionary

Source: LendingClub accepted loans 2007–2018 (Kaggle), 2,260,701 loans, 151 columns.

## Filters
- 36-month loans only
- Issued 2012 to 2015, so every loan has finished by Dec 2018
- Only loans with a known outcome: Fully Paid, Charged Off, Default
- Dropped 2 rows with missing dti
- Result: 589,486 loans, bad rate 14.0%

## Columns kept
| Column | Meaning | Notes |
|---|---|---|
| id | Loan ID | Not used in the model |
| loan_amnt | Amount borrowed | |
| term | Loan length | All 36 months after filter |
| int_rate | Interest rate (%) | Set by LendingClub from grade |
| grade | LendingClub risk grade, A (safest) to G | |
| sub_grade | Finer grade, A1 to G5 | |
| emp_length | Years in current job (text) | 6% missing |
| home_ownership | Rent, own or mortgage | |
| annual_inc | Yearly income | |
| purpose | Reason for the loan | |
| dti | Debt-to-income ratio (%) | |
| issue_d | Month the loan was issued | Used for the filter only |
| loan_status | Final status | Used to build the target |

## New columns
| Column | Meaning |
|---|---|
| bad | Target: 1 = Charged Off or Default, 0 = Fully Paid |
| emp_years | emp_length as a number, 0 to 10 ("10+ years" = 10) |
| emp_missing | 1 if emp_length was blank. Blank applicants defaulted more (20.5% vs 13.6%) |

## Columns left out on purpose
### Leakage: only known after the loan starts
| Column | Why left out |
|---|---|
| total_pymnt | Total paid back, known only at the end |
| recoveries | Money recovered after default |
| last_pymnt_d | Date of last payment |
| out_prncp | Amount still owed |

### Credit history: known at application, may add in Module 1
| Column | Meaning |
|---|---|
| fico_range_low, fico_range_high | Credit score range |
| delinq_2yrs | Late payments in the last 2 years |
| inq_last_6mths | Credit checks in the last 6 months |
| revol_util | How much of the credit card limit is used |
| earliest_cr_line | Date of first credit account |