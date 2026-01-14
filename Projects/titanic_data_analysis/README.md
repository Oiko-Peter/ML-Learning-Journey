# Titanic Data Analysis

## 📋 Project Overview
Exploratory data analysis and machine learning modeling on the Titanic dataset to predict passenger survival. This is Day 13 project of my 9-month ML Learning Journey.

**Goal:** Transform from Data Analyst to AI Engineer by building a comprehensive ML portfolio.

## 🎯 Objectives
- Perform thorough exploratory data analysis (EDA)
- Understand factors affecting passenger survival
- Engineer relevant features from raw data
- Build and evaluate predictive models
- Document insights and methodology

## 📊 Dataset
The data is from the [Kaggle Titanic Competition](https://www.kaggle.com/c/titanic/data)

### Dataset Information:
- **Train set:** 891 passengers with survival labels
- **Test set:** 418 passengers without labels
- **Features:** 12 columns including demographics, ticket class, and fare

### To Reproduce This Analysis:
1. Download the following files from Kaggle:
   - `train.csv`
   - `test.csv`
   - `gender_submission.csv`
2. Place them in the `data/` directory

## 📁 Project Structure
```
Titanic_Data_Analysis/
├── data/                           # Raw data files (not tracked in git)
│   ├── train.csv
│   ├── test.csv
│   └── gender_submission.csv
│
├── notebooks/                      # Jupyter notebooks for analysis
│   ├── 01_data_exploration.ipynb   # Initial EDA and statistics
│   ├── 02_data_visualization.ipynb 
│   ├── 03_feature_engineering.ipynb
│   └── 04_modeling.ipynb           
│
├── README.md                       # This file
└── KEY_FINDINGS.md                 # Detailed observations and insights
```

## 🔧 Tools & Libraries Used
- **Python 3.x**
- **pandas** - Data manipulation and analysis
- **numpy** - Numerical computations
- **matplotlib** - Data visualization
- **seaborn** - Statistical visualizations
- **scikit-learn** - Machine learning (coming soon)

## 🔍 Key Findings Summary
For detailed analysis, see [KEY_FINDINGS.md](KEY_FINDINGS.md)

**Quick Highlights:**
- Overall survival rate: 38.38%
- Gender was the strongest predictor (74% female vs 19% male survival)
- Passenger class significantly impacted survival (63% 1st class vs 24% 3rd class)
- Significant missing data in Cabin (77%) and Age (20%) columns

## 🚀 How to Run
1. **Clone the repository**
```bash
   git clone <your-repo-url>
   cd ML-Learning-Journey/Projects/Titanic_Data_Analysis
```

2. **Set up environment** (if not already done)
```bash
   conda activate ml_env
```

3. **Install required packages** (if needed)
```bash
   pip install pandas numpy matplotlib seaborn jupyter
```

4. **Download the data** from Kaggle and place in `data/` folder

5. **Launch Jupyter and open notebooks**
```bash
   jupyter notebook
```

6. **Run notebooks in order:**
   - Start with `01_data_exploration.ipynb`
   - 

## 📈 Project Status
- [x] Initial data exploration
- [x] Statistical analysis
- [x] Missing value identification
- [ ] Data visualization
- [ ] Feature engineering
- [ ] Model building
- [ ] Model evaluation
- [ ] Final predictions

## 👤 Author
**Nyams** - Data Analyst transitioning to AI Engineer
- Location: Nairobi, Kenya
- Focus: Machine Learning with Healthcare AI specialization

## 📝 License
This project is part of a personal learning journey. Data is from Kaggle's Titanic Competition.