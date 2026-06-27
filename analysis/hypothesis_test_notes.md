# Hypothesis Test Notes

## Metric Being Tested
Paid conversion rate.

Formula:

`converted_to_paid users / total users`

## Reason for Choosing This Metric
Paid conversion rate is the primary business outcome because the campaign's objective is to improve user activation and conversion into paying customers.

## Null Hypothesis
H0: Treatment paid conversion rate is less than or equal to Control paid conversion rate.

## Alternate Hypothesis
H1: Treatment paid conversion rate is greater than Control paid conversion rate.

## Test Type
One-tailed two-proportion z-test.

This is one-tailed because the business question is whether the treatment improves conversion, not just whether it is different.

## Significance Level
α = 0.05

## Test Inputs
Control users: 690  
Control paid conversions: 22  
Control conversion rate: 3.19%

Treatment users: 710  
Treatment paid conversions: 50  
Treatment conversion rate: 7.04%

## Test Output
Absolute lift: 3.85%  
Relative lift: 120.87%  
Z-statistic: 3.2640  
P-value: 0.000549

## Decision Rule
If p-value < 0.05, reject the null hypothesis.

## Result
The p-value is 0.000549, which is less than 0.05. Therefore, reject the null hypothesis.

## Business Interpretation
The treatment group shows a statistically significant improvement in paid conversion rate compared with the control group. The treatment can be launched, but guardrail metrics such as support ticket rate and refund rate should be monitored.
