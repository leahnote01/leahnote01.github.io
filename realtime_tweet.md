## 🧠 Real-Time Tweet Sentiment Analysis Pipeline  
**Databricks | PySpark Structured Streaming | Delta Lake | Hugging Face | MLflow**

---

### 🚀 Overview  
Designed and deployed a **real-time streaming pipeline** to classify tweet sentiments at scale using **transformer-based NLP models** within **Apache Spark Structured Streaming**.  
The system processes millions of tweets with **low latency**, leveraging a **Delta Lake multi-layer architecture (Bronze → Silver → Gold)** and **MLflow** for tracking, model registry, and deployment.

> **Goal:** Bridge the gap between scalable data engineering and NLP by integrating distributed streaming with real-time model inference.

---

### 🧩 Architecture  
**Data Flow:**  
`Twitter Stream (JSON)` → `Bronze (Raw)` → `Silver (Cleaned)` → `Gold (Predicted)`  

**Components:**  
- **Streaming Engine:** Apache Spark Structured Streaming  
- **Storage:** Delta Lake (ACID, checkpointing, schema evolution)  
- **Model:** Hugging Face `cardiffnlp/twitter-roberta-base-sentiment`  
- **Model Management:** MLflow (tracking, registry, serving)  
- **Infrastructure:** Databricks on AWS (S3 as source + Delta for persistence)  
- **Visualization:** Real-time sentiment dashboards built from Gold table  

---

### ⚙️ Pipeline Workflow  

1. **Ingestion – Bronze Layer**  
   - Continuously reads tweet JSON streams from `s3a://voc-75-databricks-data/voc_volume/`  
   - Stores raw semi-structured data into Bronze Delta Table  

2. **Transformation – Silver Layer**  
   - Extracts key fields: `full_text`, `timestamp`, `lang`, `user_id`  
   - Cleans nulls, deduplicates IDs, standardizes timestamps  

3. **Model Inference – Gold Layer**  
   - Applies **Transformer-based sentiment classifier** via PySpark UDF  
   - Predicts sentiment labels: *positive, neutral, negative*  
   - Writes predictions to Gold Delta Table for downstream analytics  

---

### 🧠 Model & Tracking  
- **Model:** `cardiffnlp/twitter-roberta-base-sentiment` (Hugging Face)  
- **Integration:** MLflow logs metrics (Accuracy, F1, Latency) and version controls the model registry  
- **Deployment:** Registered model transitioned from *Staging* → *Production* for continuous inference  

---

### 📊 Results & Observations  
- **Accuracy:** ~92% on validation set using pre-finetuned model  
- **Latency:** Stream batches processed every 60 seconds  
- **Robustness:** Delta checkpointing ensured fault-tolerant writes  
- **Insights:** Visualized sentiment trends aligned with major real-world events (e.g., spikes in negative sentiment during global crises)

---

### 🧩 Key Challenges & Solutions  
- **Transformer inference overhead** → Batched processing + lightweight RoBERTa variant  
- **Stateful stream recovery** → Delta checkpointing + idempotent writes  
- **Real-time model scaling** → Asynchronous UDF + caching of embeddings  
- **MLflow registry sync** → Automated transition scripts for model stage promotion  

---

📎 **Full Code:**  
[👉 GitHub — Starter Streaming Tweet Sentiment (Spring 2024 Final Project)](https://github.com/leahnote01/dscc402/blob/main/final_project/Starter%20Streaming%20Tweet%20Sentiment%20-%20Spring%202024%20Final%20Project.ipynb)

---

📘 **Keywords:**  
`PySpark Structured Streaming` | `Delta Lake` | `Databricks` | `Transformer Models` | `MLflow` |  
`Real-Time Inference` | `Data Engineering` | `Hugging Face` | `MLOps` | `Sentiment Analysis`

