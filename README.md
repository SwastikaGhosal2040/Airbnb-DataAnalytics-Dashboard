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

The following table summarizes the data preprocessing and cleaning activities performed on the Airbnb dataset before developing the dashboard.

| Column Name | Activities |
|-------------|------------|
| `neighbourhood_group` | Removed the column because it contained entirely missing values and did not contribute to the analysis. |
| `host_name` | Missing values were replaced with **"Unknown"**. |
| `last_review` | Converted from text to **Date** format (`datetime`). Missing values were intentionally retained because they represent listings with no reviews. |
| `scrape_date` | Converted from text to **Date** format (`datetime`). |
| `reviews_per_month` | Verified that missing values corresponded to listings with zero reviews, then replaced missing values with **0**. |
| `price` | Records containing missing prices were removed since price is a critical analytical attribute. |
| `license` | Missing values were replaced with **"Not Available"**. |
| **Entire Dataset** | Checked for duplicate records. No duplicate rows were found. |
| **Entire Dataset** | Verified remaining missing values after cleaning. |
| **Entire Dataset** | Generated a reproducible random sample of **50,000** records using `random_state=42`. |
| `price` | Performed statistical analysis using descriptive statistics and quantiles to identify extreme values. |
| `price` | Removed price outliers by retaining listings with a price less than or equal to **6188**. |
| **Entire Dataset** | Generated a new random sample of **50,000** cleaned records after outlier removal. |
| **Entire Dataset** | Validated dataset structure, data types, missing values, and duplicate records before export. |
| **Entire Dataset** | Exported the final cleaned dataset as **Airbnb_CleanData.csv** for dashboard development. |

---
