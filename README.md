# Real-Time ESG Sentiment Scoring for Financial Assets

This FinTech project introduces a **Real-Time ESG Sentiment Scoring System** powered by Big Data technologies and NLP. It combines ESG (Environmental, Social, Governance) analysis with sentiment mining from social media and financial news to provide **dynamic ESG scores** for financial assets.

The goal is to help investors make **ESG-conscious decisions** and observe **stock volatility patterns influenced by ESG narratives**.

---

## Key Features

- Real-time data ingestion using **Flume, Kafka, and Twitter APIs**
- ESG sentiment classification using **FinBERT + Named Entity Recognition (NER)**
- Dynamic scoring algorithm with time-decay and virality weighting
- Big Data storage via **HDFS and Hive**
- Automated asset action system (buy/sell) using **paper trading APIs**
- Visualization via **Streamlit dashboards**
- Research-grade: Enables publication-level analysis on ESG impact on stock behavior

---

## Tech Stack

- **Data Ingestion**: Flume, Kafka, Twitter API
- **Storage**: Hadoop HDFS, Hive
- **Processing**: Spark, Sqoop
- **NLP**: FinBERT, Spacy NER
- **Visualization**: Streamlit
- **Automation**: Alpaca API (Paper Trading)
- **Scheduler**: Apache Airflow

---

## Dataset Links

- ✅ [Twitter Financial Dataset (via Tweepy)](https://developer.twitter.com/en/docs/twitter-api)
- ✅ [Reddit ESG Sentiment Dataset (Pushshift)](https://pushshift.io)
- ✅ [Yahoo Finance Prices](https://finance.yahoo.com)
- ✅ [FinBERT Pretrained Model](https://huggingface.co/yiyanghkust/finbert-esg)

---

## 📂 Folder Structure

```
esg-sentiment-index/
├── data/
│   ├── raw/
│   ├── processed/
├── ingestion/
│   ├── flume-config/
│   └── kafka-producer/
├── processing/
│   ├── finbert_classifier.py
│   ├── esg_ner.py
├── storage/
│   ├── hdfs/
│   └── hive_queries.sql
├── automation/
│   └── alpaca_trading.py
├── dashboard/
│   └── streamlit_app.py
├── notebooks/
│   └── esg-volatility-analysis.ipynb
├── airflow_dags/
│   └── pipeline_scheduler.py
└── README.md
```

---

## How to Run the Project

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/esg-sentiment-index.git
cd esg-sentiment-index
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Set Up Flume + Kafka for Real-Time Data
```bash
# Launch Flume agent
flume-ng agent --conf conf --conf-file flume.conf --name a1

# Run Kafka producer to ingest Twitter/Reddit/News data
python kafka-producer/twitter_stream.py
```

### 4. Run NLP Scoring Pipeline
```bash
python processing/finbert_classifier.py
python processing/esg_ner.py
```

### 5. View ESG Dashboard
```bash
streamlit run dashboard/streamlit_app.py
```

---

## ⚙️ Automate Buy/Sell Decisions

- Use **[Alpaca Paper Trading](https://alpaca.markets/docs/api-references/trading-api/)** to simulate asset trades without real money.
- Configure API keys in `.env`:
```
ALPACA_API_KEY=your_key
ALPACA_SECRET_KEY=your_secret
```
- Run:
```bash
python automation/alpaca_trading.py
```

---

## 🧠 Research Contributions

- ✅ Proposes a **new ESG Sentiment Scoring Algorithm**
- ✅ Compares **traditional vs. big data ESG metrics**
- ✅ Analyzes **real-time ESG sentiment’s effect on stock volatility**

---

## 📜 License

MIT License

## 👨‍🔬 Authors

- Atharv Maleyvar
- Ansh Singhal
- Raghav Wadhwa

---

## Future Work

- Real-time ESG alerts system
- Integrate news articles from Bloomberg/Reuters
- Multilingual ESG sentiment scoring
