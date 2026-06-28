# Hypothesis Test Notes

---

## 1. Null Hypothesis (H0)

The new campaign has no effect on paid conversion rate. The conversion rate is the same for both Control and Treatment groups.

---

## 2. Alternate Hypothesis (H1)

The new campaign increased the paid conversion rate. The Treatment group has a higher conversion rate than the Control group.

---

## 3. Test Type

**One-tailed test** — because we are only testing whether the Treatment group performs better than the Control group, not whether it is different in either direction.

---

## 4. Significance Level

**0.05 (5%)** — meaning we need to be 95% confident before concluding the campaign worked.

---

## 5. Metric Being Tested

**Paid Conversion Rate**
- Control group: 3.2%
- Treatment group: 7.0%

---

## 6. Reason for Choosing This Metric

Conversion to paid is chosen as the metric because it directly measures the core business goal of turning free users into paying customers. It is the most direct measure of whether the campaign is generating revenue for the business.

---

## 7. Interpretation Logic

| p-value result | Decision | Meaning |
|---|---|---|
| p-value < 0.05 | Reject H0 | Campaign DID improve conversion rate ✅ |
| p-value > 0.05 | Fail to reject H0 | Cannot conclude campaign worked ❌ |

**In our experiment:**
- p-value = 0.0011
- 0.0011 < 0.05 ✅
- Decision: **Reject H0**
- Conclusion: The new campaign significantly improved the paid conversion rate.

---

## Summary Table

| Element | Detail |
|---|---|
| Null Hypothesis (H0) | No difference in conversion rate between groups |
| Alternate Hypothesis (H1) | Treatment group has higher conversion rate |
| Test Type | One-tailed |
| Significance Level | 0.05 (95% confidence) |
| Metric Tested | Paid Conversion Rate |
| Control Rate | 3.2% |
| Treatment Rate | 7.0% |
| p-value | 0.0011 |
| Decision | Reject H0 |
| Conclusion | New campaign significantly improved conversion rate |
