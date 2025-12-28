
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

### Complete Dataset
**[`Kwara_full_dataset.csv`](./Kwara_full_dataset.csv)**
- Full engineered dataset with all parties (APC, PDP, LP, NNPP)
- 2,519 polling units × 4 parties = ~10,000 records
- Includes: votes, coordinates, neighbors, outlier scores, vote shares

**[`kwara_party_dataset.xlsx`](./kwara_party_dataset.xlsx)**
- Same data organized by party (separate sheets)
- Easier for party-specific analysis
- Sheets: APC, PDP, LP, NNPP

### Key Features in Dataset
| Feature | Description |
|---------|-------------|
| `PU-Code` | Unique polling unit identifier |
| `Votes` | Votes received by party |
| `Latitude/Longitude` | Geographic coordinates |
| `Neighbours` | Polling units within 1km |
| `Neighbour_Count` | Number of spatial neighbors |
| `Outlier_Score` | Z-score deviation from neighborhood |
| `Vote_Share` | Percentage of total votes |

## 📄 Full Report
**[Download detailed analysis report (PDF)](./https://drive.google.com/file/d/1ZgQJagGdBTHoR2oDY70IRg86SLV5vTXd/view?usp=drivesdk)**

Includes:
- Complete methodology documentation
- Statistical distribution analysis
- Top outlier cases with context
- Visualization of anomaly patterns
- Interpretation guidelines

## 🛠️ Tools & Technologies
- **Python**: Pandas, Scikit-learn (BallTree), GeoPy
- **Statistical Methods**: Z-score analysis, spatial clustering
- **Geocoding**: Google Sheets (Geocode by Awesome Table)
- **Visualization**: Matplotlib, Seaborn

## 📊 Sample Findings

### Top Outlier Example
**PU-Code: 23-08-07-023 (NNPP)**
- Actual votes: 64
- Neighbor average: 0.17
- Z-score: **164.69** (extreme anomaly)
- Interpretation: Requires investigation

### Distribution Summary
| Party | Mean Z-Score | Max Z-Score | Outliers (>2σ) |
|-------|--------------|-------------|----------------|
| APC | 0.68 | 4.11 | 16 units |
| PDP | 0.70 | 5.41 | 8 units |
| LP | 0.64 | 9.63 | 19 units |
| NNPP | 0.55 | 7.81 | 31 units |

## ⚠️ Important Note
Outliers indicate statistical anomalies requiring further investigation, not definitive evidence of malpractice. Multiple legitimate factors can produce outliers including:
- Demographic differences
- Varying voter turnout  
- Localized party dominance
- Data collection inconsistencies

## 📈 Potential Use Cases
- Electoral monitoring and verification
- Election integrity research
- Geospatial analysis methodology demonstration
- Anomaly detection techniques in civic data

## 📬 Contact
**Ayodeji Abdulwarith**  
Data Analyst | Lagos, Nigeria  
[LinkedIn](https://www.linkedin.com/in/ayodeji-abdulwarith/)

## 📜 License
Dataset: Public election results (2023 Kwara State)  
Analysis: Available for educational and research purposes

---

*Analysis conducted October 2024*
