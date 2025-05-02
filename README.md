# Fraud Detection with MLOps

## 📌 Project Overview
This project implements an **end-to-end fraud detection system** using **MLOps principles**, integrating data ingestion, preprocessing, model training, deployment, and monitoring.

## 🎯 Objectives
- Build a fraud detection model using **Machine Learning**.
- Automate data ingestion from **Google BigQuery**.
- Store preprocessed data in **PostgreSQL**.
- Deploy the model using **FastAPI** and containerize it with **Docker**.

## 🛠 Tech Stack
- **Python** (pandas, scikit-learn, FastAPI, SQLAlchemy)
- **Google BigQuery** (Data Warehouse)
- **PostgreSQL** (Database Storage)
- **FastAPI** (Model Serving API)
- **Docker** (Containerization)
- **GitHub Actions** (CI/CD)

## 🏗 Project Workflow
1. **Data Ingestion** → Extract fraud-related transactions from **BigQuery**.
2. **ETL Process** → Clean & preprocess data (handling missing values, feature extraction).
3. **Model Training** → Train a **Random Forest** classifier on fraud data.
4. **Model Deployment** → Serve predictions via **FastAPI**.
5. **Containerization** → Deploy as a **Docker** container.
6. **Monitoring & Scaling** → Track API performance and improve model as needed.

## 📂 Folder Structure
```
Fraud-Detection-MLops/
│── data/                # Raw dataset
│── dataclean/           # Processed dataset
│── model/               # Saved ML model & vectorizer
│── preprocessing/       # Data preprocessing scripts
│── modelling/           # Model training scripts
│── etl/                 # ETL scripts (BigQuery & PostgreSQL)
│── docker/              # Docker configurations
│── main.py              # FastAPI backend
│── Dockerfile           # Docker image setup
│── requirements.txt     # Python dependencies
│── README.md            # Project documentation
```

## 🚀 Getting Started
### 1️⃣ Setup Environment
```bash
# Clone the repository
git clone https://github.com/your-username/Fraud-Detection-MLops.git
cd Fraud-Detection-MLops

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### 2️⃣ Configure Google BigQuery & PostgreSQL
Ensure you have:
- **Google Cloud credentials** (`service_account.json`)
- **PostgreSQL database** with a created schema

Set up your environment variables:
```bash
export GOOGLE_APPLICATION_CREDENTIALS="path/to/service_account.json"
export DATABASE_URL="postgresql://user:password@localhost:5432/fraud_db"
```

### 3️⃣ Run the ETL Pipeline
```bash
python etl/data_ingestion.py
```

### 4️⃣ Train & Save the Model
```bash
python modelling/train_model.py
```

### 5️⃣ Start FastAPI Server
```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

### 6️⃣ Run with Docker
```bash
# Build Docker image
docker build -t fraud-detection .

# Run container
docker run -p 8000:8000 fraud-detection
```

## 📊 API Endpoints
| Method | Endpoint         | Description                 |
|--------|----------------|-----------------------------|
| POST   | `/predict/`     | Predict fraud transaction  |
| GET    | `/health/`      | Check API health           |

## 📜 License
This project is open-source under the **MIT License**.

---
**Author:** [Naufal Faiz](https://github.com/nopal-fz)  
🚀 Happy Coding!
