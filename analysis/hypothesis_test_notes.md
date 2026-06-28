# Hypothesis Test Notes

## Hypothesis

* **Null Hypothesis ($H_0$):** There is no difference in the conversion rate between the Control and Treatment groups ($p_{\text{Treatment}} - p_{\text{Control}} \le 0$).
* **Alternate Hypothesis ($H_1$):** The Treatment group has a higher conversion rate than the Control group ($p_{\text{Treatment}} - p_{\text{Control}} > 0$).
* **Test Type:** One-tailed test (as we are specifically testing for an improvement).
* **Significance Level ($\alpha$):** 0.05
* **Metric Tested:** Paid Conversion Rate.
* **Reason for Metric:** This is our North Star metric; it directly reflects the business goal of increasing recurring revenue from new user trials.
* **Interpretation Logic:** If the $p$-value is less than 0.05, we reject the null hypothesis, indicating that the observed conversion lift is statistically significant and likely due to the campaign rather than random chance. This supports a decision to roll out the campaign.

## Hypothesis Test Analysis

### Summary of Test Inputs
* **Control Group:** 690 users
* **Treatment Group:** 710 users
* **Test Method:** Two-sample $t$-test (assuming unequal variances) for proportions.

### Test Output
* **P-value:** 0.0005
* **Decision Rule:** Since $p < 0.05$, we reject the null hypothesis.

### Business Interpretation
The experiment resulted in a **3.85% lift** in conversion, and with a $p$-value of 0.0005, the result is highly statistically significant. This provides strong evidence that the new onboarding campaign is effective at driving higher conversion rates. However, this decision must be weighed against the guardrail metrics (support tickets) documented in the `recommendation_memo.md` before final approval.


### Evidence
**`screenshots/hypothesis_test_output.png`**.