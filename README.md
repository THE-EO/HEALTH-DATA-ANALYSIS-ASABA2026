# HEALTH-DATA-ANALYSIS-ASABA2026
A foundational health data science project transforming raw screening data into reliable descriptive insights using Python.
# Descriptive and Exploratory Analysis of Blood Pressure and Random Blood Glucose Measurements Among Adults Screened at a Community Health Initiative in Asaba, Nigeria

## 1. Project Overview

This project analyzes health screening data collected during a community health awareness and basic health screening initiative conducted in Asaba, Delta State, Nigeria.

The project focuses on descriptive and exploratory analysis of **blood pressure** and **random blood glucose (RBS)** measurements among adults who participated in the screening.

The purpose of the analysis was to understand the structure and quality of the collected data, describe the distribution of the major health measurements, examine differences across screening locations and sex groups, and explore relationships between age, blood pressure, and random blood glucose.

The project demonstrates the application of data science methods to a real-world community health dataset while maintaining appropriate caution around interpretation and participant privacy.


## 2. Background and Context

Community health screening initiatives can generate useful data for understanding patterns in basic health measurements and identifying observations that may warrant further attention.

As part of a community health awareness initiative, participants were offered basic screening that included blood pressure and random blood glucose measurements.

The resulting dataset provides an opportunity to apply data analysis techniques to real-world health data rather than relying exclusively on simulated or classroom datasets.

This project therefore combines a health-science perspective with data science methods to examine the collected measurements systematically.

The analysis is exploratory and descriptive. It is **not intended to diagnose disease, establish clinical conditions, or estimate disease prevalence in the wider population**.



## 3. Research Question

### Main Research Question

**What patterns and relationships can be identified in the health characteristics of the screening participants, and what factors appear to be associated with differences in measured health outcomes?**

### Sub-questions

1. **Data Structure:**
   What does the dataset contain, and is it structured appropriately for analysis?

2. **Distribution:**
   How are the major health measurements distributed?

3. **Group Differences:**
   Do health measurements differ descriptively across relevant demographic or geographic groups?

4. **Relationships:**
   Are age, blood pressure, and random blood glucose associated with one another?

5. **Data Quality:**
   Are missing values, unusual observations, or measurement issues likely to affect the findings?

6. **Interpretation:**
   What can reasonably be concluded from the observed patterns, and what remains uncertain?


## 4. Dataset Description

The dataset contains **50 screening observations** and **9 recorded variables**, including a serial number used to identify rows.

The variables include participant characteristics, screening measurements, screening location, and date of screening.

### Main Variables

| Variable         | Description                            |
| ---------------- | -------------------------------------- |
| S/N              | Sequential identifier for each record  |
| Age              | Participant age as originally recorded |
| Sex              | Participant sex                        |
| FBS/RBS (mg/dL)  | Random blood glucose measurement       |
| Systolic (mmHg)  | Systolic blood pressure measurement    |
| Diastolic (mmHg) | Diastolic blood pressure measurement   |
| Date             | Date of screening                      |
| Location         | Screening location                     |

The original dataset also contained a participant-name field for operational use. **Personally identifying information is excluded from the public version of the dataset used for this portfolio project.**



## 5. Data Preparation and Quality Assessment

Several data-quality checks were performed before analysis.

### Dataset structure

The dataset contained:

* **50 observations**
* **9 recorded columns**
* Numerical and categorical variables appropriate for the planned analysis

### Missing values

The original dataset contained **no missing values** across the recorded variables.

However, the `Age` variable contained some entries recorded as `"Ad"` where a participant identified as an adult but did not provide a specific numerical age.

For numerical analysis, a separate `age_numeric` variable was created using numeric conversion. The `"Ad"` entries were represented as `NaN` in this analytical variable while the original `Age` column was retained unchanged.

This resulted in **47 numerical age observations and 3 non-numerical age entries**.

### Duplicate records

Duplicate-record checks were performed and no duplicate observations were identified.

### Unusual observations

Unusually high or low measurements were not automatically removed.

An unusual observation may represent genuine biological variation, a measurement issue, data-entry error, or a participant whose measurement warrants further clinical attention. Therefore, unusual observations were considered within the context of data quality and study limitations rather than being automatically treated as errors.


## 6. Methods and Analysis Approach

The analysis followed a structured exploratory workflow.

### 6.1 Descriptive Statistics

The major health measurements were summarized using:

* Mean
* Median
* Standard deviation
* Minimum
* Maximum
* 25th percentile
* 75th percentile
* Interquartile range (IQR)

The primary numerical variables analyzed were:

* Systolic blood pressure
* Diastolic blood pressure
* Random blood glucose

### 6.2 Distribution Analysis

Histograms and boxplots were used to examine:

* Distribution
* Central tendency
* Spread
* Potential skewness
* Unusual or extreme observations

### 6.3 Group Comparisons

Descriptive comparisons were performed across screening locations.

For each location, the analysis examined:

* Number of observations
* Mean systolic blood pressure
* Median systolic blood pressure
* Mean diastolic blood pressure
* Median diastolic blood pressure
* Mean random blood glucose
* Median random blood glucose

Boxplots were used to visualize differences in random blood glucose across screening locations.

Random blood glucose was also examined across sex groups.

These comparisons describe observed differences within this sample and do not establish statistical significance or causation.

### 6.4 Relationship Analysis

Scatterplots and correlation analysis were used to examine relationships between:

* Age and systolic blood pressure
* Age and diastolic blood pressure
* Age and random blood glucose
* Systolic and diastolic blood pressure
* Systolic blood pressure and random blood glucose
* Diastolic blood pressure and random blood glucose

Pearson correlation coefficients were used to summarize the direction and strength of linear association between numerical variables.

### 6.5 Pulse Pressure

Pulse pressure was calculated as:

**Pulse Pressure = Systolic Blood Pressure − Diastolic Blood Pressure**

This was used as an additional descriptive blood-pressure measure rather than as a diagnostic outcome.



## 7. Key Findings

### 7.1 Overall Distribution of Health Measurements

The overall descriptive statistics were:

| Measurement                  |   Mean | Median |    SD | Min |    Q1 |     Q3 | Max |   IQR |
| ---------------------------- | -----: | -----: | ----: | --: | ----: | -----: | --: | ----: |
| Systolic BP (mmHg)           | 119.78 |  119.0 | 15.75 |  94 | 111.0 | 128.75 | 179 | 17.75 |
| Diastolic BP (mmHg)          |  77.32 |   75.0 |  9.04 |  56 |  70.0 |   85.0 |  98 | 15.00 |
| Random blood glucose (mg/dL) |  97.69 |   91.4 | 19.96 |  72 |  84.3 | 102.45 | 167 | 18.15 |

The median values were lower than the means for all three major measurements, reflecting the influence of higher observations within the sample.

The highest recorded systolic blood pressure was **179 mmHg**, while the highest diastolic measurement was **98 mmHg**.

The highest recorded random blood glucose measurement was **167 mg/dL**.

These observations are noteworthy within the dataset but should not be interpreted as diagnostic findings from this analysis alone.



### 7.2 Differences Across Screening Locations

The number of observations and descriptive results by location were:

| Location    |  n | Mean Systolic | Median Systolic | Mean Diastolic | Median Diastolic | Mean RBS | Median RBS |
| ----------- | -: | ------------: | --------------: | -------------: | ---------------: | -------: | ---------: |
| DDPA Estate | 16 |        120.13 |           119.5 |          78.00 |             77.0 |    99.76 |       97.6 |
| Echolab     | 30 |        118.90 |           117.5 |          77.37 |             75.5 |    98.41 |       92.7 |
| Lifestream  |  4 |        125.00 |           124.5 |          74.25 |             71.5 |    84.00 |       84.0 |

The descriptive results show some differences between locations.

For example, Lifestream had the highest mean systolic blood pressure and the lowest mean random blood glucose. However, only **four participants** were represented in that location, making comparisons involving Lifestream particularly unstable and unsuitable for strong conclusions.

The differences therefore provide descriptive observations rather than evidence that location itself causes differences in health measurements.



### 7.3 Relationships Between Numerical Variables

The correlation matrix showed the following relationships:

| Variable Pair                       | Correlation |
| ----------------------------------- | ----------: |
| Age – Systolic BP                   |      -0.078 |
| Age – Diastolic BP                  |       0.066 |
| Age – Random Blood Glucose          |       0.163 |
| Systolic BP – Diastolic BP          |       0.535 |
| Systolic BP – Random Blood Glucose  |      -0.058 |
| Diastolic BP – Random Blood Glucose |       0.130 |

The strongest observed relationship was between **systolic and diastolic blood pressure (r = 0.535)**, indicating a moderate positive linear association in this dataset.

The relationship between age and random blood glucose was weakly positive (**r = 0.163**), while the relationships between age and the two blood-pressure measures were very weak.

The correlations between blood pressure and random blood glucose were also weak.

These results describe associations within the screened participants and should not be interpreted as evidence of causation.



## 8. Interpretation of the Findings

Overall, the analysis shows that the screening dataset contains measurable variation in blood pressure and random blood glucose across participants.

The two blood-pressure measurements showed a moderate positive relationship, while age had relatively weak linear associations with systolic blood pressure, diastolic blood pressure, and random blood glucose in this sample.

Descriptive differences were also observed across screening locations. However, the unequal number of participants between locations, particularly the small number at Lifestream, limits the strength of those comparisons.

The analysis therefore provides a useful description of the screened population while avoiding conclusions that cannot be supported by the study design.

Importantly, the measurements represent screening observations rather than repeated clinical measurements or confirmed diagnoses.



## 9. Limitations

Several limitations should be considered when interpreting the findings.

### Small sample size

The dataset contains only **50 participants**, which limits the statistical power and generalizability of the findings.

### Convenience screening sample

Participants were individuals who attended the community screening initiative. They were not selected using a population-based random sampling method.

Consequently, the sample may not represent the wider population of Asaba or Delta State.

### Single screening period

The measurements represent observations collected during the screening initiative. They do not provide longitudinal information about changes in individual health measurements over time.

### Non-numerical age entries

Three participants were recorded as `"Ad"` rather than providing a specific numerical age. These observations were retained in the original data but excluded from analyses requiring numerical age.

### Unequal location sizes

The number of participants differed substantially across locations, particularly for Lifestream, which had only four observations.

This limits the reliability of direct comparisons between locations.

### Screening measurements are not diagnoses

A single screening measurement cannot by itself establish a medical diagnosis.

The findings should therefore be interpreted as descriptive observations that may identify measurements requiring appropriate follow-up rather than as confirmed clinical conditions.

### Limited variables

The dataset does not contain additional variables such as height, weight, BMI, medical history, medication use, dietary information, physical activity, or other potential health-related factors.

Therefore, the analysis cannot assess the influence of these factors.



## 10. Ethical and Privacy Considerations

Because the dataset contains health-related measurements, participant privacy was treated as an important consideration.

The public version of the project should **not contain participant names or other directly identifying information**.

Participant names were excluded from the public dataset used for portfolio purposes.

The project uses a serial number to identify records within the analytical dataset rather than exposing participant identities.

The analysis is also intentionally descriptive and avoids assigning diagnoses to individual participants.

Any potentially noteworthy measurement should be understood as a screening observation requiring appropriate professional interpretation and, where necessary, clinical follow-up.

The project demonstrates the importance of separating data-analysis learning from unnecessary exposure of personally identifiable health information.



## 11. Conclusion

This project applied data science techniques to a real-world community health screening dataset containing blood pressure and random blood glucose measurements from 50 participants.

The analysis established that the dataset was sufficiently structured for exploratory analysis and contained no missing values or duplicate records in the original recorded variables.

Descriptive analysis showed variation in systolic blood pressure, diastolic blood pressure, and random blood glucose. Group comparisons identified descriptive differences across screening locations, while correlation analysis showed a moderate positive relationship between systolic and diastolic blood pressure and relatively weak relationships between age and the other major measurements.

The findings demonstrate how exploratory data analysis can be applied to community health data to identify patterns, assess data quality, and generate questions for further investigation.

However, the small convenience sample, unequal group sizes, single screening period, and limited health variables mean that the findings should not be generalized to the wider population or interpreted as diagnostic conclusions.

Overall, the project provides a practical example of combining **biochemistry/health knowledge with data science methods** to analyze real-world health data responsibly.



## 12. Tools Used

### Programming Language

* Python

### Data Analysis

* Pandas
* NumPy

### Statistical Analysis

* Descriptive statistics
* Pearson correlation
* Interquartile range (IQR)

### Data Visualization

* Matplotlib

### Development Environment

* Jupyter Notebook

### Data Storage

* Microsoft Excel during data collection/organization
* CSV for the anonymized analytical dataset

### Version Control and Portfolio

* GitHub

## 13. Repository Structure

```text
project-01-community-health-screening/
│
├── README.md
│
├── data/
│   └── screening_data.csv
│
├── documentation/
│   └── data_dictionary.csv
│
└── notebooks/
    └── analysis.ipynb
```

### File descriptions

**`README.md`**
Provides the project background, research questions, methods, findings, limitations, ethical considerations, and conclusion.

**`data/screening_data.csv`**
Contains the anonymized dataset used for the public analysis.

**`documentation/data_dictionary.csv`**
Provides definitions and descriptions of the variables in the dataset.

**`notebooks/analysis.ipynb`**
Contains the complete analysis, including data preparation, exploratory analysis, statistical calculations, visualizations, and interpretation.


## 14. Project Scope

This project was developed as an exploratory health-data-science portfolio project based on data collected during a community screening initiative.

The analysis demonstrates practical skills in:

* Data cleaning and preparation
* Data-quality assessment
* Descriptive statistics
* Exploratory data analysis
* Grouped analysis
* Correlation analysis
* Data visualization
* Health-data interpretation
* Ethical handling of sensitive data

The project does not attempt to replace clinical assessment or establish population-level epidemiological estimates.
