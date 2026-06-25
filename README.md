# 🤖 RAG Chatbot | Cardiac Pre- and Post-Operative Guidance

This repository contains the source code of the prototype developed for the Graduation Thesis (TCC) in Biomedical Informatics, focusing on the safe application of Artificial Intelligence in healthcare.

## 🎯 Objective
To develop and validate a Conversational Agent (CA) that utilizes the Retrieval-Augmented Generation (RAG) architecture to provide accurate and safe guidance to cardiac patients, mitigating the hallucination risks associated with generic LLMs.

## ⚙️ Architecture and Technologies
The success of the project is attributed to the engineering of a composite Knowledge Base (KB) and the rigorous parameterization of the RAG chain.

| Component | Technology | Role in the Project |
| :--- | :--- | :--- |
| **LLM (Language Model)** | Llama 3 (Quantized Version) | Generation of human-like and contextualized responses. |
| **Framework** | LangChain | Orchestration of the RAG chain and retriever logic. |
| **Vector Database (DB)** | ChromaDB | Persistent storage of the vector Knowledge Base (KB). |
| **Simulation Interface** | Gradio | Creation of the web and mobile interface for remote testing. |

## 📁 Hybrid Knowledge Base
The KB was optimized for clinical safety, combining:
* **Scientific Literature:** Peer-reviewed articles on cardiac surgery.
* **Tactical Knowledge:** FAQ documents and routine protocols developed by a specialist nurse.

## 🔑 Safety and Validation
* The system utilizes a **Safety Prompt Template** that forces redirection to a medical professional in case of individualized questions or uncertainty.
* The **Safety Rate (0% hallucination)** was validated through blind tests with clinical specialists.

## 💻 How to Run

This project was developed for the **Google Colab** environment. To run it, follow these steps:

1. Clone this repository and upload the `data/` and `chroma_db/` folders to an accessible location in your Google Drive.
2. Open the main notebook file (e.g., `Chatbot_RAG.ipynb`) in Google Colab.
3. **Path Adjustment (CRITICAL):** In the first cell of the notebook, where the Google Drive paths are defined, it is essential to adjust the variables (`DRIVE_PATH`, `CHROMA_PERSIST_DIR`, etc.) so that they point to the exact location of the folders in your own Drive.

   *Example of Notebook Adjustment:* If you placed the project in `My Drive/ChatBot/`, the path in the code must be modified to:
   ```python
   DRIVE_PATH = "/content/drive/MyDrive/ChatBot/"
