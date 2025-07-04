## E-Cigarette Perception Capstone Project

---
**Project description:** 
- Conducted a multilingual NLP project analyzing over 51,000 English and 7,000 Spanish tweets (from an original pool of 1.1M and 34K respectively) to uncover cultural and linguistic differences in public e-cigarette discourse on Twitter/X.
- Led key components including full-text crawling, NLP preprocessing, manual labeling, fine-tuning transformer models (Bertweet, Twitter Twin BERT Large), and multilingual topic modeling using Sentence Transformers, UMAP, and K-means.
- Revealed critical thematic and attitudinal differences between language groups, guiding culturally sensitive public health messaging strategies.
<br>

### Overview

This project aimed to analyze public perceptions of e-cigarettes across English and Spanish tweets to support inclusive, culturally informed public health campaigns. Motivated by the lack of multilingual research in this domain, the project used advanced NLP tools to uncover thematic trends and attitudinal differences between English- and Spanish-speaking communities.

<br>

### 1. Dataset and Preprocessing
- Data Source: Tweets related to e-cigarettes collected via keyword filtering by a third-party provider
- Initial Dataset Sizes:
  - ~1.1 million English tweets
  - ~34,000 Spanish tweets
- Final Preprocessed Dataset:
  - 51,000 English tweets
  - 7,000 Spanish tweets
- Preprocessing Pipeline:
  - Deduplication and removal of retweets
  - Full-text crawling (sampled 100K English tweets)
  - Text normalization: lowercasing, stop word removal, lemmatization, emoji/special character removal
<br>

### 2. Model Training and Fine-Tuning
- Labeling Tasks:
  - Relevance
  - Commercial vs. Non-commercial intent
  - Attitude classification (positive, neutral, negative)

- Manual Labeling: 1,000 tweets labeled through iterative refinement and group consensus

- Transformer Models Used:
  - Relevance: Bertweet (96% accuracy, F1 0.85), Twitter Twin BERT Large (94%)
  - Commercial Intent: Bertweet (93% accuracy, F1 0.87)
  - Attitude: Bert Rate Model (92% accuracy, F1 0.89)

<br>

### 3. Topic Modeling Framework
- Embedding + Clustering Pipeline:
  - Sentence-BERT Embeddings
  - UMAP for dimensionality reduction
  - K-Means for topic grouping
- Models Compared: LDA, TF-IDF, BERT Topic
- Final Selection: BERT Topic for best balance between coherence, domain relevance, and interpretability
- Topic Naming: Refined using OpenAI-based LLMs with 100+ iterations per theme


<br>

### 4. Major Findings
- Cross-Linguistic Themes
  - English Tweets: Focused on regulation, school-related vaping, and public health risks.
  - Spanish Tweets: Emphasized social lifestyle, recreational habits, and cultural context.
  - Translation Evaluation: Minimal loss in sentiment polarity; however, key cultural idioms and slang were diluted or altered.

- Sentiment vs. Attitude
  - Sentiment (VADER): Majority of tweets labeled as neutral.
  - Attitude (Fine-tuned Model): Revealed more polarized opinions (24.6% positive, 41.2% negative, 34.2% neutral), uncovering what traditional sentiment tools often miss.

- Translation vs. Original Spanish
  - Original Spanish tweets emphasized addiction, cravings, and personal habits.
  - Translations introduced themes like gift-giving and product preferences not found in the original.
  - Demonstrated how translation may shift thematic interpretations and miss cultural depth.

<br>

### 5. Challenges and Limitations
- **Ground Truth Labeling Subjectivity**: Creating labeled data for classification tasks (e.g., attitude and commercial relevance) involved manual annotation and group consensus, making the labels inherently subjective. Especially in cross-cultural contexts, definitions of "positive," "neutral," and "negative" vary and may affect reproducibility and downstream model interpretation.
- **Preserving Cultural Nuance During Translation**: Machine translation often failed to retain idiomatic expressions, slang, emoji usage, and cultural references in Spanish tweets, leading to loss of contextual richness and thematic accuracy.
- **Disparity in Dataset Sizes**: The English dataset significantly outweighed the Spanish dataset in volume, creating imbalances that affected cross-linguistic comparability and interpretability.
- **Cross-Language Topic Modeling**: Structural and syntactic differences between English and Spanish introduced challenges in achieving consistent and unbiased topic clusters, limiting model performance and coherence across languages.
- **Demographic Bias**: Social media users, particularly those active on Twitter, are not representative of the general population. Differences in age, socioeconomic status, and language fluency limit the generalizability of findings to broader public health contexts.

<br>

### 6. Future Work

- Enhance multilingual topic modeling frameworks for improved cultural fidelity.
- Construct balanced datasets across languages to ensure unbiased comparison.
- Conduct temporal analysis to study perception shifts after policy changes or public health campaigns.

<br>

---

### Report Download

Full report is available here <a href="pdf/Hotel_Review_Analysis_Wonha Shin.pdf">Report Viewer</a>
