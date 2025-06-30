# GOWelfare - Employee Welfare Platform Analytics

## Project Overview

GOWelfare is an employee welfare platform that provides an app for local purchases, allowing employees to spend welfare credits at their favorite local shops rather than being limited to large retail chains. This project aims to implement systems to optimize the welfare platform and maximize both profit and user satisfaction.

## Project Objectives

- **Optimize** the welfare platform for maximum efficiency
- **Maximize profit** through data-driven insights
- **Enhance user satisfaction** by understanding spending patterns
- **Analyze user behavior** to improve platform offerings

## Dataset Description

The project utilizes four main datasets:

### 1. `giftcard_model`
Lists all giftcards available on the welfare application along with their associated brands.

| Column | Description | Unique Values |
|--------|-------------|---------------|
| `id` | Unique identifier for giftcard model | 96 |
| `amount` | Giftcard amount | 12 |
| `new_brand_name` | Brand name | 33 |
| `brand_id` | Brand identifier | 34 |
| `category` | Product category | 9 |
| `fee` | Transaction fee | 17 |
| `num_punti_vendita` | Number of sales points | 32 |

### 2. `transaction`
Lists all basic operations of users towards the welfare platform.

| Column | Description | Unique Values |
|--------|-------------|---------------|
| `id` | Transaction ID | 18,409 |
| `amount` | Transaction amount | 537 |
| `type` | Transaction type | 1 |
| `status` | Transaction status | 1 |
| `timestamp` | Transaction timestamp | 18,409 |
| `transaction_uuid_hash` | Hashed transaction UUID | 18,409 |
| `email_hash` | Hashed user email | 15,735 |
| `receiver_id_hash` | Hashed receiver ID | 15,735 |

### 3. `giftcard_obf`
Lists all giftcards bought by users.

| Column | Description | Unique Values |
|--------|-------------|---------------|
| `id` | Purchase ID | 40,189 |
| `provider_error_code` | Error code from provider | 8 |
| `purchase_date` | Date of purchase | 40,189 |
| `giftcard_model_id` | Reference to giftcard model | 94 |
| `transaction_uuid_hash` | Hashed transaction UUID | 40,189 |
| `client_email_hash` | Hashed client email | 9,053 |

### 4. `elected_giftcards_dec_2024_new.xlsx`
Contains daily selections of featured/recommended giftcard models for December 2024.

| Column | Description | Details |
|--------|-------------|---------|
| `date` | Daily timestamp | December 1-31, 2024 (31 days) |
| `giftcard_model_ids` | Array of selected model IDs | 15-30 selections per day |

**Key Statistics:**
- **Total selections**: 716 across 31 days
- **Average per day**: 23.1 giftcard models featured
- **Unique models featured**: 63 different giftcard models
- **Model ID range**: 1-110
- **Selection range**: 15-30 models per day

## Key Financial Metrics (FY 2023)

- **Total Turnover**: €2,299,656
- **Total Spent**: €1,002,055
- **Total Profit**: €26,645
- **Total Unspent**: €1,297,601
- **Potential Profit** (if all gift cards had maximum fee): €80,164

## Performance Analysis

### Best Performing Brands

**By Volume (FY 2023):**
- **CondividiAcquista**: 4,771 giftcards sold, €95,420 total amount

**By Revenue (FY 2023):**
- **SupermercatoElite**: €125,415 earned from 2,424 giftcards

### Featured Giftcard Models (December 2024)

Analysis of daily featured giftcard selections reveals consistent top performers:

**Most Featured Models:**
1. **Model IDs 3, 4, 22, 34**: Each featured 31 times (100% of days)
2. **Model ID 80**: Featured 27 times (87% of days)
3. **Model ID 26**: Featured 25 times (81% of days)
4. **Model ID 21**: Featured 24 times (77% of days)
5. **Model IDs 8, 15**: Each featured 23 times (74% of days)

These models demonstrate consistent selection for platform promotion, indicating either high popularity, strategic importance, or strong performance metrics.

### Category Distribution
The platform offers 9 main categories:
1. **Food** (dominant category - ~40% of purchases)
2. **Sport**
3. **Carburanti** (Fuel)
4. **Casa** (Home)
5. **Electronics**
6. **Abbigliamento** (Clothing)
7. **E-commerce**
8. **Brico** (DIY)
9. **Gaming**

## User Behavior Analysis

### Transaction Patterns
- **Most users** conduct low-value, infrequent transactions
- **Majority** of maximum gift card purchases fall between €40-60
- **Heavy concentration** of users with minimal transaction activity
- **Small subset** of high-value, frequent users driving significant revenue

### User Segmentation

Through clustering analysis, three distinct user segments were identified:

#### Cluster 0: Low Engagement Users
- Lower purchase counts across all categories
- Minimal platform interaction
- Represents the majority of the user base

#### Cluster 1: Moderate Users
- Moderate engagement levels
- Slightly higher activity in e-commerce and food categories
- Balanced spending behavior

#### Cluster 2: Heavy Spenders
- Higher mean transaction values
- Increased activity in food, e-commerce, and electronics
- Premium user segment with significant revenue contribution

### Anomaly Detection

**Outlier Analysis Results:**
- **572 outlier users** identified from 6,148 total users (9.3%)
- Outliers show significantly higher mean transaction amounts
- Broader transaction ranges indicating diverse spending behaviors
- Some negative minimum values suggesting refunds or adjustments

## Technical Implementation

### Analysis Methods Used
- **Exploratory Data Analysis (EDA)**
- **Principal Component Analysis (PCA)** for dimensionality reduction
- **K-means Clustering** for user segmentation
- **Interquartile Range (IQR)** method for anomaly detection
- **Statistical analysis** of transaction patterns

### Key Visualizations
- Giftcard amount and category distribution histograms
- User credit distribution analysis
- Time-series analysis of top-performing giftcard models (2023 vs 2024)
- Cluster visualization using PCA components

## Project Structure

```
GOWelfare/
├── data/
│   ├── giftcard_model.csv
│   ├── transaction.csv
│   ├── giftcard_obf.csv
│   └── elected_giftcards_dec_2024_new.xlsx
├── notebooks/
│   └── analysis.ipynb
├── visualizations/
│   ├── eda_charts/
│   ├── user_segmentation/
│   ├── anomaly_detection/
│   └── featured_models_analysis/
└── README.md
```

## Getting Started

### Prerequisites
- Python 3.7+
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Openpyxl (for Excel file handling)

### Data Files
Ensure the following data files are in the `data/` directory:
- `giftcard_model.csv`
- `transaction.csv` 
- `giftcard_obf.csv`
- `elected_giftcards_dec_2024_new.xlsx`




