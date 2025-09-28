# Can You Hear Me? Automatic Speech Recognition Pipeline for Distress Intelligence.

# Project Lifecycle and Deliverables
The project follows the complete AI service lifecycle for the Automatic Speech Recognition (ASR) Pipeline, with each phase delivering a critical component.

| Phase | Directory | Goal | Key Deliverables |
| :--- | :--- | :--- | :--- |
| **1. Deployment** | `deployment/` | Host the base ASR model as a scalable microservice. | **Docker Image** with the respective inference endpoint. |
| **2. Finetuning** | `train/` | Optimize the model's accuracy using the Common Voice dataset. | Custom finetuned model weights. |
| **3. Evaluation** | `eval/` | Quantify performance gains and outline the strategic roadmap. | **Comparison** detailing baseline vs. finetuned performance. |
| **4. Post-Processing** | `postprocessing/` | Transform raw transcripts into actionable intelligence. | **Detection results** enhanced with **AI-powered similarity** analysis. |

# Project Overview
- Phase 1: Deployment 🚀
    - To establish the foundational infrastructure by hosting the base ASR model as a scalable microservice and outputting a reliable Dockerized API.
    - Created a lightweight web service with a primary inference endpoint for audio transcription, then containerize it for consistent deployment.
- Phase 2: Finetuning 🧠
    - To improve model performance by finetuning the base ASR model on custom data.
- Phase 3: Evaluation 📊
    - To quantify the model's performance gains against the baseline model.
    - Compared the finetuned model against the baseline model using quantitative and qualitative analysis and propose future improvements.
- Phase 4: Post-Processing and Intelligence 🚨
    - To supplement an intelligence layer to filter critical information.
    - Performed both exact string matching for specific hotwords and advanced semantic similarity analysis using an BERT embedding model.

## Technology Stack Overview

| Category | Component | Technology / Model |
| :--- | :--- | :--- |
| **Microservice** | Web Framework | **Python, FastAPI** |
| **ASR Model** | Base Model | **`facebook/wav2vec2-large-960h`** |
| **Intelligence** | Embedding Model | **`google-bert/bert-base-uncased`** |
| **Data** | Training & Evaluation | **Mozilla Common Voice** |
| **Deployment** | Containerization | **Docker** |

## Code Structure
The project is organized into four phases, each in its own directory.

```
.
├── deployment/
│   ├── asr_api.py                  # FastAPI service for ASR inference API.
│   ├── Dockerfile                  # Define Docker container service.
│   └── cv-decode.py                # Client script to test API.
├── train/
│   ├── asr-train.ipynb             # Notebook for model finetuning.
├── eval/
│   ├── 01-asr-eval.ipynb           # Model evaluation with test files.
│   └── 02-compare-analysis.csv     # Comparison of base vs. finetuned model performance.
├── postprocessing/
│   ├── 01-hotword-inference.ipynb  # Notebook for exact hotword detection.
│   ├── 02-similar-hotwords.ipynb   # Notebook for semantic similarity analysis.
└── README.md
```

