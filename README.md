# 🔄 Funnel Analysis — Python Data Analytics Project

A business-focused **Funnel Analysis project using Python** to understand customer journey behavior, identify major conversion bottlenecks, evaluate channel and segment performance, and uncover opportunities to improve purchase conversion and revenue.

---

## 📌 Project Overview

This project analyzes **21,663 customer interaction events across 10,000 unique sessions** to evaluate how users progress through an e-commerce conversion funnel:

**Browse → Add to Cart → Checkout → Purchase**

The analysis uses Python-based data cleaning, transformation, exploratory data analysis, funnel analysis, segmentation, behavioral analysis, and visualization to identify where customers drop off and which business segments demonstrate stronger conversion performance.

The project focuses on converting raw customer interaction data into **actionable business insights and recommendations**.

---

## 🎯 Business Problem

A high volume of website traffic does not necessarily translate into purchases.

The business needs to understand:

"_Where are customers abandoning the purchasing journey, which customer segments perform differently, and what can be done to improve funnel conversion and revenue?_"

- Where customers abandon the purchasing journey
- Which funnel stage creates the greatest friction
- Which acquisition channels perform better
- Which devices and regions have stronger conversion
- Which product categories attract customers but struggle to convert
- When customers are most likely to purchase
- Whether customer engagement and session behavior influence conversion

### Business Objective

The primary objective is to identify the major drivers of funnel drop-off and provide data-driven recommendations to improve:

- Customer conversion
- Checkout completion
- Marketing effectiveness
- Customer experience
- Revenue generation

---

## ❓ Business Questions

1. What does the overall customer funnel look like, and how many sessions reach each stage?
2. Where is the largest funnel drop-off?
3. Which acquisition channel converts browsing sessions into purchases most effectively?
4. Which acquisition channels generate the most revenue?
5. Which device has the biggest funnel performance gap?
6. Which region has the strongest and weakest purchase conversion?
7. Which product categories attract users but struggle to convert?
8. Does funnel performance vary by day of the week?
9. What hours generate the strongest purchase conversion?
10. How does bounce behavior vary across acquisition channels and devices?
11. Does session duration influence purchase conversion?
12. What are the most common customer journey paths, and where do users abandon the funnel?

---

## 🔄 Project Workflow

    Raw CSV Dataset
           ↓
    Data Import into Python
           ↓
    Data Cleaning & Validation
           ↓
    Feature Engineering
           ↓
    Session-Level Data Preparation
           ↓
    Exploratory Data Analysis
           ↓
    Funnel & Conversion Analysis
           ↓
    Business Questions 1–12
           ↓
    Insights & Business Impact
           ↓
    Recommendations

---

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| **Python** | Data analysis and business problem-solving |
| **Pandas** | Data cleaning, transformation and aggregation |
| **NumPy** | Numerical analysis and calculations |
| **Matplotlib** | Data visualization |
| **Seaborn** | Statistical and analytical visualization |
| **Plotly** | Interactive visual analysis |
| **Jupyter Notebook** | Analysis development and documentation |
| **CSV** | Source data format |

---

## 📂 Dataset Overview

The dataset contains customer interaction events generated throughout the e-commerce purchasing journey.

| Column | Description |
|---|---|
| `User_ID` | Unique customer identifier |
| `Session_ID` | Unique browsing session identifier |
| `Event` | Customer funnel event |
| `Timestamp` | Date and time of the event |
| `Device` | Device used during the session |
| `Region` | Customer geographic region |
| `Channel` | Acquisition / marketing channel |
| `Product_Category` | Product category associated with the session |
| `Revenue` | Revenue generated from the session |
| `Bounce_Flag` | Indicates whether the session was classified as a bounce |

### Dataset Summary

- **21,663** total event records
- **10,000** unique sessions
- **10,000** unique users
- **4** funnel stages
- **4** acquisition channels
- **3** device types
- **4** regions
- **5** product categories
- No missing values
- No duplicate records

---

## 🧹 Data Cleaning & Preparation

The dataset was validated and prepared before performing business analysis.

### Data Cleaning

- Inspected dataset structure and data types
- Checked for missing values
- Checked for duplicate records
- Converted `Timestamp` into datetime format
- Standardized `Bounce_Flag` from categorical values into numerical indicators
- Verified categorical dimensions including device, region, channel and product category

### Feature Engineering

Additional analytical features were created from the timestamp and session data:

- `Date`
- `Day_of_Week`
- `Hour`
- `Week_Number`
- `Event_Sequence`
- `Session_Duration_Minutes`
- `Events_Per_Session`
- `Last_Event`
- `Purchased`

### Session-Level Analysis

A session-level dataset was created to evaluate customer behavior at the session level.

This enabled analysis of:

- Purchase conversion
- Session duration
- Events per session
- Bounce behavior
- Customer journey completion
- Channel performance
- Device performance
- Regional performance
- Product-category performance

---

# 🔍 Funnel Analysis

## 1️⃣ Overall Customer Funnel

**Business Question:**  
What does the overall customer funnel look like, and how many sessions reach each stage?

**Analysis Approach:**

- Count unique sessions reaching each funnel stage.
- Calculate stage-to-stage conversion rates.
- Calculate overall Browse-to-Purchase conversion.
- Compare the volume retained at each stage.

**Key Finding:**

- **10,000** sessions reached Browse
- **7,059** reached Add to Cart
- **3,524** reached Checkout
- **1,080** resulted in Purchase
- Overall Browse-to-Purchase conversion was **10.80%**

**Business Value:**  
Provides an overall view of funnel health and establishes the baseline for identifying conversion opportunities.

---

## 2️⃣ Largest Funnel Drop-Off

**Business Question:**  
Where is the largest funnel drop-off?

**Analysis Approach:**

- Calculate conversion between consecutive funnel stages.
- Calculate percentage drop-off at each stage.
- Identify the stage with the greatest customer loss.

**Key Finding:**

| Funnel Transition | Conversion | Drop-Off |
|---|---:|---:|
| Browse → Add to Cart | 70.59% | 29.41% |
| Add to Cart → Checkout | 49.92% | 50.08% |
| Checkout → Purchase | 30.65% | 69.35% |

The largest bottleneck occurs between **Checkout and Purchase**, where **69.35% of sessions drop off**.

**Business Value:**  
Identifies checkout completion as the highest-priority area for conversion optimization.

---

## 3️⃣ Acquisition Channel Conversion

**Business Question:**  
Which acquisition channel converts browsing sessions into purchases most effectively?

**Analysis Approach:**

- Group funnel activity by acquisition channel.
- Compare Browse and Purchase activity.
- Calculate Browse-to-Purchase conversion rates.
- Compare the relative efficiency of each channel.

**Key Finding:**

- **Email:** 11.21%
- **Google Ads:** 10.90%
- **Social Media:** 10.86%
- **Organic:** 10.23%

The differences between channels are relatively narrow, indicating broadly similar conversion efficiency.

**Business Value:**  
Helps marketing teams evaluate channel effectiveness and identify opportunities for campaign optimization.

---

## 4️⃣ Channel Revenue Performance

**Business Question:**  
Which acquisition channels generate the most revenue?

**Analysis Approach:**

- Aggregate session-level revenue by acquisition channel.
- Compare total revenue generated across channels.
- Evaluate revenue alongside session volume and purchases.

**Key Finding:**

| Channel | Sessions | Purchases | Revenue |
|---|---:|---:|---:|
| Google Ads | 2,560 | 282 | 312,769.26 |
| Organic | 2,511 | 281 | 307,448.35 |
| Social Media | 2,440 | 263 | 280,071.63 |
| Email | 2,489 | 254 | 276,116.54 |

**Business Value:**  
Helps prioritize marketing investment toward channels that contribute strongly to revenue while considering conversion efficiency.

---

## 5️⃣ Device Funnel Performance

**Business Question:**  
Which device has the biggest funnel performance gap?

**Analysis Approach:**

- Analyze funnel stages by device.
- Calculate stage-level and overall conversion rates.
- Compare Desktop, Mobile and Tablet performance.

**Key Finding:**

| Device | Browse → Purchase |
|---|---:|
| Tablet | **11.52%** |
| Mobile | **11.03%** |
| Desktop | **9.85%** |

Desktop has the weakest overall conversion, with particularly low performance at the Checkout-to-Purchase stage.

**Business Value:**  
Highlights the need to investigate desktop checkout usability and potential device-specific customer experience issues.

---

## 6️⃣ Regional Conversion Performance

**Business Question:**  
Which region has the strongest and weakest purchase conversion?

**Analysis Approach:**

- Group sessions by region.
- Calculate purchase conversion.
- Compare performance across geographic segments.

**Key Finding:**

| Region | Purchase Conversion |
|---|---:|
| South | **11.25%** |
| East | **11.14%** |
| North | **10.42%** |
| West | **10.38%** |

South demonstrates the strongest conversion, while West records the lowest.

**Business Value:**  
Supports regional marketing optimization and helps identify areas where localized strategies may improve performance.

---

## 7️⃣ Product Category Conversion

**Business Question:**  
Which product categories attract users but struggle to convert?

**Analysis Approach:**

- Analyze funnel stages by product category.
- Compare Add-to-Cart, Checkout and Purchase conversion.
- Identify categories with stronger engagement but weaker purchase conversion.

**Key Finding:**

- **Electronics** recorded the highest purchase conversion at **11.19%**.
- **Beauty** recorded the lowest purchase conversion at **10.16%**.
- **Sports** recorded the strongest Add-to-Cart rate at **71.85%**.

**Business Value:**  
Helps identify product categories requiring better pricing, product information, promotions or checkout strategies.

---

## 8️⃣ Day-of-Week Conversion

**Business Question:**  
Does funnel performance vary by day of the week?

**Analysis Approach:**

- Extract the day of the week from session timestamps.
- Group sessions by day.
- Calculate purchase conversion for each day.
- Compare high- and low-performing days.

**Key Finding:**

- **Monday:** 11.95% — highest conversion
- **Sunday:** 11.80%
- **Saturday:** 11.03%
- **Thursday:** 11.02%
- **Friday:** 10.65%
- **Wednesday:** 9.71%
- **Tuesday:** 9.41% — lowest conversion

**Business Value:**  
Can support timing decisions for promotions, campaigns and conversion-focused marketing activities.

---

## 9️⃣ Entry-Hour Purchase Conversion

**Business Question:**  
What hours generate the strongest purchase conversion?

**Analysis Approach:**

- Extract the entry hour from session timestamps.
- Group sessions by hour.
- Calculate purchase conversion for each hour.
- Identify peak and low-conversion periods.

**Key Finding:**

- Highest conversion: **17:00 — 12.88%**
- Lowest conversion: **11:00 — 8.31%**

**Business Value:**  
Supports time-based campaign scheduling and helps businesses focus promotional activity around stronger purchase-intent periods.

---

## 🔟 Bounce Behavior

**Business Question:**  
How does bounce behavior vary across acquisition channels and devices?

**Analysis Approach:**

- Calculate overall bounce rate.
- Compare bounce rates by acquisition channel.
- Compare bounce rates by device.
- Evaluate whether specific segments explain the overall bounce level.

**Key Finding:**

Overall bounce rate was **89.20%**.

### By Channel

- Email: 89.80%
- Social Media: 89.22%
- Google Ads: 88.98%
- Organic: 88.81%

### By Device

- Tablet: 89.62%
- Mobile: 89.15%
- Desktop: 88.83%

The differences are relatively small across both channels and devices.

**Business Value:**  
Suggests that high bounce behavior is not driven by a single acquisition channel or device and may require deeper investigation into landing pages, content relevance and customer experience.

---

## 1️⃣1️⃣ Session Duration & Conversion

**Business Question:**  
Does session duration influence purchase conversion?

**Analysis Approach:**

- Calculate session duration using the first and last event timestamps.
- Segment sessions into duration groups.
- Compare purchase conversion across duration segments.

**Key Finding:**

| Session Duration | Sessions | Purchases | Conversion |
|---|---:|---:|---:|
| 0–1 min | 2,941 | 0 | 0% |
| 1–5 min | 3,950 | 0 | 0% |
| 5–10 min | 2,566 | 537 | 20.93% |
| 10+ min | 543 | 543 | 100% |

Longer sessions are strongly associated with purchase completion in this dataset.

**Business Value:**  
Highlights the importance of meaningful customer engagement and suggests that businesses should focus on reducing friction while keeping users engaged through the purchasing journey.

---

## 1️⃣2️⃣ Customer Journey Paths

**Business Question:**  
What are the most common customer journey paths, and where do users abandon the funnel?

**Analysis Approach:**

- Sort events chronologically within each session.
- Create event sequences for every session.
- Identify the final event and common journey paths.
- Compare completed and abandoned journeys.

**Key Finding:**

| Customer Journey | Sessions |
|---|---:|
| Browse → Add to Cart | 3,535 |
| Browse Only | 2,941 |
| Browse → Add to Cart → Checkout | 2,444 |
| Browse → Add to Cart → Checkout → Purchase | 1,080 |

The analysis highlights significant abandonment before purchase completion, particularly among users who reach Checkout.

**Business Value:**  
Provides a behavioral view of customer abandonment and helps prioritize specific journey stages for optimization.

---

# 💼 Business Impact

1. Helps identify and prioritize the biggest funnel bottlenecks affecting purchase conversion.

2. Supports checkout optimization by highlighting the significant Checkout-to-Purchase drop-off.

3. Helps marketing teams evaluate acquisition channels based on conversion and revenue contribution.

4. Supports device-specific optimization by identifying weaker Desktop conversion performance.

5. Enables regional performance comparison and targeted geographic strategies.

6. Supports product-category optimization by identifying categories with stronger or weaker conversion.

7. Helps optimize campaign timing based on day-of-week and entry-hour conversion patterns.

8. Highlights potential landing-page and customer-experience issues through bounce-rate analysis.

9. Helps understand the relationship between customer engagement and purchase behavior.

10. Provides a structured framework for improving customer journey performance and revenue conversion.

---

# 🎯 Recommendations

### 1. Optimize Checkout

Prioritize the Checkout-to-Purchase stage by:

- Simplifying the checkout process
- Reducing unnecessary form fields
- Improving payment reliability
- Providing transparent delivery and pricing information
- Strengthening trust and security signals

### 2. Improve Cart-to-Checkout Conversion

- Improve cart-page usability
- Strengthen checkout CTAs
- Display shipping information earlier
- Use abandoned-cart reminders
- Test targeted incentives for high-intent users

### 3. Optimize Marketing Investment

- Continue evaluating Google Ads and Organic for revenue contribution
- Compare channel revenue against acquisition costs
- Optimize campaigns using conversion and revenue quality
- Investigate opportunities to improve Email revenue performance

### 4. Investigate Desktop Experience

- Conduct a desktop checkout UX audit
- Test page speed and payment flows
- Review browser-specific issues
- Compare desktop behavior against higher-performing devices

### 5. Address High Bounce Rates

- Review landing-page relevance
- Improve campaign-to-landing-page alignment
- Improve website performance
- Strengthen calls-to-action
- Analyze bounce behavior at landing-page and campaign level

### 6. Use Time-Based Campaign Optimization

- Test campaigns around higher-conversion periods
- Prioritize stronger-performing days and hours
- Use retargeting during high-intent periods
- Test different promotional strategies during weaker periods

### 7. Improve Product Category Performance

- Investigate weaker-performing categories
- Improve product descriptions and imagery
- Review pricing and promotional strategies
- Introduce personalized recommendations and cross-selling

---

# 📊 Key Performance Indicators

| KPI | Value |
|---|---:|
| Total Events | **21,663** |
| Total Sessions | **10,000** |
| Browse Sessions | **10,000** |
| Add-to-Cart Sessions | **7,059** |
| Checkout Sessions | **3,524** |
| Purchase Sessions | **1,080** |
| Overall Conversion | **10.80%** |
| Checkout-to-Purchase Conversion | **30.65%** |
| Checkout-to-Purchase Drop-Off | **69.35%** |
| Overall Bounce Rate | **89.20%** |
| Highest Device Conversion | **Tablet — 11.52%** |
| Highest Region Conversion | **South — 11.25%** |
| Highest Category Conversion | **Electronics — 11.19%** |
| Highest Entry-Hour Conversion | **17:00 — 12.88%** |

---

# 📚 Analytical Techniques Used

- Data Cleaning
- Data Validation
- Data Transformation
- Exploratory Data Analysis
- Funnel Analysis
- Conversion Rate Analysis
- Drop-Off Analysis
- Session-Level Analysis
- Customer Journey Analysis
- Behavioral Analysis
- Segmentation Analysis
- Time-Based Analysis
- Channel Performance Analysis
- Revenue Analysis
- KPI Analysis
- Feature Engineering
- Data Visualization
- Business Insight Generation

---

# 📦 Project Deliverables

### 📓 Python Jupyter Notebook

Complete end-to-end analysis covering:

- Data loading
- Data cleaning
- Data validation
- Feature engineering
- Exploratory Data Analysis
- Funnel analysis
- Customer journey analysis
- Business questions
- Visualizations
- Insights
- Recommendations

### 📑 Executive Summary

A professional business summary covering:

- Project Overview
- Business Problem
- Business Questions
- Key Insights
- Recommendations
- Conclusion

### 📄 GitHub README

Detailed documentation of the project's:

- Business objective
- Dataset
- Workflow
- Methodology
- Analysis
- Business impact
- Recommendations
- Key performance indicators

---

# 📁 Repository Structure

    Funnel-Analysis/
    │
    ├── 📂 Dataset/
    │   └── funnel_analysis_data.csv
    │
    ├── 📂 Reports/
    │   └── Executive_Summary.pdf
    │   └── Funnel_Analysis.ipynb
    │
    └── 📄 README.md

---

# 🎓 Skills Demonstrated

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly
- Data Cleaning
- Data Transformation
- Exploratory Data Analysis
- Funnel Analysis
- Customer Journey Analysis
- KPI Analysis
- Business Analysis
- Data Visualization
- Analytical Thinking
- Problem Solving
- Data-Driven Decision Making
- Business Insight Communication

---

# 🚀 Project Learning Outcomes

This project strengthened my ability to use Python to solve practical business problems through a structured analytical approach:

    Business Problem
           ↓
    Business Questions
           ↓
    Data Understanding
           ↓
    Data Cleaning
           ↓
    Feature Engineering
           ↓
    Exploratory Data Analysis
           ↓
    Funnel & Behavioral Analysis
           ↓
    Key Insights
           ↓
    Business Recommendations

The project demonstrates the ability to move from **raw data to actionable business recommendations**, rather than focusing only on descriptive statistics or visualizations.

---

# 🏁 Conclusion

The **Funnel Analysis** project demonstrates how Python can be used to transform customer interaction data into meaningful business intelligence.

The analysis identified **Checkout-to-Purchase as the primary funnel bottleneck**, with a **69.35% drop-off**, while also highlighting differences across acquisition channels, devices, regions, product categories and customer behavior.

The findings provide a practical foundation for improving checkout performance, optimizing marketing investment, addressing device-level friction, improving customer engagement and increasing overall purchase conversion.

---

# 👨‍💻 About Me

**Sanjay Singh | Data Analyst**

I am a Data Analyst focused on transforming data into actionable insights and solving business problems through analytical thinking and a strong technical foundation.

My core areas include:

**SQL | Power BI | Python | Excel | Data Analysis | Data Visualization | Business Intelligence | KPI Analysis**

---

# 📌 Connect With Me

- 💼 **LinkedIn:** www.linkedin.com/in/sanjay-singh-509aa7135
- 💻 **GitHub:** https://github.com/itssanju1806
- 📧 **Email:** singhsanjay846@gmail.com

---

⭐ If you found this project useful, feel free to explore the repository and connect with me on LinkedIn.
