# 100m Sprint Performance Analysis

## Project Overview

This project analyzes the optimal characteristics that make world-class sprinters fast in the 100-meter dash.  
Using data from Olympic athletes and World Athletics Association records, we investigate how demographic and physical traits correlate with sprint performance.  

Through exploratory data analysis (EDA) and predictive modeling, I examined how features such as height, weight, and age impact sprint time.  
The analysis includes data cleaning, outlier handling, and regression modeling to identify which variables most strongly influence performance outcomes.

### Research Questions

1. **What is the peak performance age for sprinters in the 100 meters?**
2. **What is the optimal height for sprinters to perform best in the 100 meters?**
3. **What is the optimal weight for sprinters to perform best in the 100 meters?**
4. **Can we predict sprint times based on physical characteristics?**

## Datasets

This project uses two primary datasets:

1. **Olympic Athletes Dataset** ([Kaggle](https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results))
   - Contains 120 years of Olympic history with athlete biometric data
   - Features: Name, Age, Sex, Height, Weight, Year, Event

2. **World Athletics Sprint Records** ([GitHub](https://github.com/kgmuchiri/WAA-Scraping/blob/main/datasets/split_by_type/sprints.csv))
   - Performance data from World Athletics Association
   - Features: Athlete name, Season, Mark (sprint time), Discipline

The datasets were merged on athlete name and year, filtered for 100m events only.

## Methodology

### Data Processing
- Filtered both datasets to include only 100-meter race data
- Merged datasets on athlete name and year
- Removed missing data and normalized name formats
- Applied IQR (Interquartile Range) method to remove outliers

### Statistical Analysis
- **Hypothesis Testing**: Used t-tests to verify optimal values for age, height, and weight
- **Significance Level**: α = 0.05
- Compared performance between athletes at optimal values vs. those above/below

### Machine Learning Models

1. **Linear Regression**
   - Predicted sprint times based on age, height, and weight
   - Evaluated model performance using R² score and MSE

2. **Decision Tree Regression**
   - Built separate models for male and female athletes
   - Used GridSearchCV for hyperparameter tuning
   - Evaluated with R² and MSE metrics

3. **Decision Tree Classification**
   - Classified athletes as "Elite" vs. "Competitive" based on performance thresholds
   - Male threshold: 10.00 seconds
   - Female threshold: 11.07 seconds
   - Visualized decision boundaries

## Key Findings

### Optimal Characteristics (Validated with Statistical Significance)

**Male Athletes:**
- **Peak Age**: 22 years old (p < 0.05)
- **Optimal Height**: 183 cm (6'0")
- **Optimal Weight**: 79 kg (174 lbs)

**Female Athletes:**
- **Peak Age**: 32 years old (p < 0.05)
- **Optimal Height**: 168 cm (5'6")
- **Optimal Weight**: 59 kg (130 lbs)


## Technologies Used

- **Python 3.x**
- **Libraries:**
  - `pandas`: Data manipulation and analysis
  - `numpy`: Numerical computing
  - `scikit-learn`: Machine learning models (GridSearchCV for hyperparameter tuning)
  - `matplotlib`: Data visualization
  - `seaborn`: Statistical data visualization
  - `scipy`: Statistical testing (t-tests, p-values)

## How to Run

### Prerequisites

pip install pandas numpy scikit-learn matplotlib seaborn scipy

### Running the Notebook

1. Clone this repository:
   git clone https://github.com/YifanJ6/100m-sprint-analysis.git
   cd 100m-sprint-analysis

2. Download the datasets:
   - [Olympic Athletes Dataset](https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results)
   - [Sprint Performance Dataset](https://github.com/kgmuchiri/WAA-Scraping/blob/main/datasets/split_by_type/sprints.csv)

3. Update the file paths in the notebook to point to your dataset locations

4. Open and run the Jupyter notebook:
   jupyter notebook CSE163_Final_Project.ipynb


## Project Structure

```
100m-sprint-performance-analysis/
├── CSE163_Final_Project.ipynb # Main analysis notebook
├── athlete_events.csv # Dataset of Olympic athletes
├── sprints.csv # Sprint performance dataset
├── README.md # Project documentation
├── .Rhistory # R environment history (can ignore)
└── .DS_Store # System file (can ignore)
```

## Limitations

- The model is trained on Olympic-level athletes, so predictions may not generalize well to amateur or youth athletes
- Dataset does not capture changes in athlete characteristics over time (e.g., weight fluctuations during a career)
- Other important factors like training regimen, technique, and genetics are not included in the analysis

## Authors

- **Yifan Ji** - [GitHub](https://github.com/YifanJ6) | [LinkedIn](https://www.linkedin.com/in/yifan-ji-a225802a0)
- **Johnny Nguyen** - Project Collaborator

*University of Washington - CSE 163: Intermediate Data Programming*

## License

This project is created for educational purposes as part of CSE 163 coursework.

## Acknowledgments

- Data sources: Kaggle and World Athletics Association
- Course: CSE 163 - Intermediate Data Programming
- Thanks to all contributors and dataset maintainers

**Note**: This project analyzes historical data and optimal characteristics. Individual performance varies greatly based on many factors beyond physical attributes.
