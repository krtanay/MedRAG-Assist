# 🏥 MedRAG Assist— Intelligent Healthcare Assistant

Welcome to the **MedRAG Assist** — a production-ready, intelligent healthcare assistant powered by **Retrieval-Augmented Generation (RAG)** technology! This comprehensive system combines advanced language models with medical knowledge retrieval to provide accurate, contextual healthcare information and assistance.

---

## ✨ Key Features

- **🧠 RAG Architecture**: Combines retrieval and generation for accurate, evidence-based medical responses
- **📚 Medical Knowledge Base**: Pre-loaded with comprehensive medical documents and literature  
- **🔍 Smart Retrieval**: FAISS vector database for lightning-fast similarity search and document retrieval
- **🤖 Advanced LLM Integration**: Powered by LangChain with support for multiple language models (Groq, HuggingFace)
- **🌐 Web Interface**: Clean, intuitive Flask-based chatbot interface for seamless user interaction
- **🚀 Production-Ready**: Complete CI/CD pipeline with Jenkins, Docker, AWS ECR, and App Runner deployment
- **🔒 Secure & Scalable**: Containerized deployment with security scanning via Trivy
- **📱 Responsive Design**: Mobile-friendly interface for healthcare professionals and patients

---

## 🏗️ Architecture Overview

### RAG (Retrieval-Augmented Generation) Workflow

```
User Query → Embedding → Vector Search (FAISS) → Document Retrieval → 
Context + Query → LLM Processing → Generated Response → User Interface
```

### System Components

- **Document Processing**: PDF loaders for medical literature ingestion
- **Vector Store**: FAISS-based similarity search for rapid document retrieval  
- **Embeddings**: Sentence transformers for semantic document understanding
- **LLM Integration**: Multiple model support via LangChain (Groq, HuggingFace)
- **Web Frontend**: Flask-based responsive chatbot interface
- **Backend API**: RESTful endpoints for chat functionality

---

## 📂 Repository Structure

```plaintext
RAG-MEDICAL-CHATBOT/
├── app/
│   ├── components/           # Core RAG components
│   │   ├── data_loader.py   # Document loading utilities
│   │   ├── embeddings.py    # Text embedding generation
│   │   ├── llm.py          # Language model integration
│   │   ├── pdf_loader.py   # PDF document processing
│   │   ├── retriever.py    # Document retrieval logic
│   │   └── vector_store.py # FAISS vector database
│   ├── common/              # Shared utilities
│   ├── config/              # Configuration management
│   ├── templates/           # Flask HTML templates
│   └── application.py       # Main Flask application
├── custom_jenkins/          # Jenkins CI/CD setup
├── data/                    # Medical documents and datasets
├── vectorstore/db_faiss/    # Pre-built FAISS vector database
├── .gitignore
├── Dockerfile               # Container configuration
├── Jenkinsfile             # CI/CD pipeline definition
├── requirements.txt        # Python dependencies
├── setup.py               # Package setup

```

---

## 🚀 Quick Start

### Prerequisites
- Python 3.10+
- Docker Desktop (for containerized deployment)
- API Keys: HuggingFace, Groq (optional)

### Local Development Setup

```bash
# Clone the repository
git clone https://github.com/data-guru0/RAG-MEDICAL-CHATBOT.git
cd RAG-MEDICAL-CHATBOT

# Create virtual environment (Windows)
python -m venv venv
venv\Scripts\activate

# Install dependencies
pip install -e .

# Run the application
python app/application.py
```

Access the chatbot at `http://localhost:5000`

### Docker Deployment

```bash
# Build Docker image
docker build -t rag-medical-chatbot .

# Run container
docker run -p 5000:5000 rag-medical-chatbot
```

---

## 🔧 Technology Stack

### Core AI/ML Technologies
- **LangChain**: Framework for LLM application development
- **FAISS**: Facebook AI Similarity Search for vector operations
- **Sentence Transformers**: State-of-the-art text embeddings
- **HuggingFace**: Model hub and transformers library
- **Groq**: High-performance LLM inference

### Backend & Infrastructure
- **Flask**: Lightweight web framework for API and UI
- **Python 3.10**: Core programming language
- **Docker**: Containerization for consistent deployment
- **Jenkins**: CI/CD automation and pipeline management
- **AWS ECR**: Container registry for Docker images
- **AWS App Runner**: Serverless container deployment

### Development & Security
- **Trivy**: Container vulnerability scanning
- **Git**: Version control and collaboration
- **pip**: Python package management

---

## 🛠️ Development Guide

### Setting Up the RAG Pipeline

1. **Document Ingestion**: Place medical PDFs in the `data/` directory
2. **Vector Database Creation**: Run embedding generation to populate FAISS index
3. **Model Configuration**: Set up LLM preferences in `config/`
4. **Testing**: Use the Flask interface to validate responses

### Customization Options

- **Add New Documents**: Extend the knowledge base with additional medical literature
- **Model Selection**: Switch between different LLMs (Groq, HuggingFace, OpenAI)
- **UI Customization**: Modify Flask templates for branding and styling
- **Retrieval Tuning**: Adjust similarity search parameters for better relevance

---

## 🚀 Production Deployment

### Complete CI/CD Pipeline

The project includes a comprehensive Jenkins pipeline for production deployment:

1. **Code Integration**: GitHub repository integration with webhook triggers
2. **Automated Testing**: Container building and dependency validation  
3. **Security Scanning**: Trivy vulnerability assessment
4. **Container Registry**: Automated push to AWS ECR
5. **Deployment**: AWS App Runner for scalable, serverless hosting

### Deployment Steps

```bash
# 1. Setup Jenkins with Docker-in-Docker
cd custom_jenkins
docker build -t jenkins-dind .
docker run -d --name jenkins-dind --privileged -p 8080:8080 jenkins-dind

# 2. Configure GitHub integration and AWS credentials in Jenkins
# 3. Create pipeline job using provided Jenkinsfile
# 4. Trigger deployment pipeline
```

---

## 💡 Use Cases & Applications

### Healthcare Professionals
- **Clinical Decision Support**: Quick access to medical literature and guidelines
- **Patient Education**: Generate explanations for medical conditions and treatments
- **Research Assistance**: Rapid literature review and evidence synthesis

### Healthcare Institutions  
- **Patient Support**: 24/7 automated initial consultation and triage
- **Administrative Efficiency**: Reduce routine inquiry workload
- **Knowledge Management**: Centralized access to institutional medical knowledge

### Medical Education
- **Study Assistant**: Interactive learning with medical textbooks and papers
- **Case Studies**: Generate educational scenarios and explanations
- **Exam Preparation**: Q&A practice with evidence-based answers

---

## 🔒 Security & Compliance

- **Container Security**: Automated vulnerability scanning with Trivy
- **Data Privacy**: Local document processing without external data sharing
- **API Security**: Secure endpoint configuration and access controls
- **Audit Trail**: Comprehensive logging for compliance and monitoring

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 👥 Credits

**Project Maintainer**: Tanay  
**Built with**: LangChain, FAISS, Flask, Docker, AWS, Jenkins

**Special Thanks**: Open-source medical literature contributors and the AI/ML community
---

*Transform healthcare communication with intelligent, evidence-based AI assistance. Get started today!* 🚀