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

### 6. Evaluation & Monitoring
- Validation: Applied the classifier to labeled test tweets for precision checks
- Latency: Streamed batches processed every 60 seconds
- Accuracy: ~92% on small-scale test set using pre-finetuned model
- Robustness: Fault-tolerant write and checkpointing supported via Delta


<br>

### 7. Visualization & Insights
- Created interactive plots of sentiment proportions over time
- Filtered by language, hour, and keyword to visualize public reactions
- Notable trends aligned with world events (e.g., spikes in negative sentiment)

<br>

### 8. Challenges
- Transformer Inference Overhead:
  Mitigated by batching and using lightweight model variant
- Stateful Stream Fault Tolerance:
  Ensured idempotent writes using Delta Lake + Checkpointing
- Real-time UDF Performance:
  Limited scalability when using large language models
- Model Registration Sync:
  Ensured proper MLflow stage transitions from "Staging" to "Production"


<br>

### 9. Conclusion & Future Work
This project successfully demonstrated a fully functional, end-to-end real-time sentiment analysis pipeline using Spark and Hugging Face transformers. It showcases the feasibility of integrating NLP models into streaming systems at scale.

- Future Directions:
  - Use distributed inference (e.g., ONNX or model parallelism)
  - Add multilingual support and translate non-English tweets
  - Integrate drift detection via MLflow model monitoring



---

### 📎 Full Code Access
Full code snippet is available here:
<a href="https://github.com/leahnote01/dscc402/blob/main/final_project/Starter%20Streaming%20Tweet%20Sentiment%20-%20Spring%202024%20Final%20Project.ipynb" target="_blank">👉 Let’s go to my GitHub!</a>
