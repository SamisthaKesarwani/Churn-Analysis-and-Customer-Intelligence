# 📉 Churn Analysis and Customer Intelligence

A project where I looked at why subscription customers cancel. I used Python (pandas, Matplotlib, Seaborn) and SQL (SQLite) on a sample dataset of 21 customers across three tables: customer details, subscriptions and support complaints. The main finding is that referred customers and customers who complained were far more likely to leave.

## 📁 What's in this repo

| File | What it is |
|---|---|
| 📓 [`Churn_analysis.ipynb`](Churn_analysis.ipynb) | The full notebook: cleaning, analysis, charts, SQL |
| 📊 [`customer_churn_data_raw.xlsx`](customer_churn_data_raw.xlsx) | Raw data (3 sheets: customer, subscription, support) |
| 🗄️ [`customer_churn.db`](customer_churn.db) | SQLite database built from the Excel file |
| 🧾 [`exported_churn_data.csv`](exported_churn_data.csv) | Cleaned and merged data (21 rows, 25 columns) |

## 🛠️ What I did

1. **Cleaned the data:** renamed and dropped columns, converted dates, made gender values consistent, and filled missing countries using the state.
2. **Merged three tables.** The support table had customers with more than one complaint, which made the merge produce 23 rows instead of 21. I counted complaints per customer first, then removed the duplicates before joining.
3. **Created new columns:** churn flag, tenure in days, churn risk (low / med / high), age and age group.
4. **Calculated KPIs:** churn rate, ARPU, escalation rate, average complaints per customer and monthly revenue lost to churn.
5. **Made charts and pivot tables** with Matplotlib and Seaborn.
6. **Repeated key questions in SQL** to check my numbers.

## 🔍 What I found

- 📌 **Overall churn is 28.57%** (6 of 21 customers).
- 🤝 **Referred customers churned the most:** 5 of 6 referral customers left, compared with 1 of 6 paid customers and 0 of 9 organic customers.
- 📦 **Basic plan churn is 60% (3 of 5).** But all 3 of those were referral customers, and both organic Basic customers stayed. So the channel may matter more than the plan. Referral customers were only on Basic and Standard plans, so I can't fully separate the two.
- 📞 **Complaints:** all 6 customers who churned had filed a support complaint, and none of the 14 who never complained left. The data doesn't show whether the complaint came before the decision to leave.
- 🧩 **Cancellation reasons were all different** (price, not enough content, streaming quality, a competitor, a forgotten trial), so there isn't one single cause.
- 🎂 **Age:** the 35-44 group had the highest churn (3 of 7), but the groups are tiny.

## 💡 What I'd suggest to the business

- Find out whether referred customers join through trials or discounts, and whether they stay active once the offer ends.
- Give Basic-plan customers better onboarding, for example by showing them content early.
- Treat a support complaint as a trigger for a follow-up call.
- Track referral customers separately from other customers.

## ⚠️ Limitations

- The dataset has only 21 customers, so these are patterns worth investigating, not proven conclusions. For example, the 0.77 correlation between escalations and churn comes from 21 rows.
- Charts split by state aren't reliable, because each state has only 1 to 4 customers.
- The data doesn't say what currency the charges are in, so I haven't assumed one.

## ▶️ How to run it

1. Download all the files into one folder.
2. Install the libraries: `pip install pandas numpy matplotlib seaborn openpyxl`
3. Open `Churn_analysis.ipynb` in Jupyter or Google Colab and run the cells from the top.

## 🧰 Tools

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) ![pandas](https://img.shields.io/badge/pandas-150458?logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white) ![SQLite](https://img.shields.io/badge/SQLite-003B57?logo=sqlite&logoColor=white) ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)

## 👩‍💻 About me

Made by **Samistha Kesarwani**

🔗 GitHub: [github.com/SamisthaKesarwani](https://github.com/SamisthaKesarwani)
