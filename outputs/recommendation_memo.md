# Recommendation Memo


## 1. Executive Summary

The company tested a new onboarding and activation campaign against the existing experience. The new campaign showed a strong improvement in paid conversion rate, more than doubling it from 3.2% to 7.0%. However, three guardrail metrics raised serious concerns — support tickets increased by 70%, revenue per converter dropped by 53%, and refund requests appeared for the first time.

**Recommendation: Do not launch to all users yet.** The issues with support tickets and revenue quality must be investigated and fixed before a full launch decision is made.

---

## 2. North Star Metric

The North Star Metric for this experiment is **Paid Conversion Rate** — the percentage of users who convert from free signups to paying customers.

This metric was chosen because it directly measures the core business goal of generating revenue from new users. A subscription business only survives when users convert to paid, making this the single most important measure of campaign success.

| Group | Conversion Rate |
|---|---|
| Control | 3.2% |
| Treatment | 7.0% |
| Improvement | +120% ✅ |

---

## 3. KPI Tree Explanation

The North Star Metric (Conversion to Paid) is driven by three primary KPIs:

**1. User Acquisition** -Are enough people signing up and visiting the product?
- Sub-drivers: Landing page visit rate, Trial start rate

**2. Onboarding Effectiveness** - Are users completing the setup process?
- Sub-drivers: Onboarding completion rate, Days to convert

**3. Product Engagement** - Are users finding value in the product?
- Sub-drivers: Engagement score, Revenue per customer

**Guardrail Metrics** (warning signs monitored separately):
- Support ticket rate
- Refund rate
- Revenue per converter

---

## 4. Experiment Result Summary

| Metric | Control | Treatment | Change |
|---|---|---|---|
| User Count | 693 | 715 | - |
| Landing Page Visit Rate | 63.6% | 72.6% | +14.1% ✅ |
| Trial Start Rate | 25.1% | 29.1% | +15.9% ✅ |
| Onboarding Completion Rate | 15.6% | 21.3% | +36.4% ✅ |
| Paid Conversion Rate | 3.2% | 7.0% | +120.3% ✅ |
| Average Revenue Per User | $51.75 | $53.88 | +4.1% ✅ |
| Average Revenue Per Converter | $1,630 | $770 | -53% ❌ |
| Refund Rate | 0.0% | 0.4% | New issue ❌ |
| Support Ticket Rate | 0.22 | 0.37 | +70% ❌ |
| Engagement Score | 57.0 | 62.9 | +10.3% ✅ |
| Average Days to Convert | 8.9 | 6.4 | -28% ✅ |

The new campaign performed strongly on primary metrics but raised concerns on guardrail metrics.

---

## 5. Hypothesis Test Interpretation

A t-Test (Two-Sample Assuming Unequal Variances) was performed on the paid conversion rate.

| Element | Detail |
|---|---|
| Null Hypothesis (H0) | No difference in conversion rate between groups |
| Alternate Hypothesis (H1) | Treatment group has higher conversion rate |
| Test Type | One-tailed t-Test |
| Significance Level | 0.05 (95% confidence) |
| p-value | 0.0005 |
| Decision | Reject H0 ✅ |

**Interpretation:** The p-value of 0.0005 is much lower than the significance level of 0.05. This means we reject the Null Hypothesis and conclude that the new campaign genuinely and significantly improved the paid conversion rate. We are 99.9% confident this is a real improvement and not due to random chance.

---

## 6. Guardrail Analysis

While the conversion improvement is real, three guardrail metrics raised serious concerns:

### Support Ticket Rate - 🔴 High Risk
- Control: 0.22 | Treatment: 0.37 | Change: +70%
- More users in the Treatment group are complaining or asking for help
- This suggests the new experience may be confusing users after signup
- Higher support costs reduce the profitability of each new customer

### Refund Rate - 🟡 Medium Risk
- Control: 0.0% | Treatment: 0.4% | Change: Refunds appeared
- Nobody asked for refunds in the old experience
- Some users in the new experience paid and then wanted their money back
- This suggests the campaign may be attracting users who are not genuinely interested

### Revenue Per Converter - 🔴 High Risk
- Control: $1,630 | Treatment: $770 | Change: -53%
- Even though more people are converting, each person is paying much less
- The campaign is converting more free plan users instead of premium users
- The financial benefit of higher conversion may be offset by lower revenue per customer

---

## 7. Segment Level Insight

### By Region
| Region | Control | Treatment |
|---|---|---|
| East | 2.53% | 6.40% |
| North | 3.45% | 8.89% |
| South | 3.26% | 7.61% |
| West | 3.38% | 5.03% |

North region showed the strongest improvement. West region showed the weakest improvement.

### By Device
| Device | Control | Treatment |
|---|---|---|
| Desktop | 4.50% | 6.54% |
| Mobile | 2.57% | 7.34% |
| Tablet | 1.79% | 7.14% |

Mobile and Tablet users showed the biggest improvements suggesting the new campaign works particularly well on mobile devices.

### By Traffic Source
| Source | Control | Treatment |
|---|---|---|
| Email | 2.70% | 7.14% |
| Organic | 2.03% | 6.22% |
| Paid Search | 1.28% | 6.25% |
| Referral | 2.47% | 10.99% |
| Social | 7.69% | 6.02% |

Referral traffic showed the strongest improvement (+10.99%). Social traffic actually performed worse in Treatment than Control.

### By Plan Type
| Plan | Control | Treatment |
|---|---|---|
| Basic | 3.59% | 3.83% |
| Free | 3.05% | 9.24% |
| Premium | 2.75% | 6.25% |

Free plan users showed the biggest jump which explains the drop in revenue per converter — more lower value users are converting.

---

## 8. Final Recommendation

**Recommendation: Do Not Launch Yet, Fix Issues First**

The new campaign shows genuine and statistically significant improvement in conversion rate. However a full launch is not recommended at this time for the following reasons:

**Issue 1: Fix the support ticket problem:**
The 70% increase in support tickets suggests users are confused by the new experience. The company must identify what is causing confusion and fix it before launching to all users. Otherwise the cost of handling complaints will reduce the financial benefit of higher conversions.

**Issue 2: Investigate the revenue drop:**
The drop in revenue per converter from $1,630 to $770 is a serious concern. The company must investigate why more free plan users are converting instead of premium users. The campaign should be adjusted to attract higher value customers before a full launch.

Once these two issues are resolved, the campaign should be reconsidered for launch — particularly targeting:
- **Mobile and Tablet users** where improvement was strongest
- **Referral traffic** where conversion jumped to 10.99%
- **North region** where improvement was highest

---

## 9. Risks and Limitations

| Risk | Description |
|---|---|
| Revenue risk | Higher conversion but lower revenue per customer may mean total revenue does not grow |
| Support cost risk | 70% more support tickets increases operational costs |
| Refund risk | Refunds appearing for the first time could grow after full launch |
| Sample size | The experiment ran on 1,408 users — a larger sample may give more reliable results |
| Short term data | Only 30 days of revenue data — long term impact is unknown |
| Social traffic decline | Social users performed worse in Treatment — needs investigation |

---

## 10. Next Steps

1. **Investigate support tickets**: Find out what is confusing users in the new experience and fix it
2. **Investigate revenue drop**: Understand why free plan users are converting more than premium users and adjust the campaign
3. **Fix refund issue**: Identify why users are asking for refunds and address the root cause
4. **Run a follow up experiment**: After fixes are made, run a new experiment with a larger sample size and longer duration
5. **Consider partial launch**: Launch the new experience only to Mobile users and Referral traffic where results were strongest
6. **Monitor long term metrics**: Track revenue and retention beyond 30 days to understand the true business impact

---

## Summary

| Element | Detail |
|---|---|
| North Star Metric | Paid Conversion Rate |
| Conversion Improvement | 3.2% → 7.0% (+120%) ✅ |
| Statistical Significance | p-value 0.0005 ✅ |
| Guardrail Concerns | Support tickets +70%, Revenue -53%, Refunds appeared ❌ |
| Final Decision | Do Not Launch Yet |
| Reason | Fix support and revenue issues first |
| Next Step | Investigate issues, fix campaign, re-test |

