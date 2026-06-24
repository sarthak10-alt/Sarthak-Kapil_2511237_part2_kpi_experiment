# Sarthak-Kapil_2511237_part2_kpi_experiment
# Campaign Experiment Analysis

## 1. Business Context
A subscription-based digital product company tested a new onboarding and activation campaign. Users were split into:
- Control group: existing onboarding experience
- Treatment group: new campaign experience

The decision is whether the treatment should be launched to all users.

## 2. Dataset Description
The dataset contains user-level experiment records with group assignment, segment attributes, funnel actions, revenue, support, refund, conversion timing, and engagement score.

Raw records: 1408
Records used after removing exact duplicates: 1400

## 3. North Star Metric Selected
**Paid conversion rate** was selected as the North Star metric.

Formula:

`converted_to_paid users / total users`

This metric directly measures whether the onboarding campaign helps users become paying customers.

## 4. KPI Tree Summary
The KPI tree breaks paid conversion rate into:
- Activation quality: landing page visit rate, trial start rate, onboarding completion rate
- Revenue quality: average revenue per user, converted-user revenue, paid conversions
- Guardrail metrics: refund rate, support ticket rate, days to convert, engagement score

KPI tree file:

`outputs/kpi_tree.png`

## 5. Experiment Analysis Approach
The analysis compared Control and Treatment across:
- User count
- Landing page visit rate
- Trial start rate
- Onboarding completion rate
- Paid conversion rate
- Revenue metrics
- Refund rate
- Support ticket rate
- Engagement score
- Days to convert

Segment analysis was completed for:
- Region
- Device type
- Traffic source
- Plan type

## 6. Hypothesis Test Summary
Primary metric tested: **Paid conversion rate**

Null hypothesis: Treatment conversion rate is less than or equal to Control conversion rate.  
Alternative hypothesis: Treatment conversion rate is greater than Control conversion rate.

Test used: One-tailed two-proportion z-test  
Significance level: 0.05

Control conversion rate: 3.19%  
Treatment conversion rate: 7.04%  
Absolute lift: 3.85%  
Z-statistic: 3.2640  
P-value: 0.000549

Since the p-value is below 0.05, the null hypothesis is rejected.

## 7. Guardrail Metrics Considered
The treatment improved engagement and reduced days to convert. However, support ticket rate increased and refund requests appeared in the treatment group. These are risks that should be monitored after launch.

## 8. Final Recommendation
**Launch the treatment experience with monitoring.**

Reason:
- Paid conversion rate improved from 3.19% to 7.04%.
- The improvement is statistically significant.
- Engagement improved.
- Average days to convert decreased.

Caution:
- Monitor support ticket rate.
- Monitor refund rate.
- Review Social and Unknown traffic segments before aggressively scaling those channels.

## 9. Assumptions and Limitations
- Exact duplicate rows were removed before analysis.
- Missing device type and traffic source were categorized as Unknown for segment-level reporting.
- Missing engagement scores were excluded from engagement average calculations.
- Revenue outliers were kept because high revenue values may be valid for converted users.
- The analysis assumes users were randomly assigned to Control and Treatment.

## 10. Screenshots Included
Required screenshots are included in the `screenshots/` folder:
- `summary_metrics.png`
- `hypothesis_test_output.png`
- `kpi_tree_preview.png`
