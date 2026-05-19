# Explainable cadet risk score methodology

## Overview

This report describes the methodology used for building an explainable cadet risk score system. The goal was to identify cadets who may experience delays or difficulties in training progression using operational, academic, and financial indicators.

The final risk score was designed to be:

- simple to understand
- easy to explain
- transparent in decision making
- suitable for operational review meetings

Instead of using a machine learning model, a rule-based weighted scoring method was used to generate a risk value between 0 and 100.

---

# Approach used

A weighted scoring approach was selected because the task specifically required an explainable solution.

Complex machine learning models such as:

- Random Forest
- XGBoost
- Neural Networks
- Deep Learning models

were not used.

Reasons:

- They behave as black-box models
- Risk predictions become difficult to explain
- No historical labels were available for supervised learning
- Operational teams need clear reasons for individual risk values

A weighted score allows every feature contribution to be visible.

---

# Risk score calculation

The final score was calculated by combining multiple risk indicators.

Risk Score =

(Flight Risk × 25)

+ (Study Risk × 20)

+ (Quiz Risk × 15)

+ (Inactivity Risk × 10)

+ (Payment Risk × 15)

+ (Cancellation Risk × 10)

+ (Delay Risk × 5)

Total Weight:

100

---

# Risk category definition

The calculated score was converted into three categories:

| Risk Score | Risk Level |
|-------------|------------|
| 0–39 | Low |
| 40–69 | Medium |
| 70–100 | High |

---

# Feature selection and justification

## Flight progress (25)

Flight progress received the highest weight because it directly represents cadet advancement toward training completion.

Lower flight progress generally indicates:

- larger remaining flying hours
- slower completion status
- increased delay risk

Formula:

Flight Risk

= 1 − (Flight Progress /100)

---

## Study progress (20)

Study progress measures theoretical course completion and learning advancement.

Lower values may indicate:

- incomplete syllabus coverage
- weaker preparation
- possible examination delays

Formula:

Study Risk

= 1 − (Study Progress /100)

---

## Quiz score (15)

Quiz performance was included because chapter completion alone does not necessarily indicate understanding.

Lower quiz scores may indicate:

- weak conceptual understanding
- retention problems
- requirement for additional revision

Formula:

Quiz Risk

= 1 − (Quiz Score /100)

---

## Outstanding payment (15)

Payment risk was included because financial issues may affect training continuity.

Large outstanding amounts may create:

- scheduling interruptions
- delayed operational activities
- follow-up requirements

Formula:

Payment Risk

= Outstanding Amount / Maximum Outstanding Amount

---

## Study inactivity (10)

Long inactivity periods may indicate reduced learning engagement.

High inactivity may suggest:

- inconsistent study habits
- declining participation
- delayed preparation

Formula:

Inactivity Risk

= Inactive Days /90

---

## Frequent cancellations (10)

Repeated cancellations were included because disruptions may reduce training continuity.

Higher cancellation counts may result in:

- missed opportunities
- delayed progress

Formula:

Cancellation Risk

= Cancellation Count /5

---

## Average delay (5)

Average delay received the lowest weight because delays mainly affect efficiency rather than directly preventing completion.

Formula:

Delay Risk

= Average Delay /60

---

# Reason for weight selection

Weights were assigned according to expected operational impact.

| Feature | Weight |
|-----------|---------|
| Flight Progress | 25 |
| Study Progress | 20 |
| Quiz Score | 15 |
| Outstanding Payment | 15 |
| Study Inactivity | 10 |
| Frequent Cancellations | 10 |
| Average Delay | 5 |

The highest weight was assigned to flight progress because actual flying hours directly determine course completion.

Study and quiz indicators received moderate weight because academic performance contributes to readiness.

Operational factors such as delays and cancellations received lower values because they generally have indirect impact.

---

# Explainability of generated score

The generated score also stores specific reasons behind the risk level.

Examples:

| Cadet | Risk Score | Risk Level | Main Reasons |
|---------|------------|-------------|--------------|
| C001 | 38 | Medium | High payment risk, study inactivity |
| C002 | 78 | High | Low quiz score, payment risk, repeated disruption |
| C003 | 84 | High | Low flight progress, low study activity, payment risk |

This makes individual scores easier to interpret during operational review discussions.

---

# Observations from generated risk results

The generated scores showed that most cadets were distributed between low and medium risk categories.

Common factors observed in medium and high risk records included:

- lower flight progression
- payment-related risk
- inactivity in study activity
- weaker quiz performance

Flight progress and study engagement appeared to contribute most frequently to risk increases.

Payment-related factors also showed influence on overall training continuity.

---

# Limitations

Some limitations were identified in the current approach:

- Feature weights were manually assigned
- Historical outcome data was not available
- External factors such as weather and aircraft availability were not included
- Relationships between variables were assumed to be linear
- Threshold values may require future tuning

---

# Conclusion

An explainable weighted risk scoring framework was developed to identify cadets requiring additional attention.

The approach provides:

- transparent scoring
- direct feature contribution
- easier interpretation
- operational usefulness

The model can support future operational reviews and may also be improved using larger historical datasets and additional factors.
