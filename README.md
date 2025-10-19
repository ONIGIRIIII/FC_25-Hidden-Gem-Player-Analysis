# ⚽ FC 25 Hidden Gems Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-1.5+-green.svg)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow.svg)
![License](https://img.shields.io/badge/License-MIT-red.svg)

## 📊 Project Overview

An advanced data analytics project that identifies undervalued football players (hidden gems) in FIFA/FC 25 using custom performance indices, position-specific metrics, and comprehensive statistical analysis. The project combines Python-based EDA with interactive Power BI dashboards to provide actionable insights for football scouts, FIFA gamers, and sports analysts.

**🔗 [View Interactive Power BI Dashboard](https://app.powerbi.com/view?r=eyJrIjoiM2FkNzQ5NzAtMjEyZS00MjkzLWI1YTYtOThhNmU5ZGVhOGM0IiwidCI6Ijk4OTk3ZjE3LWI5Y2MtNDVhNy05ZTkxLThhOWFhMTlkMTg5NiJ9)**

---

## 🎯 Key Features

- **Position-Specific Performance Indices**: Custom weighted algorithms for Strikers, Wingers, Midfielders, and Defenders
- **Value Score Calculation**: Identifies players performing above their overall rating
- **Hidden Gem Detection**: Multi-factor analysis combining value, age, league tier, and rating
- **Interactive Power BI Dashboard**: Dynamic filtering by position, league, age, and performance metrics
- **Comprehensive EDA**: 14,345 players analyzed across 58 attributes

---

## 📈 Key Findings

### 🔍 Dataset Statistics
- **Total Players Analyzed**: 14,345 outfield players
- **Hidden Gems Identified**: 1,577 players (11% of dataset)
- **Average Value Score**: 0.27%
- **Age Range**: 17-44 years (Avg: 25.79 years)
- **Overall Rating Range**: 47-91 (Avg: 66.17)

### 🌟 Top Hidden Gems Discovery

| Rank | Player | Position | Age | OVR | Performance Index | Value Score | Team |
|------|--------|----------|-----|-----|-------------------|-------------|------|
| 1 | Li Deming | RW | 20 | 50 | 60.65 | 21.30% | Shanghai Port FC |
| 2 | Thoi Singh | LW | 20 | 49 | 58.40 | 19.18% | NorthEast United |
| 3 | Eom Seung Min | RW | 21 | 52 | 62.70 | 20.58% | Jeonbuk Hyundai |
| 4 | Serge Ngoma | RM | 19 | 58 | 70.30 | 21.21% | Red Bulls |
| 5 | Kyrell Wilson | RM | 19 | 53 | 62.45 | 17.83% | Swansea City |

### 🏆 League Analysis

**Top Leagues for Hidden Gems:**

| League | Hidden Gems | Avg Value Score | Avg Age |
|--------|-------------|-----------------|---------|
| MLS | 100 | 8.57% | 22.31 |
| K League 1 | 79 | 8.69% | 22.52 |
| Sudamericana | 74 | 8.26% | 22.82 |
| EFL Championship | 71 | 8.61% | 22.00 |
| CSL | 58 | 8.89% | 24.81 |

**Key Insight**: MLS and K League 1 are treasure troves for undiscovered talent, with over 100 and 79 hidden gems respectively.

### 🌍 Nation Analysis

**Top Nations Producing Hidden Gems:**

| Nation | Hidden Gems Count | Avg Hidden Gem Index |
|--------|-------------------|---------------------|
| England | 132 | 9.83 |
| Germany | 92 | 9.33 |
| Korea Republic | 78 | 10.53 |
| Argentina | 76 | 8.55 |
| France | 65 | 9.08 |

### ⚽ Position-Specific Insights

#### Strikers (ST/CF/LF/RF)
**Performance Formula:**
```
Striker Index = Finishing (30%) + Positioning (25%) + Shot Power (15%) + 
                Pace (15%) + Composure (10%) + Dribbling (5%)
```
- **Top Gem**: Felipe Rodríguez-Gentile (Preston, Age 17, Value Score: 8.86%)
- **Average Hidden Gem Value**: 8.12%

#### Wingers (LW/RW/LM/RM)
**Performance Formula:**
```
Winger Index = Pace (30%) + Dribbling (25%) + Crossing (20%) + 
               Agility (15%) + Finishing (10%)
```
- **Top Gem**: Li Deming (Shanghai Port FC, Age 20, Value Score: 21.30%)
- **Average Hidden Gem Value**: 11.45%
- **Key Finding**: Wingers show the highest value scores, indicating this position has the most undervalued players

#### Midfielders (CM/CDM/CAM)
**Performance Formula:**
```
Midfielder Index = Passing (30%) + Vision (25%) + Ball Control (20%) + 
                   Stamina (15%) + Long Passing (10%)
```
- **Top Gem**: Adam Kardaš (Lechia Gdańsk, Age 18, Value Score: 12.45%)
- **Average Hidden Gem Value**: 8.67%

#### Defenders (CB/LB/RB/LWB/RWB)
**Performance Formula:**
```
Defender Index = Defense (30%) + Standing Tackle (25%) + Heading (15%) + 
                 Strength (15%) + Interceptions (10%) + Pace (5%)
```
- **Top Gem**: Riccardo Di Trolio (Coventry City, Age 19, Value Score: 9.52%)
- **Average Hidden Gem Value**: 7.89%

---

## 📊 Performance Metrics Explained

### Value Score
```python
Value Score = ((Position Performance Index - Overall Rating) / Overall Rating) × 100
```
- **Positive Score**: Player performs better than their rating suggests
- **>5%**: Undervalued player
- **>10%**: Hidden Gem territory
- **Negative Score**: Overvalued based on performance

### Hidden Gem Index
```python
Hidden Gem Index = (Value Score × 0.40) + 
                   ((30 - Age) × 0.30) + 
                   (League Bonus × 0.15) + 
                   ((79 - OVR) × 0.15)
```
**Weights:**
- 40% - Performance vs Rating
- 30% - Youth Factor (younger = better)
- 15% - League Tier (non-top 5 leagues get bonus)
- 15% - Room for Growth (lower OVR = more potential)

### Player Classification

| Category | Value Score Range | Description |
|----------|------------------|-------------|
| **Hidden Gem** | >10% | Elite value, highly underrated |
| **Undervalued** | 5-10% | Good value prospects |
| **Fairly Valued** | 0-5% | Rating matches performance |
| **Overvalued** | -5 to 0% | Slightly overrated |
| **Significantly Overvalued** | <-5% | Performance below rating |

**Distribution:**
- Fairly Valued: 6,624 players (46.2%)
- Overvalued: 3,641 players (25.4%)
- Significantly Overvalued: 2,220 players (15.5%)
- Undervalued: 1,400 players (9.8%)
- Hidden Gems: 460 players (3.2%)

---

## 🛠️ Technical Implementation

### Technologies Used
- **Python 3.8+**: Core analysis language
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **Matplotlib & Seaborn**: Data visualization
- **Scikit-learn**: Machine learning utilities (StandardScaler, KMeans, PCA)
- **Power BI**: Interactive dashboard creation

### Data Processing Pipeline

```
Raw CSV Data (17,737 players)
        ↓
Data Cleaning (Remove GK, handle missing values)
        ↓
Feature Engineering (Calculate indices, scores)
        ↓
Classification (Age categories, rating tiers, quadrants)
        ↓
Export Processed Data (6 CSV files)
        ↓
Power BI Dashboard (Interactive visualizations)
```

### Key Algorithms

#### 1. Position-Specific Performance Calculation
```python
def calculate_striker_index(row):    
    return (
        row['Finishing'] * 0.30 +
        row['Positioning'] * 0.25 +
        row['Shot Power'] * 0.15 +
        row['PAC'] * 0.15 +
        row['Composure'] * 0.10 +
        row['Dribbling'] * 0.05
    )
```

#### 2. Hidden Gem Detection
```python
hidden_gems = df_outfield[
    (df_outfield['Value_Score'] > 5) &      # Positive value
    (df_outfield['OVR'] <= 82) &            # Not already elite
    (df_outfield['Age'] <= 28)              # Reasonable age
]
```

#### 3. Quadrant Classification
```python
def classify_quadrant(row):
    if row['Value_Score'] >= 5 and row['Age'] <= 25:
        return '★ Prime Target'
    elif row['Value_Score'] >= 5 and row['Age'] > 25:
        return 'Short-term Value'
    elif row['Value_Score'] < 5 and row['Age'] <= 25:
        return 'Development Player'
    else:
        return 'Overvalued'
```

---

## 📁 Project Structure

```
fc25-hidden-gems/
│
├── data/
│   ├── raw/
│   │   └── male_players.csv              # Original dataset (17,737 players)
│   └── processed/
│       ├── players_with_metrics.csv      # Full dataset with calculated metrics
│       ├── hidden_gems_top50.csv         # Top 50 hidden gems
│       ├── position_analysis.csv         # Position-grouped statistics
│       ├── league_insights.csv           # League-level aggregations
│       ├── nation_insights.csv           # Nation-level aggregations
│       └── correlation_matrix.csv        # Attribute correlations
│
├── notebooks/
│   └── EDA(FC_25 dataset).ipynb         # Main analysis notebook
│
├── visualizations/
│   └── PowerBI_Dashboard.pbix            # Power BI dashboard file
│
├── requirements.txt                      # Python dependencies
├── README.md                             # This file
└── LICENSE                               # MIT License
```

---

## 🚀 Getting Started

### Prerequisites
```bash
Python 3.8 or higher
pip (Python package manager)
Power BI Desktop (for dashboard editing)
```

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/fc25-hidden-gems.git
cd fc25-hidden-gems
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Run the Jupyter Notebook**
```bash
jupyter notebook notebooks/EDA(FC_25\ dataset).ipynb
```

### Requirements.txt
```
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.5.0
seaborn>=0.12.0
scikit-learn>=1.1.0
jupyter>=1.0.0
```

---

## 📊 Power BI Dashboard Features

### Interactive Visualizations

1. **Overview Page**
   - Total players count
   - Average OVR distribution
   - Top leagues by hidden gems
   - Performance vs Rating scatter plot

2. **Hidden Gems Explorer**
   - Dynamic filtering by position, league, age
   - Value score histogram
   - Top 50 hidden gems table
   - Quadrant analysis (Age vs Value)

3. **Position Analysis**
   - Position-specific performance indices
   - Attribute radar charts
   - Top performers by position
   - Value score distribution

4. **League & Nation Insights**
   - Geographic distribution heatmap
   - League comparison metrics
   - Nation-level statistics
   - Hidden gem density by region

### Key Metrics (DAX Measures)

```dax
Total Players = COUNTROWS(players_with_metrics)

Avg Value Score = AVERAGE(players_with_metrics[Value_Score])

Hidden Gems Count = 
CALCULATE(
    COUNTROWS(players_with_metrics),
    players_with_metrics[Value_Score] > 5,
    players_with_metrics[OVR] <= 82,
    players_with_metrics[Age] <= 28
)

Selected Player = 
IF(
    ISFILTERED(players_with_metrics[Name]),
    SELECTEDVALUE(players_with_metrics[Name]),
    "Select a player from filters"
)
```

---

## 🎓 Use Cases

### For FIFA/FC Gamers
- **Career Mode**: Identify cheap, high-potential signings
- **Ultimate Team**: Find budget beasts for your squad
- **Scout Young Talent**: Build dynasty teams with future stars

### For Football Scouts
- **Real-world Application**: Discover undervalued players in emerging leagues
- **Market Inefficiencies**: Find talent overlooked by major clubs
- **Youth Development**: Identify promising young players

### For Data Analysts
- **Methodology Reference**: Position-specific performance modeling
- **Feature Engineering**: Custom index creation techniques
- **Sports Analytics**: Application of ML concepts to sports data

---

## 📊 Statistical Deep Dive

### Attribute Correlations with Overall Rating

| Attribute | Correlation with OVR |
|-----------|---------------------|
| Reactions | 0.87 |
| Composure | 0.84 |
| Ball Control | 0.82 |
| Short Passing | 0.79 |
| Vision | 0.76 |
| Dribbling | 0.74 |

**Key Insight**: Mental attributes (Reactions, Composure) correlate more strongly with OVR than physical attributes.

### Age Distribution of Hidden Gems

| Age Group | Count | Percentage | Avg Value Score |
|-----------|-------|------------|-----------------|
| 17-21 (Young Prospect) | 687 | 43.6% | 9.23% |
| 22-25 (Developing) | 624 | 39.6% | 8.87% |
| 26-28 (Prime) | 266 | 16.8% | 8.45% |

**Key Insight**: 83% of hidden gems are under 26, emphasizing the importance of youth in value assessment.

### Position Group Distribution

| Position Group | Player Count | Avg OVR | Hidden Gems | % Hidden Gems |
|----------------|--------------|---------|-------------|---------------|
| Midfielder | 4,892 | 66.32 | 538 | 11.0% |
| Defender | 4,214 | 65.87 | 447 | 10.6% |
| Striker | 2,876 | 66.45 | 318 | 11.1% |
| Winger | 2,363 | 66.18 | 274 | 11.6% |

---

## 🔮 Future Enhancements

### Planned Features
- [ ] Machine Learning model for OVR prediction
- [ ] Time-series analysis tracking player development
- [ ] Transfer market value integration
- [ ] Playstyle compatibility analysis
- [ ] Team chemistry optimization
- [ ] Real-time data updates via EA Sports API
- [ ] Mobile-responsive dashboard version
- [ ] Comparison tool for multiple players

### Advanced Analytics
- [ ] K-Means clustering for player archetypes
- [ ] PCA for dimensionality reduction
- [ ] Neural network for performance prediction
- [ ] Natural Language Processing for player reviews

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit your changes** (`git commit -m 'Add some AmazingFeature'`)
4. **Push to the branch** (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

### Contribution Ideas
- Add more position-specific indices
- Improve performance formulas
- Create additional visualizations
- Optimize data processing pipeline
- Add unit tests

---

## 📝 Methodology Notes

### Why These Weights?

The position-specific performance indices were carefully designed based on:
1. **Football Domain Knowledge**: Consulting with scouts and coaches
2. **Statistical Analysis**: Correlation studies between attributes and success metrics
3. **Game Mechanics**: Understanding FC 25's player rating system
4. **Iterative Testing**: Validating results against known player valuations

### Limitations

- **Subjective Weights**: Performance formulas use expert judgment
- **Static Analysis**: Does not account for player form or injuries
- **Game vs Reality**: FC 25 ratings may not perfectly reflect real-world ability
- **Missing Context**: Team tactics, chemistry, and playstyle preferences not included

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 FC 25 Hidden Gems Project

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 👤 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- LinkedIn: [Your LinkedIn](https://linkedin.com/in/yourprofile)
- Email: your.email@example.com

---

## 🙏 Acknowledgments

- **EA Sports** for FC 25 player data
- **Football Analytics Community** for methodology inspiration
- **Kaggle** for dataset hosting and community support
- **Power BI Community** for dashboard design patterns

---

## 📚 References

1. EA Sports FC 25 Official Ratings Database
2. "Moneyball: The Art of Winning an Unfair Game" - Michael Lewis
3. Sports Analytics Research Papers on Player Valuation
4. Power BI Documentation - Microsoft
5. Pandas Documentation - Data Analysis in Python

---

## 🔗 Related Projects

- [FIFA Player Analysis](https://github.com/example/fifa-analysis)
- [Football Transfer Market Prediction](https://github.com/example/transfer-prediction)
- [Player Performance Tracking](https://github.com/example/performance-tracking)

---

## 📧 Contact & Support

Have questions or suggestions? Feel free to:
- Open an [Issue](https://github.com/yourusername/fc25-hidden-gems/issues)
- Start a [Discussion](https://github.com/yourusername/fc25-hidden-gems/discussions)
- Email: your.email@example.com

---

## ⭐ Show Your Support

If you find this project helpful, please consider:
- Giving it a ⭐ on GitHub
- Sharing it with fellow FIFA/FC enthusiasts
- Contributing to the project
- Citing it in your research or projects

---

<div align="center">

**Made with ⚽ and 📊 for the football analytics community**

[Report Bug](https://github.com/yourusername/fc25-hidden-gems/issues) · [Request Feature](https://github.com/yourusername/fc25-hidden-gems/issues) · [View Dashboard](https://app.powerbi.com/view?r=eyJrIjoiM2FkNzQ5NzAtMjEyZS00MjkzLWI1YTYtOThhNmU5ZGVhOGM0IiwidCI6Ijk4OTk3ZjE3LWI5Y2MtNDVhNy05ZTkxLThhOWFhMTlkMTg5NiJ9)

</div>
