# What Drives Health Insurance Costs?

Analysis of 1,338 insurance records to identify the biggest drivers of medical charges, using Python, SQL, and regression modeling.

## Key Findings
- **Smoking is the #1 cost driver.** Smokers pay \$32,050 on average vs. \$8,434 for non-smokers, about 3.8x more.
- **Smoking and obesity compound.** Smokers with a BMI of 30+ average \$41,558, nearly double smokers with a lower BMI (\$21,363) and about 5x non-smokers. This group is only 11% of members but the most expensive by far.
- **For non-smokers, BMI has little effect.** Non-smokers with a BMI of 30+ average \$8,843 vs. \$7,977 for those under 30, a difference of under \$900.
- **Costs rise steadily with age.** Average charges more than double, from \$9,182 for ages 18–29 to \$21,248 for ages 60+.
- **Region matters little.** Among non-smokers, average charges across regions differ by only about \$1,150.

## Model Results
| Model | R² | Avg Error |
|---|---|---|
| Baseline linear regression | 0.784 | \$4,181 |
| Improved (obese-smoker + age² features) | 0.876 | \$2,420 |

Adding two features based on patterns found during exploration raised R² from 0.78 to 0.88 and cut average prediction error by 42%.

**What the improved model shows:**
- Smoking adds about \$13,300 to annual charges, holding other factors constant.
- Smokers with a BMI of 30+ pay an additional \$19,800 on top of that, about \$33,100 more than a comparable non-smoker.
- Once this interaction is included, BMI alone has little effect (about \$50 per point), meaning obesity mainly increases costs in combination with smoking.
- Each child adds about \$600; sex and region have minor effects.

## Recommendations for an Insurer
1. Smoking cessation programs could offer the highest return, since smokers with high BMI are the most expensive group.
2. Pricing models should account for the smoking–BMI interaction rather than treating each factor separately.
3. Wellness programs targeting weight management may matter most for members who smoke.

## Tools
Python (pandas, seaborn, scikit-learn), SQL (SQLite), Jupyter Notebook

## Data
[Medical Cost Personal Datasets](https://www.kaggle.com/datasets/mirichoi0218/insurance) from Kaggle.
