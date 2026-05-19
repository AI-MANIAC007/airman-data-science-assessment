# Executive Insights Report

## Overview

This report summarizes the key findings obtained from operational data, cadet training progress, TOGA learning activity, finance risk analysis, and risk score modeling. The objective was to identify operational gaps, understand cadet performance patterns, and suggest improvements for both Skynet and TOGA systems.

---

# 1. Top 5 Operational Insights

### 1. Low aircraft utilization was observed across the fleet

Aircraft utilization remained low across all aircraft, with no aircraft crossing 15% utilization. The highest utilization was observed for aircraft A008 at approximately 12.8%.

### 2. Aircraft A004 and A008 may require operational review

Aircraft A004 and A008 showed defect counts above 10 while also operating at relatively low utilization levels. High defect frequency may be affecting operational availability.

### 3. Instructor availability created more cancellations than weather

Instructor availability issues contributed to 6 cancellations, while weather contributed to 4 cancellations. This suggests scheduling and resource allocation may currently have greater impact than environmental conditions.

### 4. Circuit and Solo sessions experienced comparatively higher delays

Circuit and Solo lesson types showed average delays close to 20 minutes. These lesson categories may require schedule optimization.

### 5. Base B01 showed slightly lower operational performance

Average utilization:

- B01 → 6.94%
- B02 → 8.01%

B01 also showed slightly higher delay values.

---

# 2. Top 5 Training Progress Insights

### 1. Training progress varied considerably across cadets

Cadet progress ranged from nearly 8% to approximately 89%. This indicates that cadets are currently distributed across very different training stages.

### 2. Multiple cadets still require large flight-hour completion

Examples include:

- C005 → 183.9 hours remaining
- C036 → 177.9 hours remaining
- C004 → 167 hours remaining

These cadets may need additional monitoring.

### 3. Flight progress and study progress were not always balanced

Some cadets showed strong flight progress but weaker study performance.

Example:

- C045:
    - Flight progress ≈ 86.9%
    - Study progress ≈ 14.8%

This may affect long-term training consistency.

### 4. Medium-risk cadets formed the largest group

Most identified risk cases belonged to the Medium category rather than High category. Early intervention may prevent future escalation.

### 5. Instructor workload distribution was uneven

Instructor I013 handled the highest number of sorties while several instructors handled comparatively fewer sessions.

This may indicate resource imbalance.

---

# 3. Top 3 TOGA Personalization Opportunities

### 1. Subject-specific revision recommendations

Navigation and Technical General repeatedly appeared among weaker subject areas. Personalized revision plans can help cadets focus on problem areas.

### 2. Study inactivity reminders

Several cadets showed inactivity periods greater than 30 days. Reminder systems may help improve consistency.

### 3. Theory support based on flight progress

Some cadets showed strong practical progress but weaker theory performance. TOGA can provide targeted learning support in such cases.

---

# 4. Top 3 Finance Risks

### 1. High outstanding amounts may affect training continuity

Several cadets showed larger pending balances together with medium or high training risk levels.

### 2. Delayed payments may create operational impact

Long payment gaps could influence training continuation and scheduling.

### 3. Revenue leakage indicators were observed

High outstanding balances together with delayed payments indicate possible collection risk.

---

# 5. Product Recommendations for Skynet

### Recommendation 1

Add instructor workload balancing to distribute sessions more evenly.

### Recommendation 2

Introduce maintenance risk alerts for aircraft with repeated defect patterns.

### Recommendation 3

Create operational delay monitoring for lesson types showing frequent delays.

---

# 6. Product Recommendations for TOGA

### Recommendation 1

Provide personalized weak-subject revision suggestions.

### Recommendation 2

Introduce study inactivity notifications.

### Recommendation 3

Add adaptive practice recommendations based on cadet performance.

---

# 7. Data Quality Issues Found

The following issues were identified during data cleaning and validation:

- Missing actual start and end times
- Missing cancellation reasons
- Delay mismatch records
- Cancelled sorties with recorded flight activity
- Invalid flight time sequences
- Missing study activity records
- Payment calculation inconsistencies
- Duplicate record checks

---

# 8. Suggested Additional Fields AIRMAN Should Collect

The current data can be improved by collecting:

- Weather severity information
- Instructor experience level
- Aircraft maintenance history
- Cadet attendance percentage
- Cadet feedback score

These additional fields may improve future analysis quality.

---

# 9. Final Recommendation to AIRMAN Leadership

Current findings suggest that operational, academic, and financial information should not be analyzed independently.

AIRMAN should prioritize a unified intelligence layer combining operational, academic, and financial indicators to proactively identify cadets at risk and improve training continuity across Skynet and TOGA.
