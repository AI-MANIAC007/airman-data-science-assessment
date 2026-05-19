# Skynet operations analysis

## Overview

This report summarizes the operational analysis performed on aircraft utilization, instructor utilization, and dispatch reliability using the cleaned Skynet training operations datasets. The analysis was done to identify operational inefficiencies, utilization patterns, instructor workload issues, and recurring delay or cancellation factors.

---

# Aircraft utilization analysis

Aircraft utilization across both bases was generally low. Most aircraft were operating below 15% utilization even though sufficient available hours were present. This indicates that aircraft resources are not being fully used during training operations.

Base B02 showed slightly better utilization compared to B01.

| base | average utilization |
|------|---------------------|
| B01 | 6.94% |
| B02 | 8.01% |

Aircraft A008 recorded the highest utilization at around 12.83%, while A007 showed the lowest utilization at 4.49%.

All aircraft fell under the underutilized category based on the chosen threshold of 20%.

### High defect aircraft

Two aircraft showed unusually high defect counts:

- A004 → 12 defects
- A008 → 14 defects

Frequent defects may impact dispatch reliability and maintenance scheduling.

### Maintenance downtime observations

Several aircraft recorded high maintenance downtime values. Aircraft A010 had the highest downtime of 80 hours, while A009 and A005 also showed significant downtime.

The high downtime values appear to contribute to the low utilization percentages observed across the fleet.

### Aircraft requiring operational review

Aircraft A004 and A008 were flagged for operational review because they showed both:
- high defect counts
- low operational utilization

These aircraft may require detailed maintenance inspection or scheduling adjustments.

---

# Instructor utilization analysis

Instructor utilization showed large variation across the training staff.

Some instructors had very high utilization percentages:
- I001 → 92.86%
- I009 → 92.70%
- I013 → 87.14%

This suggests that certain instructors are heavily involved in flight operations.

At the same time, a few instructors showed low utilization levels below 40%, indicating uneven workload distribution.

### Overloaded instructors

The following instructors exceeded the selected duty hour threshold of 180 hours:

- I003 → 199 duty hours
- I012 → 181 duty hours

Continuous high duty hours may increase fatigue risk and scheduling pressure.

### Underutilized instructors

The following instructors were identified as underutilized:
- I002
- I003
- I007
- I010
- I011

Better redistribution of sortie assignments could help improve instructor balancing.

### Qualification mismatch risks

A significant number of qualification mismatches were detected between instructor qualification type and assigned aircraft type.

A total of 80 mismatch cases were identified.

Example:
- Instructor qualified for C152 assigned to PA28
- Instructor qualified for C172 assigned to DA40

These mismatches may indicate:
- incorrect assignment records
- training allocation issues
- qualification tracking problems

This area requires immediate operational validation because qualification mismatches can become a safety concern.

---

# Dispatch reliability analysis

A total of 100 sorties were analyzed.

| metric | value |
|--------|-------|
| total sorties | 100 |
| completed sorties | 82 |
| cancelled sorties | 18 |
| delayed sorties | 82 |

The completion rate was 82%, while the cancellation rate was 18%.

A high number of sorties experienced delays, with an average delay of approximately 17.63 minutes.

### Cancellation analysis

The most common cancellation reason was instructor unavailability.

| cancellation reason | count |
|--------------------|------|
| Instructor Unavailable | 6 |
| Aircraft Defect | 5 |
| Weather | 4 |
| ATC Restriction | 3 |

This suggests that instructor scheduling and aircraft maintenance are contributing factors affecting sortie completion.

### Delay analysis by base

| base | average delay |
|------|---------------|
| B01 | 19.06 minutes |
| B02 | 16.31 minutes |

B01 experienced slightly higher delays compared to B02.

### Delay analysis by lesson type

Circuit and Solo lessons showed the highest average delays at around 19.7 minutes.

General Handling lessons recorded the lowest delay values.

### Delay analysis by day

Friday showed the highest average delay among all weekdays at 22.13 minutes. Thursday also showed relatively high delays.

This may indicate increased operational load near the end of the training week.

---

# Conclusion

The analysis identified several operational areas that may require attention:

- Overall aircraft utilization is low
- Some aircraft have high defect frequency
- Maintenance downtime is impacting availability
- Instructor workload distribution is uneven
- Qualification mismatch records are high
- Delays are common across training operations

The current training operations appear functional, but improvements in scheduling, maintenance planning, and instructor allocation could help improve operational efficiency and dispatch reliability.
