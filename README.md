# Quantum-Enhanced Medical Question Answering System

## Overview

This project presents a Quantum-Enhanced Retrieval-Augmented Generation (RAG) system for answering medical questions. The system combines Large Language Models (LLMs), semantic retrieval, neural re-ranking, and quantum machine learning techniques to improve the quality and relevance of generated medical responses.

The model is fine-tuned on a medical Question-Answer dataset and uses a multi-stage retrieval pipeline consisting of FAISS retrieval, Cross-Encoder re-ranking, and Quantum Kernel re-ranking before generating answers.

---

## Features

- Fine-tuned Qwen2.5-3B-Instruct model using LoRA
- Retrieval-Augmented Generation (RAG)
- Semantic search with Sentence Transformers
- FAISS vector indexing
- Cross-Encoder document re-ranking
- Quantum-enhanced re-ranking using Qiskit
- Medical Question Answering interface
- GPU-optimized training using Unsloth

---

## System Architecture

User Question
↓
Embedding Generation
↓
FAISS Retrieval
↓
Cross-Encoder Re-ranking
↓
Quantum Kernel Re-ranking
↓
Context Construction
↓
Fine-Tuned Qwen Model
↓
Generated Medical Answer

---

## Dataset

The project uses the Cancer Q&A Dataset available on Kaggle.

Dataset contains:

- Medical questions
- Expert answers
- Cancer-related healthcare information

---

## Technologies Used

### Machine Learning

- Python
- Pandas
- NumPy

### Large Language Models

- Qwen2.5-3B-Instruct
- Unsloth
- LoRA (PEFT)

### Retrieval

- Sentence Transformers
- FAISS

### Re-ranking

- Cross-Encoder (MS MARCO MiniLM)

### Quantum Computing

- Qiskit
- Qiskit Machine Learning
- Fidelity Quantum Kernel
- ZZ Feature Map

---

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/quantum-medical-rag.git
cd quantum-medical-rag
```

Install dependencies:

```bash
pip install unsloth
pip install datasets
pip install sentence-transformers
pip install faiss-cpu
pip install qiskit
pip install qiskit-machine-learning
```

---

## Model Training

The Qwen2.5 model is fine-tuned using:

- LoRA adapters
- 4-bit quantization
- Medical Question-Answer dataset

Training pipeline:

1. Load dataset
2. Clean and preprocess data
3. Format instruction-response pairs
4. Fine-tune model using SFTTrainer
5. Save trained model

---

## Retrieval Pipeline

### Step 1: Dense Retrieval

Questions are embedded using:

```text
BAAI/bge-m3
```

and indexed using FAISS.

### Step 2: Cross-Encoder Re-ranking

Retrieved documents are re-ranked using:

```text
cross-encoder/ms-marco-MiniLM-L-6-v2
```

### Step 3: Quantum Re-ranking

A Quantum Kernel is applied using:

```text
ZZFeatureMap
```

and

```text
FidelityQuantumKernel
```

to further refine document ranking.

---

## Answer Generation

The top-ranked answers are merged into a context window and passed to the fine-tuned Qwen model.

The model is instructed to:

- Answer only from retrieved evidence
- Avoid hallucinations
- Return evidence-based responses

---

## Example

### Input

```text
What are the symptoms of lung cancer?
```

### Output

```text
Common symptoms of lung cancer include persistent cough,
chest pain, shortness of breath, coughing blood,
fatigue, and unexplained weight loss.
```

---

## Project Structure

```text
quantum-medical-rag/
│
├── quantum-model.ipynb
├── medical_qwen/
├── README.md
└── requirements.txt
```

---

## Future Improvements

- Larger medical datasets
- Hybrid sparse-dense retrieval
- Clinical benchmark evaluation
- Real quantum hardware experiments
- Web-based medical chatbot interface
- Explainable AI module

---

## Disclaimer

This project is intended for educational and research purposes only.

The generated responses should not be considered professional medical advice. Users should always consult qualified healthcare professionals for diagnosis and treatment decisions.

---

## Author

Developed as a research project on:

**Quantum-Enhanced Retrieval-Augmented Generation for Medical Question Answering**
