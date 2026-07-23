<h1 align="center">Airbnb Data Analytics Dashboard</h1>

<p align="center">
An interactive business intelligence dashboard developed using <b>Google Sheets</b> and <b>Google Looker Studio (formerly Google Data Studio)</b> to analyze Airbnb listing performance, pricing strategies, customer engagement, room type distribution, and property availability across five major cities.
</p>

---

# Project Overview

This project presents an end-to-end **Airbnb Data Analytics Dashboard** developed using a dataset containing **50,000 Airbnb listings**.

The objective of this project is to transform raw Airbnb listing data into meaningful business insights through interactive dashboards. The analysis focuses on listing performance, pricing trends, room type distribution, customer engagement, and annual availability to support data-driven business decision-making.

The dashboard consists of **two analytical pages**:

### Page 1 – Executive Overview

Provides a high-level business summary through KPI cards and interactive visualizations, helping stakeholders quickly understand the overall performance of the Airbnb marketplace.

### Page 2 – Detailed Analytical Insight

Provides deeper analytical insights into customer behavior, pricing patterns, listing distribution, minimum stay requirements, and city-wise performance through advanced visualizations.

---

# Cover Image

![Cover Image](Images/CoverPhoto.png)

---

# File Details

| Attribute | Details |
|------------|---------|
| **Filename** | **[Airbnb_CleanData.csv](https://docs.google.com/spreadsheets/d/164MJ79fPHCDYt3I5QY5TI4j1fPSt8Dhg3D1ko--Rf-o/edit?usp=sharing)** |
| **Google Colab Notebook** | **[Airbnb_Data_Cleaning.ipynb](https://colab.research.google.com/drive/1IpU9saO532VS99zbu2CB4bg3bPT4OXix?usp=sharing)** |
| **Kaggle Notebook** | **[Airbnb Data Cleaning – Swastika Ghosal](https://www.kaggle.com/code/swastikaghosal/airbnb-data-cleaning-swastika-ghosal)** |
| **Total Records** | **50,000** |
| **Primary Keys** | `id`, `host_id`, `city`, `room_type` |
| **Source of Data** | **[airbnb_top_cities.csv](https://www.kaggle.com/datasets/darkmatternet/airbnb-listings-nyc-london-paris-tokyo-and-more)** |
| **Dashboard** | **[Airbnb Analytics Dashboard](https://datastudio.google.com/u/1/reporting/a4868b03-8c2d-41b0-9e78-c85cdaaa0402/page/cks2F/edit)** |

---

# Repository Structure

```text
Airbnb-DataAnalytics-Dashboard
│
├── Dataset
│   └── Airbnb_Clean_Data.csv
│
├── Images
│   ├── CoverPhoto.png
│   ├── Dashboard_Page1.png
│   └── Dashboard_Page2.png
│
└── README.md
```



# Tools & Technologies

- **Kaggle** – Dataset acquisition
- **Google Sheets** – Data validation and preparation
- **Microsoft Excel** – Performed additional exploration and verification
- **Google Colab** – Data cleaning and preprocessing
- **Pandas** – Data manipulation and transformation
- **Google Looker Studio (Google Data Studio)** – Interactive dashboard development and visualization

---

# Data Dictionary

The following table describes the columns available in the cleaned Airbnb dataset used for analysis and dashboard development.

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| `id` | Unique identifier for each Airbnb listing | Integer |
| `name` | Name or title of the Airbnb listing | Text |
| `host_id` | Unique identifier of the host | Integer |
| `host_name` | Name of the Airbnb host | Text |
| `neighbourhood` | Neighborhood where the listing is located | Text |
| `latitude` | Latitude coordinate of the property | Decimal |
| `longitude` | Longitude coordinate of the property | Decimal |
| `room_type` | Type of accommodation offered | Text |
| `price` | Nightly rental price of the listing | Decimal |
| `minimum_nights` | Minimum number of nights required for booking | Integer |
| `number_of_reviews` | Total number of customer reviews received | Integer |
| `last_review` | Date of the most recent customer review | Date |
| `reviews_per_month` | Average number of reviews received per month | Decimal |
| `calculated_host_listings_count` | Number of active listings owned by the host | Integer |
| `availability_365` | Number of days the listing is available in a year | Integer |
| `number_of_reviews_ltm` | Number of reviews received during the last 12 months | Integer |
| `license` | Registration or license information of the listing | Text |
| `city` | City where the Airbnb listing is located | Text |
| `scrape_date` | Date on which the dataset was collected | Date |


---


# Data Cleaning Notes

The following table summarizes the data cleaning and preprocessing activities performed on the Airbnb dataset before dashboard development.

| Column Name | Activities |
|-------------|------------|
| `neighbourhood_group` | Removed the column because it contained only missing values and did not contribute to the analysis. |
| `host_name` | Replaced missing values with **"Unknown"** to preserve valid listing records. |
| `last_review` | Converted the column to **DateTime** format. Missing values were intentionally retained because they represent listings without customer reviews. |
| `scrape_date` | Converted the column to **DateTime** format for proper date-based analysis. |
| `reviews_per_month` | Verified that missing values corresponded to listings with zero reviews and replaced them with **0**. |
| `price` | Removed records containing missing values. Performed statistical analysis to identify outliers and retained listings with prices less than or equal to **6188**. |
| `license` | Replaced missing values with **"Not Available"**. |

---


---

# Executive Overview Dashboard

The Executive Overview dashboard provides a high-level summary of Airbnb listing performance across five major cities. It enables stakeholders to monitor key business metrics, compare pricing strategies, evaluate listing distribution, analyze property availability, and identify geographical trends through interactive visualizations.

## Dashboard Preview

![Executive Overview Dashboard](Images/Dashboard_Page1.png)

---

## A. Key Insights

### 1. KPI Summary

- The dataset contains **50,000 Airbnb listings** managed by **29,829 active hosts**.
- The average listing price across all cities is **₹421.82**.
- The average minimum stay requirement is **7.15 nights**.
- The listings have accumulated approximately **2 million customer reviews**, indicating strong customer engagement.
- On average, each listing receives **40.49 reviews**, with **1.14 reviews per month**.
- Properties remain available for an average of **227 days per year**, indicating moderate annual occupancy.

---

### 2. Average Listing Price by Room Type

- **Hotel rooms** have the highest average listing price (₹810).
- **Entire homes/apartments** are the second most expensive accommodation type.
- **Private rooms** and **Shared rooms** are comparatively more affordable, making them attractive to budget-conscious travelers.

---

### 3. Listing Share by Room Type

- **Entire homes/apartments** dominate the marketplace with approximately **35,000 listings**.
- **Private rooms** represent the second-largest accommodation category.
- **Shared rooms** and **Hotel rooms** account for only a small fraction of total listings.

---

### 4. Listings by City (Geo Map)

- Listing availability varies significantly across cities.
- Some metropolitan cities have a much larger concentration of Airbnb properties, indicating stronger market penetration.
- The geographical visualization clearly highlights regional differences in listing density.

---

### 5. Average Availability (Days) by City

- **Bangkok** has the highest average annual availability (**276 days**).
- **Rome** and **Barcelona** show similar availability levels.
- **London** has slightly lower availability.
- **Amsterdam** has the lowest average availability, suggesting comparatively higher occupancy.

---

### 6. Annual Availability Distribution

- Property availability is distributed across the entire year.
- A large number of listings remain available for **340–365 days**, indicating many properties operate almost year-round.
- Moderate availability ranges also contain a substantial number of listings, reflecting diverse host availability strategies.

---

## B. Analytical Recommendations

### KPI Summary

- Monitor average pricing and occupancy trends regularly to identify market shifts.
- Improve host engagement initiatives to increase customer reviews and listing activity.
- Track average availability to better understand seasonal demand patterns.

---

### Average Listing Price by Room Type

- Premium hotel rooms should continue targeting high-value travelers.
- Private and shared rooms can be promoted to budget travelers through pricing campaigns.
- Dynamic pricing strategies can help maximize revenue across different accommodation types.

---

### Listing Share by Room Type

- Encourage growth in underrepresented accommodation categories such as hotel rooms and shared rooms.
- Expand the supply of high-demand property types while maintaining a balanced marketplace.
- Analyze customer demand before increasing inventory in less popular room categories.

---

### Listings by City

- Prioritize marketing investments in cities with high listing concentrations.
- Develop targeted growth strategies for cities with lower Airbnb market penetration.
- Use geographic performance monitoring to optimize regional business decisions.

---

### Average Availability (Days) by City

- Investigate why Bangkok listings remain available longer and whether occupancy can be improved.
- Study Amsterdam's comparatively lower availability to identify successful booking patterns.
- Adjust promotional campaigns according to city-specific occupancy behavior.

---

### Annual Availability Distribution

- Encourage hosts with extremely high availability to optimize pricing during low-demand periods.
- Identify seasonal booking opportunities to reduce prolonged vacancies.
- Develop occupancy-focused promotional campaigns for listings with consistently high availability.
