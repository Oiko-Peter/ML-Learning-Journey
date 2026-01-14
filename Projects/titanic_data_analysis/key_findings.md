# Key Findings - Titanic Dataset Analysis

---

## 📊 DATASET OVERVIEW

### Structure
- **Total Records:** 891 passengers
- **Total Features:** 12 columns
- **Target Variable:** Survived (0 = No, 1 = Yes)

### Features List
| Feature | Type | Description |
|---------|------|-------------|
| PassengerId | int64 | Unique identifier |
| Survived | int64 | Survival (0 = No, 1 = Yes) |
| Pclass | int64 | Ticket class (1 = 1st, 2 = 2nd, 3 = 3rd) |
| Name | object | Passenger name |
| Sex | object | Gender (male/female) |
| Age | float64 | Age in years |
| SibSp | int64 | # of siblings/spouses aboard |
| Parch | int64 | # of parents/children aboard |
| Ticket | object | Ticket number |
| Fare | float64 | Passenger fare |
| Cabin | object | Cabin number |
| Embarked | object | Port of embarkation (C/Q/S) |

---

## 🔍 DATA QUALITY ASSESSMENT

### Missing Values Analysis
| Column | Missing Count | Percentage | Severity |
|--------|---------------|------------|----------|
| Cabin | 687 | 77.10% | ❌ Critical |
| Age | 177 | 19.87% | ⚠️ Significant |
| Embarked | 2 | 0.22% | ✅ Minimal |
| Others | 0 | 0.00% | ✅ Complete |

**Key Issues:**
1. **Cabin:** 77% missing - likely unusable without significant feature engineering
2. **Age:** 20% missing - will require imputation for modeling
3. **Embarked:** Only 2 missing - easy to handle with mode imputation

---

## 📈 SURVIVAL ANALYSIS

### Overall Survival Rate
- **Survived:** 342 passengers (38.38%)
- **Died:** 549 passengers (61.62%)
- **Key Insight:** Nearly 2 out of 3 passengers perished in the disaster

---

## 👥 GENDER PATTERNS (STRONGEST PREDICTOR)

### Distribution
- **Male:** 577 passengers (64.8%)
- **Female:** 314 passengers (35.2%)

### Survival by Gender
| Gender | Total | Survived | Died | Survival Rate |
|--------|-------|----------|------|---------------|
| Female | 314 | 233 | 81 | **74.20%** |
| Male | 577 | 109 | 468 | **18.89%** |

### Critical Insights
✅ Women were **~4x more likely** to survive than men  
✅ "Women and children first" evacuation protocol clearly evident  
✅ Gender is likely the **strongest predictor** of survival  
✅ 233 out of 342 survivors were female (68% of all survivors)

---

## 🎫 PASSENGER CLASS PATTERNS (SECOND STRONGEST PREDICTOR)

### Distribution
- **1st Class:** 216 passengers (24.2%)
- **2nd Class:** 184 passengers (20.7%)
- **3rd Class:** 491 passengers (55.1%)

### Survival by Class
| Class | Total | Survived | Died | Survival Rate |
|-------|-------|----------|------|---------------|
| 1st | 216 | 136 | 80 | **62.96%** |
| 2nd | 184 | 87 | 97 | **47.28%** |
| 3rd | 491 | 119 | 372 | **24.24%** |

### Critical Insights
✅ 1st Class passengers were **~2.6x more likely** to survive than 3rd Class  
✅ Clear socioeconomic disparity in survival outcomes  
✅ Over half the passengers were in 3rd class but had the **lowest survival rate**  
✅ Possible factors: cabin location (deck level), priority in evacuation, proximity to lifeboats

---

## ⚓ EMBARKATION PORT PATTERNS

### Distribution
- **Southampton (S):** 644 passengers (72.3%)
- **Cherbourg (C):** 168 passengers (18.9%)
- **Queenstown (Q):** 77 passengers (8.6%)

### Survival by Port
| Port | Total | Survived | Died | Survival Rate |
|------|-------|----------|------|---------------|
| Cherbourg (C) | 168 | 93 | 75 | **55.36%** |
| Queenstown (Q) | 77 | 30 | 47 | **38.96%** |
| Southampton (S) | 644 | 217 | 427 | **33.70%** |

### Observations
- Cherbourg passengers had the **highest survival rate** (may correlate with class)
- Southampton had majority of passengers but **lowest survival rate**
- **Hypothesis:** Embarkation port may be a proxy for passenger class/wealth

---

## 👶 AGE DEMOGRAPHICS

### Statistics
- **Youngest:** 0.42 years (5-month-old infant)
- **Oldest:** 80.00 years
- **Mean Age:** 29.70 years
- **Median Age:** 28.00 years
- **Missing:** 177 passengers (19.87%)

### Insights
- Relatively **young passenger population** (median 28)
- Wide age range suggests diverse demographics
- Age distribution appears roughly normal
- Missing age data will require strategic imputation

---

## 🎯 KEY FINDINGS SUMMARY

### Top 3 Survival Factors (in order of importance)
1. **Gender:** Women had 74% survival vs 19% for men (3.9x difference)
2. **Passenger Class:** 1st class 63% vs 3rd class 24% (2.6x difference)
3. **Embarkation Port:** Cherbourg 55% vs Southampton 34% (1.6x difference)

### Data Quality Concerns
1. Cabin column is 77% missing - likely need to drop or extract deck info only
2. Age column is 20% missing - will need imputation
3. Some features (Ticket, Name) need feature engineering to be useful

### Patterns Identified
- Clear gender bias in survival (women prioritized)
- Socioeconomic status matters (class affects survival)
- Possible interaction effects between gender and class worth exploring
- Family size features (SibSp, Parch) haven't been fully analyzed yet

---

## 🔬 HYPOTHESES TO TEST

### High Priority
1. Are 1st class women more likely to survive than 3rd class women?
2. Did children have higher survival rates regardless of class?
3. Does traveling with family increase or decrease survival?

### Medium Priority
4. Is there an optimal age range for survival?
5. Does fare (as a proxy for wealth) predict survival beyond class?
6. Can we extract deck information from Cabin despite missing data?

### Low Priority
7. Does ticket number contain useful information?
8. Can we extract titles from Name (Mr., Mrs., Miss., Master.)?
9. Are there patterns in passenger groups traveling together?

---

## 📋 NEXT STEPS

### Phase 2: Data Visualization (Next Notebook)
- [ ] Create survival rate visualizations by gender, class, age
- [ ] Plot missing data patterns
- [ ] Visualize distributions of continuous variables
- [ ] Create correlation heatmap
- [ ] Build interaction plots (Gender × Class)

### Phase 3: Feature Engineering
- [ ] Handle missing Age values (imputation strategy)
- [ ] Extract Title from Name (Mr., Mrs., Miss., Master., etc.)
- [ ] Create FamilySize feature (SibSp + Parch + 1)
- [ ] Create IsAlone binary feature
- [ ] Extract Deck from Cabin (first letter)
- [ ] Bin Age into categories (Child, Teen, Adult, Senior)
- [ ] Encode categorical variables

### Phase 4: Modeling
- [ ] Split data into train/validation sets
- [ ] Baseline model (Logistic Regression)
- [ ] Try Random Forest, XGBoost
- [ ] Evaluate model performance
- [ ] Feature importance analysis
- [ ] Generate predictions for test set

---

## 💡 INSIGHTS FOR MODELING

### Expected Strong Features
1. Sex (Gender) - Strongest predictor
2. Pclass (Ticket Class) - Second strongest
3. Age - Likely important (children prioritized)
4. FamilySize (engineered) - May reveal patterns
5. Title (engineered from Name) - Social status indicator

### Features Requiring Work
- **Age:** Impute missing values
- **Cabin:** Extract deck or drop
- **Embarked:** Fill 2 missing values
- **Name:** Extract title
- **SibSp/Parch:** Combine into FamilySize

### Features to Possibly Drop
- PassengerId (just an index)
- Ticket (too irregular)
- Name (after extracting title)
- Cabin (if can't extract useful info)

---

*This document will be updated as the analysis progresses through visualization, feature engineering, and modeling phases.*