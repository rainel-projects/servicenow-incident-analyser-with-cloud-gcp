# 🧠 AI-Powered IT Incident Intelligence Platform on Google Cloud

Modern enterprises manage thousands of IT incidents daily in **ServiceNow**.  
Manual triaging, categorization, and trend reporting consume hours of analyst time.

This demo showcases a **fully cloud-native, AI-driven solution** that automates end-to-end incident intelligence — built on **Google Cloud Foundation Fabric** and **Google Agentspace (Vertex AI)**.

---

## 🚀 Project Overview

This platform automates:

- 🔄 **Incident ingestion** from ServiceNow  
- 🧩 **AI-powered summarization** of incident trends and anomalies  
- 📊 **Insight storage and visualization** using BigQuery  

The entire solution runs on **Google Cloud Free Tier**, provisioned with **Infrastructure-as-Code (Terraform / Foundation Fabric)**.

---

## 🏗️ Architecture Overview

**Services Used (Free Tier Compatible):**

| Component | Service | Purpose |
|------------|----------|----------|
| 🧱 Infrastructure-as-Code | **Cloud Foundation Fabric (Terraform)** | Builds and manages the GCP environment |
| ⚙️ Serverless Function | **Cloud Functions** | Pulls incidents from the ServiceNow API |
| 💾 Data Storage | **BigQuery** | Stores and aggregates incident data |
| 🤖 AI Summarization | **Agentspace / Vertex AI Studio** | Summarizes incident patterns using Gemini |
| 📂 Optional Backup | **Cloud Storage** | Stores raw incident JSON exports |
| 🔐 Security & Logging | **IAM / Cloud Logging** | Controls access and observability |

---

## ⚙️ Architecture Flow

1. **Terraform (Cloud Foundation Fabric)** provisions:
   - A **BigQuery dataset** for analytics  
   - A **Cloud Storage bucket** for raw data backups  

2. **Cloud Function** triggers daily (via scheduler) or manually:
   - Fetches incidents from your **ServiceNow Developer Instance** (REST API)
   - Stores results as JSON in **Cloud Storage**
   - Loads structured data into **BigQuery**

3. **Agentspace Agent (Gemini / Vertex AI)** connects to BigQuery:
   - Runs SQL queries to analyze patterns (e.g., most frequent categories, urgency levels)
   - Generates intelligent summaries and recommendations

4. **Output** can be displayed in:
   - Vertex AI Studio / Agentspace chat
   - Colab Notebook
   - Slack / Chat / Console (via API integration)

---

## 🧰 Tech Stack

- **Google Cloud Foundation Fabric (Terraform)**
- **Google Cloud Functions (Python)**
- **Google BigQuery**
- **Google Cloud Storage**
- **Agentspace / Vertex AI Studio**
- **ServiceNow Developer Instance**
- **IAM & Cloud Logging**

---

## 🧩 Setup Instructions

### 1️⃣ Prerequisites
- Google Cloud account (Free Tier)
- ServiceNow Developer Instance
- Terraform installed locally (`>= 1.6`)
- Python 3.10+ (for Cloud Function)

<img width="940" height="473" alt="image" src="https://github.com/user-attachments/assets/5df1cc69-63a6-4144-8ece-921c4838e07b" />
<img width="940" height="477" alt="image" src="https://github.com/user-attachments/assets/6456e410-74fc-4369-a559-bf287226a65c" />
<img width="940" height="504" alt="image" src="https://github.com/user-attachments/assets/5e968305-5f31-4f4d-8562-7ba6e304ac67" />


### 2️⃣ Configure Environment
```bash
gcloud init
gcloud auth application-default login


