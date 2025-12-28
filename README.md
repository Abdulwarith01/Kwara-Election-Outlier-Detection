# Election Integrity Analysis - Kwara State 2023
**Geospatial Outlier Detection Using Statistical Methods**

## 🎯 Overview
Applied geospatial analysis and statistical outlier detection to identify potential electoral irregularities across **2,519 polling units** in Kwara State's 2023 Presidential Election.

## 📊 Key Findings
- **74 polling units** flagged with outlier scores > 2σ (95% confidence)
- **NNPP** showed highest anomaly concentration (31 units, some with Z-scores > 4σ)
- **Spatial clustering** identified 3 high-risk LGAs
- **Methodology validated** through vote-share cross-analysis

## 🔬 Methodology

### 1. Data Engineering
- Geocoded 2,519 polling units using latitude/longitude coordinates
- Identified spatial neighbors within 1km radius using **BallTree algorithm** (Haversine metric)
- Calculated party-specific outlier scores comparing each unit to its neighborhood average

### 2. Statistical Analysis
- Computed Z-scores to measure deviation from neighborhood patterns
- Applied 95% confidence threshold (|Z| > 2) to flag anomalies
- Cross-validated with vote-share percentages for context

### 3. Spatial Clustering
- Analyzed geographic distribution of outliers
- Identified concentrated anomaly zones vs. isolated incidents

## 📁 Dataset Files

| File | Description | Records |
|------|-------------|---------|
| `kwara_election_with_outliers_APC.csv` | APC votes with outlier scores & neighbors | 2,519 |
| `kwara_election_with_outliers_PDP.csv` | PDP votes with outlier scores & neighbors | 2,519 |
| `kwara_election_with_outliers_LP.csv` | LP votes with outlier scores & neighbors | 2,519 |
| `kwara_election_with_outliers_NNPP.csv` | NNPP votes with outlier scores & neighbors | 2,519 |

### Engineered Features
- `Neighbours`: List of polling units within 1km radius
- `Neighbour_Count`: Number of spatial neighbors
- `Outlier_Score`: Z-score deviation from neighborhood average
- `Vote_Share`: Percentage of total votes for each party

## 📄 Full Report
[Download detailed analysis report (PDF)](./Election Analysis Report.pdf)

## 🛠️ Tools & Technologies
- **Python**: Pandas, Scikit-learn (BallTree), GeoPy
- **Statistical Methods**: Z-score analysis, spatial clustering
- **Geocoding**: Google Sheets (Geocode by Awesome Table)

## ⚠️ Important Note
Outliers indicate statistical anomalies requiring further investigation, not definitive evidence of malpractice. Multiple legitimate factors can produce outliers including:
- Demographic differences
- Varying voter turnout
- Localized party dominance
- Data collection inconsistencies

## 📬 Contact
**Ayodeji Abdulwarith**  
Data Analyst | Lagos, Nigeria  
[LinkedIn](https://www.linkedin.com/in/ayodeji-abdulwarith/)

---

*Analysis conducted October 2024. Dataset: 2023 Kwara State Presidential Election Results.*
