# 📊 Customer Churn Analysis Dashboard

An end-to-end interactive Power BI dashboard analyzing customer churn using the **IBM Telco Customer Churn dataset** (7,043 customers). This project explores *who* is leaving, *why* they leave, and *where* the business should focus its retention efforts — going beyond descriptive charts into actionable business recommendations.

---

## 🖼️ Dashboard Preview

| Overview | Churn Analysis |
|---|---|
| ![Overview](assets/overview.png) | ![Churn Analysis](assets/churn-analysis.png) |

| Revenue Analysis | Demographic |
|---|---|
| ![Revenue Analysis](assets/revenue-analysis.png) | ![Demographic](assets/demographic.png) |

| Service Usage Analysis | Insights |
|---|---|
| ![Service Usage](assets/service-usage.png) | ![Insights](assets/insights.png) |

> Replace the images above with your own exported dashboard screenshots (save them in an `assets/` folder).

---

## 📁 Dataset

- **Source**: IBM Telco Customer Churn dataset
- **Size**: 7,043 customers, 1 fiscal quarter (Q3)
- **Granularity**: 1 row per customer, with demographic, service, contract, and billing attributes
- **Target variable**: `Customer Status` (Churned / Stayed / Joined)

---

## 🗂️ Dashboard Structure

The dashboard is organized into 7 pages, each answering a distinct business question:

| Page | What it answers |
|---|---|
| **Landing Page** | Project context and navigation hub |
| **Overview** | What's the overall health of the customer base? (Churn Rate, Retention Rate, Revenue Lost) |
| **Churn Analysis** | Who is churning, and under what conditions? (Contract, Tenure, Satisfaction, Offer, CLTV) |
| **Revenue Analysis** | What's the financial impact of churn? (Revenue Lost by Contract, Payment Method, Tenure) |
| **Demographic** | Are there demographic patterns in churn? (Age, Gender, City, Senior Citizen, Marital Status) |
| **Service Usage Analysis** | Which services increase or reduce churn risk? (Add-ons, Streaming, Internet Type) |
| **Insights** | Key findings and actionable recommendations |

---

## 🔍 Key Insights

**Overall Health**
- Churn Rate: **28.37%** · Retention Rate: **71.63%**
- Revenue Churn Rate: **17.24%**, lower than the customer churn rate, indicating the company is relatively more successful at retaining high-value customers

**Highest-Risk Segments**
| Segment | Churn Rate |
|---|---|
| Tenure < 1 year | **61.86%**, highest risk across the dashboard |
| Offer E | **52.9%** (426 of 805 users) |
| Month-to-Month contract | **51.69%** |
| Fiber Optic customers | **42.18%** |
| Senior Citizens | **42.81%** |

**Financial Insights**
- Month-to-Month Contract: Has the smallest revenue ($6.16M), but loses 40.4% of its revenue from churn. This is much higher than One Year (13.9%) and Two Year (3.7%) contracts.
- Average Monthly Charge: Churned customers ($74.44) pay more than customers who stayed ($61.26). This supports the finding that competitor offers are a major reason for customers leaving.
- CLTV: Customers who stayed ($4,530.19) have a higher CLTV than churned customers ($4,149.41). This shows that the company is relatively successful at retaining high-value customers, although the difference is only around 8%.
- Offer E: Has the highest churn rate but the lowest revenue loss. This may indicate that Offer E is mainly used by lower-value customers who are already more likely to leave.


---

## 💡 Recommendations

1. Improve the onboarding process during the first 12 months, as customers are most likely to leave during this period, with a churn rate of 61.86%.
2. Encourage Month-to-Month customers to switch to annual contracts, as this segment is more financially vulnerable and has lost 40.4% of its revenue.
3. Offer Online Security & Tech Support packages to new customers, as these two services are proven to be the most effective in keeping customers.
4. Review the Offer E program, as it has a high churn rate despite having a relatively low financial impact.
5. Create a special program for Senior Citizens, focusing on easy-to-use services and more personalized support.
6. Review Fiber Optic prices and service quality, especially compared to competitors, as competitor offers are one of the main reasons customers leave.

---

## 🛠️ Tools & Skills

- **Power BI Desktop**: dashboard design & interactivity
- **DAX**: custom measures (Churn Rate, Revenue Churn Rate, Churn Gap, CLTV comparison, tenure segmentation, etc.)
- **Power Query**: data transformation, unpivoting service columns, conditional grouping
- **Data Modeling**: relationship management between fact and unpivoted tables
- **Data Visualization & Dashboard Design**: KPI cards, gauges, waterfall-style charts, geographic maps

---

## 📐 Methodology Highlights

- Built custom DAX measures for **Churn Rate**, **Retention Rate**, and **Revenue Churn Rate**, based on `Customer Status` rather than raw row counts, to correctly exclude newly joined customers from the churn base
- Solved data duplication issues from **unpivoted service tables** by separating count-based measures (`DISTINCTCOUNT`) from financial measures (`AVERAGE` instead of `SUM`) to avoid fan-out errors
- Designed a **Churn Gap** metric (No − Yes churn rate difference) to quantify each service's protective or risk-increasing effect, with signed values (+/-) for direction
- Segmented customer tenure into logical year-based groups with custom DAX sorting to preserve chronological order in visuals
- Cross-referenced **CLTV** and **Revenue Lost** to distinguish "high churn volume" segments from "high financial impact" segments — revealing cases like Offer E where the two diverge

---

## 📬 Contact

Feel free to reach out if you'd like to discuss this project or explore the dataset further!

- **LinkedIn**: www.linkedin.com/in/arfinadhifahananti
- **Email**: arfinadhifa3@gmail.com
- **Portfolio**: https://portofolioarfinadhifa.framer.website/
