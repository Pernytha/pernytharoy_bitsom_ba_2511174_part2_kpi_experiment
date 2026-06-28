# Project: Onboarding & Activation Campaign Experiment

## 1. Business Problem Statement
* **Decision to be made:** Whether to roll out the new onboarding and activation campaign to the entire user base.
* **Impact:** Affects all new users signing up for our subscription-based digital product.
* **Metric to improve:** Paid conversion rate.
* **Risks to monitor:** Increased support ticket volume, refund requests, and potential operational friction.
* **Evidence required:** Statistical significance ($p < 0.05$) in conversion lift and stability in guardrail metrics before full-scale launch.

## 2. North Star Metric (NSM)
* **Selected Metric:** **Paid conversion rate**
* **Justification:** This is the ultimate indicator of whether our onboarding effectively delivers product value. Other metrics (like landing page visits or trial starts) are supporting drivers, but they do not guarantee revenue.
* **Business Growth Connection:** Increasing this rate directly drives recurring revenue and shortens the time required to recover Customer Acquisition Costs (CAC).
* **Risks of Blind Optimization:** If optimized without regard for guardrails, we risk "dark patterns" that increase churn, generate refund requests, or overwhelm our support teams.

## 3. KPI Tree Summary
![KPI Tree](outputs/kpi_tree.png)
The KPI tree breaks down the North Star metric into actionable drivers:
* **Primary Drivers:** Landing page visit rate, Trial start rate, Onboarding completion rate.
* **Guardrails:** Support ticket rate, Refund rate, Average engagement score.

## 4. Experiment Analysis Approach
* **Data Cleaning:** 
    * Identified and removed 8 duplicate `user_id` records.
    * Validated all binary fields (0/1) for conversion events.
    * Retained revenue outliers as they represent genuine high-value users.
* **Missing Values:** No missing values identified in critical columns.
* **Statistical Method:** Conducted a two-sample $t$-test (assuming unequal variances) to compare conversion proportions between 690 Control and 710 Treatment users.

## 5. Hypothesis Test Summary
* **Null Hypothesis ($H_0$):** $p_{\text{Treatment}} - p_{\text{Control}} \le 0$
* **Alternate Hypothesis ($H_1$):** $p_{\text{Treatment}} - p_{\text{Control}} > 0$
* **Significance Level:** $\alpha = 0.05$
* **Findings:** The test yielded a **$p$-value of 0.0005**, providing strong statistical evidence to reject the null hypothesis.

## 6. Guardrail Metrics Considered
1. **Support ticket rate:** Increased from 22.03 (Control) to 37.32 (Treatment). This represents a **significant risk** of increased operational costs.
2. **Refund rate:** Observed a slight increase from 0% to 0.42%.
3. **Average engagement score:** Increased from 56.53 to 62.23, indicating positive behavioral impact.

## 7. Final Recommendation
**Recommendation: Phased Rollout.**
While the Treatment group shows a statistically significant improvement in conversion ($p=0.0005$), the 70% increase in support tickets is a major guardrail concern. We recommend a phased, segment-specific launch to refine the onboarding flow and investigate the root cause of the support ticket volume before a company-wide release.

## 8. Assumptions and Limitations
* **Assumption:** The support ticket spike is driven by user learning curves in the new flow rather than critical product bugs.
* **Limitation:** This experiment analyzes 30-day performance; long-term churn (beyond 30 days) is not yet captured.

## 9. Screenshots
* `summary_metrics.png`: Overview of conversion performance.
* `hypothesis_test_output.png`: Statistical significance evidence ($p$-value).
* `kpi_tree_preview.png`: Breakdown of the KPI hierarchy.