# Holiday Destination Analytics — Data Analysis & Ranking

A comprehensive data analysis project that evaluates countries as holiday destinations by combining economic, environmental, and natural disaster risk factors using multivariate analysis and PCA (Principal Component Analysis).

---


## 📋 Project Overview

This project analyzes global travel destinations across three key dimensions to identify the best countries for holidays:

- **Economy**: Cost of living metrics (meals, transport, accommodation)
- **Environment**: Weather and climate conditions (temperature, wind, UV index, weather patterns)
- **Risk**: Natural disaster frequency and severity

The analysis combines these three datasets into a single master dataset and applies statistical methods to rank countries based on composite holiday suitability indexes.

---


## 🔄 Workflow

### 1. **Data Cleaning** (`Cleaning_Files_Code/`)
Each dataset undergoes individual cleaning and validation
Output: Three clean CSV files in `Cleaned_Csvs/`

### 2. **Data Combination** (`Combining_Code_And_Results/`)
- Merges all three cleaned datasets on country name
- Performs inner join on Cost of Living + Weather (170 countries)
- Left joins Natural Disasters (missing values treated as no recorded events)
- Generates `Combined_Holiday.csv` master dataset

### 3. **Statistical Analysis**
- **PCA Analysis**: Reduces dimensionality while preserving 90% of variance
- **Multivariate Analysis**: Explores relationships between economic, environmental, and risk factors
- Outputs: PCA scores and transformed datasets

### 4. **Holiday Indexes** (`Indexes/`)
Four different ranking approaches:

| Index | Focus |  
|-------|-------|
| `index_cheapest_coldest_country` | Budget + Cold climates |
| `index_cheapest_warmest_country` | Budget + Warm climates |
| `index_sweetspot_holiday` | Set ranges for preferred values |
| `index_sweetspot_holiday_pca` | Set ranges for preferred values combined with PCA |

**Index Weights:**
- Economy: 35%
- Environment: 40%
- Risk: 25%

---

## 📊 Key Metrics

### Economic Indicators
- Mid-range meal price (per person)
- One-way local transport ticket cost
- Apartment rental cost (monthly)

### Environmental Indicators
- Temperature (°C) — Target: 23-26°C
- Wind speed (kph) — Target: 7-14 kph
- UV Index — Target: 4.0-5.5
- Weather condition score (0-5)

### Risk Indicators
- Disaster count (frequency)
- Median disaster severity (0-1)
- Unique days under threat (per year)

---

## 🔍 Key Findings

The analysis reveals:
- **170 countries** analyzed across all three dimensions
- **Economic factors** contribute ~35% to ideal holiday selection
- **Climate/environment** is the strongest determinant (~40%)
- **Natural disaster risk** is significant (~25% of decision-making)
- PCA reduces 10+ economic, environmental, and risk variables into interpretable components

---

## 📝 Notes

- Missing disaster records are treated as **structural zeros** (no recorded events = safe)
- All three datasets use inner join (Cost + Weather) to ensure data quality
- Outliers are identified but retained to preserve real-world variation
- Scaling and normalization applied before PCA to prevent dominance by high-variance features

