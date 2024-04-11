## Socio-Awareness Modeling and Predictive Analysis of COVID-19 Spread in Ohio Counties

---
<img src="images/OHIO.JPG?raw=true"/>


**Project description:** 
-   Spearheaded an analytical project to assess the impact of socioeconomic factors and public awareness on the COVID-19 pandemic across Ohio counties.
-   Utilized advanced machine learning techniques, employing a Random Forest model to analyze over 140 variables, achieving **an R² score of 0.95 and 89% prediction accuracy**.
-   Conducted a multifaceted analysis incorporating health, societal, and economic data to explore the nuanced interplay between community behavior and pandemic trends.
<br>
<br>

### Overview

The analysis described in the report centers around the exploration and modeling of COVID-19 case spread within Ohio counties, linked to various awareness levels on different topics among the population. This analysis sought to understand the relationships between the pandemic's impact and the array of socioeconomic indicators available in the dataset.

<br>

### 1. Key components of the analysis included

- Data Utilization: The study harnessed a rich dataset with numerous variables including COVID-19 case and death counts, social media engagement (topic awareness measured via Jaccard similarity), and socioeconomic factors like employment rates, educational attainment, and median earnings.
- Modeling Technique: The primary analytical tool was a Random Forest algorithm, chosen for its robustness against noise and overfitting. This model was trained to predict COVID-19 cases, leveraging its ensemble learning nature.
- Insightful Findings: The analysis uncovered that despite the pandemic, public interest heavily leaned towards non-health-related topics such as sports and entertainment. The geographical analysis provided insights into the distribution of awareness and its correlation with COVID-19 cases across counties.

<br>

### 2. Method
- Random Forest
  - tuning with multiple hyperparameters

<br>

### 3. Random Forest 
- Hyperparameter tuning:
  - A loop iterates over a range of values for `n_estimators` in the Random Forest Classifier to find the best performing model based on accuracy and R-squared metrics.
  - The tuning process involves training the model with different numbers of trees `n_estimators` and observing the impact on performance metrics.
  - Results are visualized using matplotlib plots, showing how different values of `n_estimators` affect the model's accuracy and R-squared score, helping to identify the optimal model configuration.

<br>

### 4. The Analysis of Results:

- The analysis using a Random Forest model demonstrated high effectiveness, with an R² score of 0.955 and 89% accuracy, indicating reliable predictive capability for COVID-19 case distribution across Ohio counties.
- The study found that non-health topics like sports and entertainment dominated public interest, overshadowing health-related information during the pandemic.
- Geographical analysis highlighted variations in COVID-19 impact, with certain counties facing higher cases or deaths per capita.
- Temporal trends in topic awareness were dynamic, fluctuating with external events. Although the model was robust, future improvements could include integrating additional relevant features to enhance accuracy and insight depth.


---
### Report Download

Full report is available here <a href="pdf/COVID-19_Ohio_Lab_Report.pdf">Report Viewer</a>
