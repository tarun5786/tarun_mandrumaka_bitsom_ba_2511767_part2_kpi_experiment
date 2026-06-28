# README
## Subscription Campaign Experiment Analysis

---

## 1. Business Context

This analysis was conducted for a subscription-based digital product company. The company launched a new onboarding and activation campaign with the goal of improving user conversion and early engagement.

Users were divided into two groups:
- **Control group:** Existing onboarding experience (693 users)
- **Treatment group:** New campaign experience (715 users)

The business question was: **Should the new onboarding campaign be launched to all users?**

---

## 2. Dataset Description

| Detail | Value |
|---|---|
| File | campaign_experiment_data.xlsx |
| Total Users | 1,408 |
| Control Group | 693 users |
| Treatment Group | 715 users |
| Time Period | 30 days |

**Columns in the dataset:**

| Column | Description |
|---|---|
| user_id | Unique identifier for each user |
| signup_date | Date the user signed up |
| experiment_group | Control or Treatment |
| region | North, South, East, West |
| device_type | Mobile, Desktop, Tablet |
| traffic_source | Organic, Paid Search, Social, Email, Referral |
| plan_type | Free, Basic, Premium |
| visited_landing_page | 1 if visited, 0 if not |
| started_trial | 1 if started trial, 0 if not |
| completed_onboarding | 1 if completed, 0 if not |
| converted_to_paid | 1 if converted, 0 if not |
| revenue_30d | Revenue generated in 30 days |
| support_tickets_30d | Number of support tickets raised |
| refund_requested | 1 if refund requested, 0 if not |
| days_to_convert | Days taken to convert to paid |
| engagement_score | User engagement score out of 100 |

---

## 3. Data Cleaning Report

### Check 1: Missing Values

**What we checked:** Are there any empty cells in the data?

**What we found:**
- Device type: 18 missing values
- Traffic source: 24 missing values
- Engagement score: 14 missing values
- Days to convert: 1,336 missing values

**What we did:**
- The 1,336 missing values in "days to convert" are normal and expected — only users who actually paid have a conversion date. Everyone else will naturally be empty.
- The other missing values (device type, traffic source, engagement score) are small in number and were kept in the data but noted as missing.

---

### Check 2: Group Counts

**What we checked:** How many users are in each group?

**What we found:**
- Control group: 693 users
- Treatment group: 715 users

**What we did:** The groups are roughly equal in size so no action was needed. The experiment is balanced.

---

### Check 3: Duplicate User IDs

**What we checked:** Is the same user counted more than once?

**What we found:** 8 users appeared twice in the data.

**What we did:** Duplicate rows were removed so each user is only counted once. This ensures the analysis is accurate.

---

### Check 4: Invalid Binary Values

**What we checked:** Columns like "converted to paid" and "refund requested" should only contain 0 or 1. Are there any wrong values?

**What we found:** All binary columns were clean — only 0s and 1s found.

**What we did:** No action needed.

---

### Check 5: Outliers in Revenue

**What we checked:** Are there any unusually high or strange revenue values?

**What we found:**
- Most users paid around $1,033 on average
- Two users paid significantly more than others:
  - USR-100106 paid $8,610
  - USR-100303 paid $6,788

**What we did:** These values are unusual but not impossible for a subscription product. They were kept in the data but flagged as outliers to be aware of during analysis.

---

### Check 6: Segment Distribution

**What we checked:** Are the two groups similar in terms of region, device type, plan type and traffic source?

**What we found:** Both groups are well balanced across all segments:
- Region: similar spread across North, South, East and West
- Device type: similar split across Mobile, Desktop and Tablet
- Plan type: similar spread across Free, Basic and Premium
- Traffic source: similar spread across Organic, Paid Search, Social, Email and Referral

**What we did:** No action needed. The experiment groups are fairly distributed.

**Overall Conclusion:** The data is mostly clean and ready for analysis. The main issues found were 8 duplicate user IDs which were removed, and some missing values in device type, traffic source and engagement score which were noted. Two revenue outliers were flagged but kept in the data.

---

## 4. North Star Metric Selected

**North Star Metric: Paid Conversion Rate**

This metric was selected because it directly measures the core business goal of turning free users into paying customers. A subscription business only generates revenue when users convert to paid, making this the single most important measure of campaign success.

| Group | Conversion Rate |
|---|---|
| Control | 3.2% |
| Treatment | 7.0% |
| Improvement | +120.3% ✅ |

---

## 5. KPI Tree Summary

```
                    Conversion to Paid (North Star)
                   /              |               \
          User Acquisition   Onboarding       Product Engagement
                             Effectiveness
          /        \           /      \          /         \
   Landing      Trial    Onboarding  Days to  Engagement  Revenue per
   Page Visit   Start    Completion  Convert   Score       Customer
   Rate         Rate     Rate

GUARDRAIL METRICS (monitored separately):
⚠ Support Ticket Rate  ⚠ Refund Rate  ⚠ Revenue per Converter
```

The KPI tree shows how all metrics connect to the North Star Metric. Primary drivers are User Acquisition, Onboarding Effectiveness and Product Engagement. Guardrail metrics are monitored separately as warning signs.

---

## 6. Experiment Analysis Approach

The following steps were taken to analyze the experiment:

1. **Data Cleaning** - Checked for missing values, duplicates, invalid binary values, outliers and segment distribution
2. **Experiment Summary** - Calculated all key metrics for Control vs Treatment groups
3. **Segment Analysis** - Broke down conversion rate by Region, Device Type, Traffic Source and Plan Type
4. **Hypothesis Testing** - Ran a t-Test to check if the conversion improvement was statistically significant
5. **Guardrail Evaluation** - Evaluated support tickets, refund rate and revenue per converter
6. **Recommendation** - Made a final business recommendation based on all findings

---

## 7. Hypothesis Test Summary

| Element | Detail |
|---|---|
| Null Hypothesis (H0) | No difference in conversion rate between groups |
| Alternate Hypothesis (H1) | Treatment group has higher conversion rate |
| Test Type | One-tailed t-Test: Two-Sample Assuming Unequal Variances |
| Significance Level | 0.05 (95% confidence) |
| t-Statistic | -3.28 |
| Degrees of Freedom | 1,269 |
| p-value | 0.0005 |
| Decision | Reject H0 ✅ |
| Conclusion | The new campaign significantly improved conversion rate |

The p-value of 0.0005 is much lower than the significance level of 0.05. This means we are 99.9% confident the improvement is real and not due to random chance.

---

## 8. Guardrail Metrics Considered

| Guardrail Metric | Control | Treatment | Change | Risk Level |
|---|---|---|---|---|
| Support Ticket Rate | 0.22 | 0.37 | +70% | 🔴 High Risk |
| Refund Rate | 0.0% | 0.4% | New issue | 🟡 Medium Risk |
| Revenue Per Converter | $1,630 | $770 | -53% | 🔴 High Risk |

**Key findings:**
- Support tickets increased significantly suggesting users are confused by the new experience
- Refund requests appeared for the first time indicating some users felt misled
- Revenue per converter dropped by half because more free plan users are converting instead of premium users

---

## 9. Final Recommendation

**Decision: Do Not Launch Yet — Fix Issues First**

While the conversion rate improvement is real and statistically significant, a full launch is not recommended because:

1. **Support tickets increased by 70%** Users are confused by the new experience and the company needs to fix this before launching to everyone
2. **Revenue per converter dropped by 53%** The campaign is attracting more free plan users instead of premium users. This needs to be investigated and the campaign adjusted to attract higher value customers
3. **Refunds appeared** Some users are asking for their money back which needs to be addressed

**After fixing these issues, consider a partial launch to:**
- Mobile and Tablet users (strongest improvement)
- Referral traffic users (conversion jumped to 10.99%)
- North region users (highest regional improvement)

---

## 10. Assumptions and Limitations

| Assumption / Limitation | Description |
|---|---|
| 30 day window only | Revenue and engagement data covers only 30 days — long term impact is unknown |
| Sample size | 1,408 users may not fully represent the entire user base |
| Outliers kept | Two high revenue outliers were kept in the data which may affect averages |
| Missing values | Small number of missing values in device type, traffic source and engagement score |
| Causation vs correlation | The experiment shows correlation between the new campaign and conversion improvement but other factors may also have contributed |
| Short experiment duration | A longer experiment may give more reliable results |

---

## 11. Screenshots Included

| Screenshot | Description | Location |
|---|---|---|
| hypothesis_test_output.png | t-Test results from Excel showing p-value and test statistics | screenshots/ |

---

