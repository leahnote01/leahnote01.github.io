## Cross-Cultural NLP Analysis of Luxury Hotel Reviews in Europe- LDA Topic Modeling 

---
**Project description:** 
-   Actively led a comprehensive NLP analysis project examining over 515,000 luxury hotel reviews to interpret complex customer latent patterns across diverse global region, utilizing Python and advanced Scikit-learn ML models (Gensim, LDA, clustering, NMF) expecting significant detailed analysis extracted insights.
-   Orchestrated advanced data preprocessing and optimization techniques, along with thorough comparative analyses using R and Tableau expect to contribute to the company’s market positioning critical strategic decisions.

<br>

### Overview

This project aims to analyze hotel reviews to uncover interesting patterns. The motivation stems from the experience of travelers and foodies who often rely on reviews and ratings but sometimes find them misleading. The goal is to look beyond ratings, focusing on review content, priority metrics for luxury hotel guests, and differences in perspectives based on nationality.
<br>

### 1. Dataset and Preprocessing
- Data Source: Kaggle ("515K Hotel Reviews Data in Europe" from Booking.com)
- Dataset Details: 515K rows from 1493 hotels across various European countries
- Preprocessing involved cleansing (space trimming, missing data removal), discretization (concept hierarchy), and structuring analysis based on regional classifications aligned with Google Maps.

<!-- 
```javascript
if (isAwesome){
  return true
}
``` -->
<br>

### 2. Method
- Topic Modeling Algorithms:
  - K-means Clustering
  - TF-IDF (Term Frequency-Inverse Document Frequency)
  - LDA (Latent Dirichlet Allocation) with Gensim

<br>

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


<br>

### 4. Presentation Thumbnail

<img src="images/HRA.JPG?raw=true"/>
Full slides is available here <a href="pdf/Hotel_Review_Analysis_Slides.pptx.pdf"> PDF Viewer</a>

<br>


### 5. Findings:

- Total reviews showed slight regional differences in priorities.
- Negative reviews were **significantly impacted by regions** 
- Positive reviews emphasized cleanliness and customer service.
- Cultural and regional differences influenced the emphasis on certain topics.
<br>

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
