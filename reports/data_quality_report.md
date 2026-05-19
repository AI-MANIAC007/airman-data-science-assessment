# Data Quality Report

## Overview

This report summarizes the data validation and quality assessment performed on the datasets used for the AIRMAN Skynet + TOGA Intelligence assessment.

Datasets validated:
- sorties.csv
- aircraft.csv
- cadets.csv
- instructors.csv
- toga_study.csv
- payments.csv

Validation checks focused on:
- Missing values
- Duplicate records
- Invalid operational logic
- Incorrect calculations
- Aviation workflow inconsistencies
- Study data anomalies
- Financial inconsistencies

---

# 1. sorties.csv Validation

## Checks Performed
- Missing values
- Duplicate sortie IDs
- Invalid scheduled times
- Invalid actual flight times
- Invalid status values
- Completed sorties without actual times
- Cancelled sorties with actual flight times
- Delay minute mismatches
- Negative delay values
- Invalid flight durations
- Missing cancellation reasons

---

## Findings

### Missing Values
- `actual_start` contains 18 missing values
- `actual_end` contains 18 missing values
- `cancel_reason` contains 82 missing values

The missing actual flight times correspond to cancelled sorties and are operationally acceptable.

### Duplicate Sortie IDs
No duplicate sortie IDs were found.

### Invalid Scheduled Times
No cases found where:
```text
scheduled_start > scheduled_end
```

### Invalid Actual Flight Times
No cases found where:
```text
actual_start > actual_end
```

### Invalid Status Values
No invalid sortie status values were detected.

Valid statuses used:
- completed
- cancelled
- delayed
- scheduled

### Completed Sorties Without Actual Times
No completed sorties were missing actual start or end times.

### Cancelled Sorties With Actual Flight Times
No cancelled sorties contained actual flight timestamps.

### Delay Minute Validation
No delay mismatches were detected between recorded and calculated delays.

### Negative Delay Values
No negative delays were identified.

### Invalid Flight Durations
No invalid or unrealistic flight durations were found.

### Missing Cancellation Reasons
No cancelled sorties were missing cancellation reasons.

---

## Operational Impact

The sortie dataset is operationally consistent and suitable for:
- dispatch reliability analysis
- aircraft utilization calculations
- instructor workload analysis
- cadet training progress analysis

The dataset demonstrates good scheduling and operational integrity.

---

# 2. aircraft.csv Validation

## Checks Performed
- Missing values
- Duplicate aircraft IDs
- Invalid registration values
- Negative available hours
- Negative maintenance downtime
- Negative defect counts
- Downtime greater than available hours
- Unusually high defect counts
- Invalid aircraft types

---

## Findings

### Missing Values
No missing values were identified.

### Duplicate Aircraft IDs
No duplicate aircraft IDs were found.

### Invalid Registration Values
No invalid aircraft registration formats were detected.

### Negative Values
No negative values were found for:
- total available hours
- maintenance downtime hours
- defect count

### Downtime Validation
No aircraft had maintenance downtime exceeding available operational hours.

### High Defect Counts
Two aircraft showed unusually high defect counts:

| Aircraft ID | Aircraft Type | Defect Count |
|---|---|---|
| A004 | PA28 | 12 |
| A008 | C172 | 14 |

These aircraft may require maintenance review and operational monitoring.

### Invalid Aircraft Types
No invalid aircraft types were identified.

---

## Operational Impact

Aircraft with high defect counts may:
- increase sortie cancellation rates
- reduce aircraft availability
- affect cadet training continuity
- increase operational maintenance costs

These aircraft should be monitored by maintenance operations teams.

---

# 3. cadets.csv Validation

## Checks Performed
- Date conversion validation
- Missing values
- Duplicate cadet IDs
- Invalid course values
- Negative required hours
- Negative flown hours
- Flown hours greater than required hours
- Invalid enrollment dates
- Future enrollment dates

---

## Findings

### Enrollment Date Conversion
Enrollment dates were successfully converted into datetime format.

### Missing Values
No missing values were detected.

### Duplicate Cadet IDs
No duplicate cadet IDs were found.

### Invalid Course Values
No invalid course values were identified.

Valid course values:
- PPL
- CPL
- IR

### Negative Values
No negative values were detected for:
- total required hours
- total flown hours

### Flown Hours Validation
No cadets exceeded their required training hours.

### Enrollment Date Validation
No invalid or future enrollment dates were detected.

---

## Operational Impact

The cadet dataset is consistent and suitable for:
- progress tracking
- cadet completion analysis
- training risk assessment
- operational planning

---

# 4. instructors.csv Validation

## Checks Performed
- Missing values
- Duplicate instructor IDs
- Negative duty hours
- Negative flight hours
- Flight hours greater than duty hours
- Unusually high instructor workload

---

## Findings

### Missing Values
No missing values were found.

### Duplicate Instructor IDs
No duplicate instructor IDs were identified.

### Negative Values
No negative values were found for:
- total duty hours
- total flight hours

### Flight Hours Greater Than Duty Hours
Two instructors showed inconsistent operational records where flight hours exceeded duty hours:

| Instructor ID | Duty Hours | Flight Hours |
|---|---|---|
| I001 | 114 | 130 |
| I009 | 118 | 127 |

This may indicate:
- incorrect logging
- duplicate flight entries
- inaccurate duty tracking

### High Instructor Workload
Two instructors showed unusually high duty workloads:

| Instructor ID | Duty Hours |
|---|---|
| I003 | 199 |
| I012 | 181 |

These instructors may be at risk of operational fatigue or scheduling imbalance.

---

## Operational Impact

Incorrect instructor duty records may affect:
- workload balancing
- fatigue analysis
- instructor utilization metrics
- safety oversight

High workload instructors should be monitored operationally.

---

# 5. toga_study.csv Validation

## Checks Performed
- Date conversion validation
- Missing values
- Duplicate cadet-subject combinations
- Negative chapters completed
- Negative total chapters
- Chapters completed greater than total chapters
- Invalid quiz scores
- Future activity dates
- Negative practice test attempts
- Cadets with no recent activity
- Invalid subject values

---

## Findings

### Date Conversion
Last active dates were successfully converted into datetime format.

### Missing Values
No missing values were identified.

### Duplicate Cadet-Subject Combinations
Multiple duplicate cadet-subject records were found.

Examples include:
- C004 – Meteorology
- C019 – Navigation
- C020 – Air Regulations
- C027 – Meteorology
- C033 – Instrument Procedures

These duplicates may represent:
- repeated study attempts
- duplicated sync records
- multiple learning sessions

### Negative Values
No negative values were detected.

### Study Progress Validation
No cases found where:
```text
chapters_completed > total_chapters
```

### Quiz Score Validation
All quiz scores were within valid range:
```text
0–100
```

### Future Activity Dates
No future dates were detected.

### Practice Test Validation
No negative practice test counts were identified.

### Cadets With No Recent Activity
67 cadet study records showed inactivity greater than 30 days.

This may indicate:
- low study engagement
- cadet disengagement risk
- poor TOGA adoption

### Invalid Subject Values
No invalid subject names were detected.

---

## Operational Impact

Inactive cadets may:
- perform poorly in assessments
- experience training delays
- require instructor intervention

Duplicate cadet-subject entries should be reviewed for proper session tracking logic.

---

# 6. payments.csv Validation

## Checks Performed
- Date conversion validation
- Missing values
- Duplicate cadet IDs
- Negative invoiced amounts
- Negative paid amounts
- Negative outstanding amounts
- Paid amount greater than invoiced amount
- Incorrect outstanding calculations
- Future payment dates

---

## Findings

### Date Conversion
Payment dates were successfully converted into datetime format.

### Missing Values
No missing values were identified.

### Duplicate Cadet IDs
No duplicate cadet payment records were found.

### Negative Financial Values
No negative values were detected for:
- invoiced amount
- paid amount
- outstanding amount

### Payment Validation
No cases found where:
```text
paid_amount > invoiced_amount
```

### Outstanding Amount Validation
All outstanding amounts matched:
```text
invoiced_amount - paid_amount
```

### Future Payment Dates
No future payment dates were detected.

---

## Operational Impact

The payment dataset is financially consistent and suitable for:
- payment risk analysis
- cadet financial monitoring
- operational revenue tracking

---

# Overall Validation Summary

| Dataset | Major Issues Found |
|---|---|
| sorties.csv | No major issues |
| aircraft.csv | High defect aircraft |
| cadets.csv | No major issues |
| instructors.csv | Duty-hour inconsistencies |
| toga_study.csv | Duplicate records, inactive cadets |
| payments.csv | No major issues |

---

# Key Data Quality Risks

1. High aircraft defect counts may affect operational reliability.
2. Instructor duty inconsistencies may distort utilization metrics.
3. Large TOGA inactivity population may indicate learning disengagement.
4. Duplicate cadet-subject study records may affect learning analytics accuracy.

---

# Conclusion

Overall, the datasets are largely clean and operationally usable for analytics, visualization, and cadet risk scoring.

The primary concerns identified are:
- high aircraft defect counts,
- instructor workload inconsistencies,
- and cadet study inactivity patterns.

Addressing these issues would improve operational intelligence quality for both Skynet and TOGA systems.
