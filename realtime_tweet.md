## Real-Time Tweet Sentiment Analysis Pipeline

---
**Project description:** 
Designed and deployed a scalable real-time streaming pipeline for classifying tweet sentiments using transformer-based models in Spark Structured Streaming. Leveraged the power of Delta Lake for incremental data ingestion and storage, with MLflow for experiment tracking and model registry. Built a robust Bronze–Silver–Gold architecture to support low-latency classification of tweet streams, enabling visualization of evolving sentiment patterns in real-time.
<br>

### 1. Motivation
The exponential growth of user-generated content on platforms like Twitter presents a unique opportunity to understand public sentiment on a global scale. However, streaming this data in real-time and analyzing it at scale poses multiple engineering and ML challenges. This project aimed to bridge that gap using **distributed streaming and model inference pipelines with Spark.**

<br>

### 2. Dataset & Streaming Architecture
- Input Source: Preloaded tweet stream containing JSON files
- Format: Simulated Twitter JSON feed (s3a://voc-75-databricks-data/voc_volume/)
- Architecture:
  - Bronze Table: Raw ingestion (semi-structured)
  - Silver Table: Cleaned and enriched with timestamp and language
  - Gold Table: Includes sentiment predictions
<br>

### 3. Tools & Technologies
- Streaming Engine: Apache Spark (Structured Streaming)
- Storage Format: Delta Lake (Bronze–Silver–Gold layers)
- ML Framework: Hugging Face Transformers (cardiffnlp/twitter-roberta-base-sentiment)
- Model Management: MLflow (Logging, Registry, Serving)
- Infrastructure: Databricks Notebook
- Visualization: Real-time dashboard using Delta Tables


<br>

### 4. Data Preprocessing & Pipeline Construction
- Step 1: Ingest Raw Tweet Stream
  - Structured Streaming read from S3 to Bronze Delta Table
- Step 2: Clean & Parse
  - Extracted relevant fields: full_text, timestamp, lang, user_id
  - Removed nulls, deduplicated tweet IDs
  - Saved to Silver Delta Table
- Step 3: Sentiment Classification
  - Applied fine-tuned transformer via UDF
  - Inferred sentiment labels: positive, neutral, negative
  - Stored predictions in Gold Table


<br>

### 5. Model Development
- Model Used: cardiffnlp/twitter-roberta-base-sentiment from Hugging Face
- Wrapper Function: Python UDF within Spark
- MLflow Integration:
  - Logged model, accuracy, F1 score
  - Registered and served model for inference

<br>

### 6. Future Work

- Enhance multilingual topic modeling frameworks for improved cultural fidelity.
- Construct balanced datasets across languages to ensure unbiased comparison.
- Conduct temporal analysis to study perception shifts after policy changes or public health campaigns.

<br>

---

### Report Download

Full report is available here <a href="pdf/Hotel_Review_Analysis_Wonha Shin.pdf">Report Viewer</a>
