# 🏥 Medical AI Chatbot

An AI-powered Medical Chatbot built using Flask, LangChain, Pinecone, Groq LLM, and HuggingFace Embeddings.

The chatbot uses Retrieval-Augmented Generation (RAG) to answer medical-related queries using a custom medical knowledge base.

---

# 🚀 Features

- 💬 Modern Chatbot UI
- 🤖 AI-powered medical responses
- 🔎 RAG (Retrieval-Augmented Generation)
- 📚 Pinecone Vector Database
- ⚡ Groq LLM Integration
- 🧠 HuggingFace Embeddings
- 🌐 Flask Backend
- 📱 Responsive Design

---

# 🛠️ Tech Stack

## Frontend
- HTML
- CSS
- Bootstrap
- JavaScript
- jQuery

## Backend
- Flask
- Python

## AI / ML
- LangChain
- Pinecone
- Groq API
- HuggingFace Embeddings

---

# ⚙️ Installation

## 1️⃣ Clone Repository

```bash
git clone https://github.com/your-username/Medical-Chatbot.git

cd Medical-Chatbot
```

---

## 2️⃣ Create Conda Environment

```bash
conda create -n medibot python=3.10
```

Activate environment:

```bash
conda activate medibot
```

---

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🔑 Environment Variables

Create a `.env` file in the root directory.

```env
GROQ_API_KEY=your_groq_api_key
PINECONE_API_KEY=your_pinecone_api_key
```

---

# 🗂️ Create Pinecone Index

Create a Pinecone index with the name:

```bash
medical-chatboat
```

---

# 🧠 Upload Embeddings

Run:

```bash
python store_index.py
```

This uploads medical document embeddings to Pinecone.

---

# ▶️ Run Application

```bash
python app.py
```

Open browser:

```bash
http://127.0.0.1:8080
```

---

# 🤖 AI Models Used

## Groq LLM

```python
llama-3.1-8b-instant
```

## Embedding Model

```python
sentence-transformers/all-MiniLM-L6-v2
```

---

# 🔄 Application Workflow

```text
User Query
    ↓
Flask Backend
    ↓
LangChain Retrieval
    ↓
Pinecone Vector Search
    ↓
Groq LLM
    ↓
Medical Response
```

---

# 📦 Requirements

```txt
flask
langchain
langchain-community
langchain-pinecone
langchain-groq
sentence-transformers
pinecone
python-dotenv
```

---

# 🚀 Future Improvements

- 🎤 Voice Assistant
- 🔐 Authentication System
- 💾 Chat History
- 📄 PDF Report Analysis
- 🌍 Multi-language Support
- 📅 Doctor Appointment Booking

---

# ☁️ Deployment

# ☁️ AWS Deployment Guide

## 1️⃣ Login to AWS Console

Create IAM user with these permissions:

- `AmazonEC2ContainerRegistryFullAccess`
- `AmazonEC2FullAccess`

---

## 2️⃣ Create ECR Repository

Create repository in AWS ECR.

Example URI:

```text
315865595366.dkr.ecr.us-east-1.amazonaws.com/medicalbot
```

Save this URI.

---

## 3️⃣ Launch EC2 Instance

- Ubuntu Server
- Open Ports:
  - 22
  - 80
  - 8080

---

## 4️⃣ Install Docker in EC2

```bash
sudo apt-get update -y

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker
```

---

## 5️⃣ Configure EC2 as Self Hosted Runner

Go to:

```text
GitHub Repo
→ Settings
→ Actions
→ Runners
→ New Self Hosted Runner
```

Run all commands inside EC2 terminal.

---

## 6️⃣ Add GitHub Secrets

Go to:

```text
Repository
→ Settings
→ Secrets and Variables
→ Actions
```

Add:

```text
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
ECR_REPO
PINECONE_API_KEY
OPENAI_API_KEY
GROQ_API_KEY
```

---

## 7️⃣ Create Dockerfile

```dockerfile
FROM python:3.10-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

EXPOSE 8080

CMD ["python", "app.py"]
```

---

## 8️⃣ Push Code

```bash
git add .

git commit -m "deployment setup"

git push origin main
```

---

## 🌐 Access App

# ⚠️ Disclaimer

This chatbot is for educational purposes only.

It should not replace professional medical advice or consultation.

---

# 👨‍💻 Author

Prince Raj

---

# 📜 License

This project is licensed under the MIT License.