## Secure-Life-General-Hospital-Operations-Billing-Dashboard

## Introduction

![](intro.png)

Secure Life General Hospital has seen changes in patient admissions, outstanding medical bills and insurance coverage across its departments, but it has no single report showing its operational and financial performance. This project analyses 1,000 patient visits (January 2024 to December 2025) and turns the raw data into an interactive dashboard that helps management monitor performance and make decisions.

## Dashboard

![](dashboard.png)


## Dataset
| Field | Meaning |
|--|--|
| Patient ID | Unique ID for each visit or record |
| Patient Name | Name of the patient |
| Age | Age in years at the time of the visit |
| Gender | Gender as recorded |
| Admission Date / Discharge Date | Start and end of the stay|
| Department | Where the patient was treated |
| Diagnosis | Recorded medical condition |
| Total Bill Amount | Total charged for treatment and services |
| Insurance Coverage % | Share of the bill covered by insurance |
| Payment Status | Paid, Pending or Partially Paid |

Each row is one patient visit, not necessarily one unique patient.

## Data checks


- 1,000 rows, 11 columns
- No missing values and no duplicate Patient IDs
- No discharge date earlier than its admission date
- Length of stay ranges from 1 to 14 days


## Method


- **Length of stay** = discharge date minus admission date (days)
- **Age groups**: 0-17, 18-34, 35-49, 50-64, 65+
- **Estimated outstanding balance** = Total Bill x (1 - Insurance %) for Pending and Partially Paid visits. The dataset has no amount received, so Partially Paid is counted in full. Treat the result as an upper limit.
- The dataset does not state a currency, so amounts are shown as recorded.

## Findings (answers to the project objectives)

| # | Question | Finding |
|--|--|--|
| 1 | Patient visits | 1,000 |
| 2 | Busiest departments | General 252, Emergency 190, Orthopedics 159, Pediatrics 153, Cardiology 152, Neurology 94 |
| 3 | Highest total bills | Orthopedics 2.55M, Cardiology 2.10M, Neurology 1.22M, General 0.99M, Emergency 0.62M, Pediatrics 0.57M |
| 4 | Average length of stay | Orthopedics 8.4 days, Neurology 6.9, Cardiology 6.5, General 3.9, Pediatrics 3.0, Emergency 2.0 (overall 4.8) |
| 5 |Payment status | Paid 56.4%, Pending 25.7%, Partially Paid 17.9% of bills |
| 6 | Billed vs outstanding | 8.05M billed; about 1.03M estimated outstanding |
| 7 | Insurance coverage | Averages 74% to 76% in every department; the real variation is by diagnosis and the 44 visits with 0% cover |
| 8 | Age groups | 65+ 243, 50-64 235, 35-49 216, 0-17 153, 18-34 153 |
| 9 | Change over time | 2024: 508 visits, 4.13M billed. 2025: 492 visits, 3.92M billed |
| 10 | Management attention | See below |

## Areas needing management attention


1. 44% of visits (436 of 1,000) are not fully paid, carrying 43% of billed value.
2. Orthopedics holds the largest estimated unpaid balance (about 314K, 31% of the total) and is also the highest-billing department with the longest stays.
3. 44 visits have no insurance cover, and 73% of them are unpaid.
4. Insurance cover is flat across departments, so differences in unpaid bills come from other factors such as bill size and diagnosis. This needs further review.
5. General sees the most visits but bills far less per visit than Orthopedics or Cardiology.
