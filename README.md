# Intelligent Job Market Analysis & Skill Demand Prediction (Python Flask & Scikit-Learn Backend)

This module provides the complete Python, Flask, Scikit-learn, Pandas, and SQLite backend architecture for the Job Market Analysis system.

## 📁 Folder Structure

```
python_backend/
├── app.py                 # Flask REST API with prediction & analytics endpoints
├── model.py               # Scikit-learn RandomForestClassifier & RandomForestRegressor
├── preprocess.py          # Pandas & NumPy data cleaning, feature extraction, one-hot encoding
├── database.py            # SQLite schema, tables, and CRUD operations
├── seed_dataset.py        # Generates sample dataset and populates SQLite database
├── requirements.txt       # Python dependencies (Flask, Scikit-learn, Pandas, etc.)
└── dataset.csv            # Cleaned job market dataset (Power BI compatible)
```

## 🚀 Setup & Execution Guide

### 1. Prerequisites
Ensure you have Python 3.9+ installed on your system.

### 2. Create Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Seed SQLite Database & CSV Dataset
```bash
python seed_dataset.py
```
This generates `dataset.csv` and populates the SQLite database (`job_market.db`).

### 5. Start Flask Backend Server
```bash
python app.py
```
The API server will run at `http://localhost:5000`.

## 📡 API Endpoints

- `GET /api/health`: Health status and model readiness.
- `GET /api/jobs`: Query job listings with role, company, and remote filters.
- `GET /api/stats/overview`: Overview KPIs, vacancies, average salaries, and model accuracy.
- `POST /api/predict/demand`: Machine learning job demand classification using Random Forest.
- `POST /api/predict/salary`: Machine learning salary regression based on role, skills, experience, and company tier.
- `POST /api/recommend/skills`: Skill gap recommendation engine comparing candidate skills against role demand.
- `GET /api/export/csv`: Download Power BI-compatible cleaned dataset CSV.

## 📊 Power BI Integration
The generated `dataset.csv` can be imported directly into Power BI Desktop:
1. Open Power BI -> Get Data -> Text/CSV.
2. Select `dataset.csv`.
3. Use the pre-built visual measures for Vacancies, Role Distribution, and Skill Frequency.
