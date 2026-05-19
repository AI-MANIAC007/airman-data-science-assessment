# AIRMAN Data Science Assessment

## Project Overview

This project focuses on analysing aviation training operations and cadet learning data from AIRMAN systems. The objective was to identify operational inefficiencies, training risks, study behavior patterns, finance-related concerns, and create an explainable cadet risk scoring system.

The project combines information from Skynet operational data and TOGA study data to generate insights that can support training continuity and improve decision making.

---

## Tools and Libraries Used

### Programming Language
- Python

### Libraries
- Pandas
- NumPy
- Matplotlib

### Environment
- Jupyter Notebook
- GitHub

---

## Project Structure

```text
AI-MANIAC007/

├── charts/
│   ├── aircraft_utilization.png
│   ├── cadet_progress.png
│   ├── cadet_risk_scores.png
│   ├── cancellation_reasons.png
│   ├── flight_vs_study_progress.png
│   ├── payment_risk.png
│   └── study_readiness.png
│
├── data/
│   ├── aircraft.csv
│   ├── cadets.csv
│   ├── instructors.csv
│   ├── payments.csv
│   ├── sorties.csv
│   ├── toga_study.csv
│   │
│   ├── cleaned_aircraft.csv
│   ├── cleaned_cadets.csv
│   ├── cleaned_instructors.csv
│   ├── cleaned_payments.csv
│   ├── cleaned_sorties.csv
│   ├── cleaned_toga_study.csv
│   │
│   ├── cleaned_outputs.csv
│   └── risk_scores.csv
│
├── notebooks/
│   └── analysis.ipynb
│
├── reports/
│   ├── data_quality_report.md
│   ├── executive_insights.md
│   ├── finance_risk_analysis.md
│   ├── methodology.md
│   ├── skynet_operations_analysis.md
│   ├── toga_study_intelligence.md
│   └── training_progress_analysis.md
│
├── README.md
└── LICENSE
```

---

## Setup Instructions

Clone the repository:

```bash
git clone <repository-url>
```

Install dependencies:

```bash
pip install pandas numpy matplotlib
```

---

## How to Run the Notebook

Open Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
notebooks/analysis.ipynb
```

Run cells sequentially from top to bottom.

---

## Data Assumptions

The following assumptions were made during analysis:

- Higher study inactivity indicates lower engagement
- Flight progress and study progress should generally move together
- High outstanding payments may affect training continuity
- Repeated cancellations can delay training progress
- Missing values were treated carefully based on context

---

## Metrics Calculated

### Operational Metrics

- Aircraft utilization percentage
- Instructor utilization
- Average delay
- Completion rate
- Cancellation rate

### Training Metrics

- Cadet progress percentage
- Remaining flight hours
- Average flying rate
- Completion risk

### TOGA Metrics

- Subject progress percentage
- Study readiness score
- Quiz performance
- Study inactivity

### Finance Metrics

- Outstanding amount
- Payment completion percentage
- Payment risk score

### Risk Metrics

- Explainable cadet risk score
- Risk level classification

---

## Risk Score Explanation

A weighted risk score was used instead of a machine learning model.

I intentionally avoided using complex ML models because:

- Dataset size is limited
- Multiple data quality issues were identified
- The task required explainability
- Leadership decisions should be easy to understand

The risk score considers:

- Flight progress
- Study progress
- Quiz score
- Study inactivity
- Outstanding payment
- Cancellation frequency
- Average delay

Risk levels:

```text
0–39   → Low
40–69  → Medium
70–100 → High
```

---

## Key Outputs

This project generated:

- Cleaned datasets
- Operational analysis reports
- Training progress insights
- TOGA learning intelligence reports
- Finance risk analysis
- Explainable cadet risk scores
- Visualization dashboard charts
- Executive recommendations

---

## Known Limitations

- Dataset size is relatively small
- Missing values and inconsistencies were present
- Weather details were limited
- Instructor experience data was unavailable
- Simulator performance information was unavailable
- Risk score weights are assumption-based and not learned from historical outcomes

---

## What I Would Improve With More Time

- Validate risk score with real historical FTO outcomes
- Include additional operational features
- Add interactive dashboards
- Introduce trend analysis over time
- Improve personalization recommendations in TOGA
- Build feedback-based weight adjustment

---

# AI Usage Disclosure

## 1. Did you use AI tools? If yes, where?

Yes.

AI tools were used as an assistance mechanism for code generation support, debugging, visualization suggestions, and report structuring. All calculations, assumptions, and outputs were manually reviewed and verified.

---

## 2. What prompts or tasks did AI help with?

AI helped with:

- Python syntax and debugging and faster coding due to time limitations
- Plot generation
- Markdown formatting
- Report wording improvements

The analysis direction and interpretations were decided manually.

---

## 3. Which parts did you personally verify?

I personally verified:

- Data cleaning logic
- Risk score calculations
- Assumptions used
- Generated insights
- Charts and outputs
- Final report content

---

## 4. Which AI suggestion did you reject or modify?

Some AI-generated suggestions initially recommended more complex ML approaches and generic insights.

I modified or rejected several suggestions based on the problem requirements:

- I avoided using complex ML models because the task required explainability and the available data contained inconsistencies.

- During data cleaning, the initial delay calculation only considered differences in actual start time and scheduled start time. I modified this logic to also handle cases where the start time remained unchanged but delay occurred because of later actual end times.

- For visualization, I added a reference line in the flight progress vs study progress scatter plot to make comparison easier and improve interpretation.

- Report content and insights were modified manually to align with the actual outputs and problem statement instead of using generic observations.

- I reviewed formulas and adjusted calculations such as study readiness score so that the score remained within meaningful limits.

I made these changes to keep the analysis explainable, realistic, and aligned with the assessment objective.

---

## 5. Which part of the analysis are you least confident about?

The risk score weights are based on assumptions and domain reasoning rather than historical FTO validation data.

These weights would require adjustment using real-world training outcomes.

---

## 6. Pick one formula or chart and explain it in your own words

Study Readiness Score:

This score combines study completion, quiz performance, and practice activity.

The idea is that completing chapters alone does not indicate readiness. A cadet should also understand the concepts and practice regularly. Therefore all three factors were included together rather than relying on only one measure.
