## Socio-Awareness Modeling and Predictive Analysis of COVID-19 Spread in Ohio Counties

---
**Project description:** 
-   Spearheaded an analytical project to assess the impact of socioeconomic factors and public awareness on the COVID-19 pandemic across Ohio counties.
-   Utilized advanced machine learning techniques, employing a Random Forest model to analyze over 140 variables, achieving an R² score of 0.95 and 89% prediction accuracy.
-   Conducted a multifaceted analysis incorporating health, societal, and economic data to explore the nuanced interplay between community behavior and pandemic trends.


### Overview

The analysis described in the report centers around the exploration and modeling of COVID-19 case spread within Ohio counties, linked to various awareness levels on different topics among the population. This analysis sought to understand the relationships between the pandemic's impact and the array of socioeconomic indicators available in the dataset.



### 1. Key components of the analysis included

Data Utilization: The study harnessed a rich dataset with numerous variables including COVID-19 case and death counts, social media engagement (topic awareness measured via Jaccard similarity), and socioeconomic factors like employment rates, educational attainment, and median earnings.
Modeling Technique: The primary analytical tool was a Random Forest algorithm, chosen for its robustness against noise and overfitting. This model was trained to predict COVID-19 cases, leveraging its ensemble learning nature.
Insightful Findings: The analysis uncovered that despite the pandemic, public interest heavily leaned towards non-health-related topics such as sports and entertainment. The geographical analysis provided insights into the distribution of awareness and its correlation with COVID-19 cases across counties.


<!-- 
```javascript
if (isAwesome){
  return true
}
``` -->

### 2. Method
- Topic Modeling Algorithms:
  - K-means Clustering
  - TF-IDF (Term Frequency-Inverse Document Frequency)
  - LDA (Latent Dirichlet Allocation) with Gensim


### 3. LDA Topic Modeling with Gensim
#### Performing Topic Modeling:

- Reference from Booking Platforms: Topics were initially based on ratings from platforms like Airbnb, Booking.com, Trivago, Trip.com, and Hotels.com.
- Model Construction:
  - A dictionary of unique words is created for the 'Bag of Words'.
  - The dictionary is vectorized by counting word frequencies.
  - Key parameters in Gensim's LDA model include:
    - num_topics: Determines the number of topics.
    - chunk size: Affects training speed and memory usage.
    - passes: Number of training iterations over the entire corpus.
    - iterations: Iterations per document for precision in topic assignments.
- Optimization Process:
Over 50 iterations fine-tuned parameters and refined the corpus.
Removed meaningless words to optimize topic modeling.
Aimed to achieve a high coherence level, indicating meaningful and consistent topics.



### 4. Presentation Thumbnail

<img src="images/HRA.JPG?raw=true"/>

### 5. Findings:

- Total reviews showed slight regional differences in priorities.
- Negative reviews were **significantly impacted by regions** 
- Positive reviews emphasized cleanliness and customer service.
- Cultural and regional differences influenced the emphasis on certain topics.


### 6. Negative Review Findings
Overall Trends: Negative reviews commonly focus on noise and comfort, meals, and the ease of the process. These factors vary significantly from the merged reviews, suggesting distinct preferences in different regions.

#### Regional Variations:
- America: Places the highest importance on value for money. Negative reviews often result from perceptions of poor value.
- Asia and Africa: Prioritize meals, indicating dissatisfaction with food leads to negative reviews.

#### Specific Concerns:
- Europe: Negative reviews often cite noise and comfort issues, such as poor soundproofing or uncomfortable furnishings.
- Operational Efficiency: An easy process is a common concern across regions, with inefficiencies leading to negative reviews.
- Value for Money: More emphasized in negative reviews than in merged reviews, showing a strong link between perceived value and dissatisfaction.


#### Sub-Regional Differences:
Differences in priorities exist within subregions. For example, Eastern Asians value customer service highly, differing from the broader Asian focus on meals. This is attributed to the region's reputation for excellent service, where failure to meet these expectations can result in negative reviews.

---
### Report Download

Full report is available here <a href="pdf/Hotel_Review_Analysis_Wonha Shin.pdf">Report Viewer</a>
