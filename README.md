# 🌙 Sloth Companion: Offline Wind-Down Companion

An offline, privacy-focused bedtime story and ambient soundscape generator powered by **Gemma 2** (`gemma2:2b`) via **Ollama** and built with **Streamlit**.
---

## 🦥 Overview

**Sloth Companion** helps you unplug and relax at the end of the day. By entering two cozy themes (e.g., *"Rain on a tin roof"* and *"Warm tea"*), the application generates a calming 3-paragraph bedtime story alongside a custom ambient soundscape recipe—**100% locally on your machine**.

---

## ✨ Features

- **100% Offline & Private:** Runs entirely on local hardware using Ollama. No data leaves your machine, no cloud API calls, and works in Airplane Mode.
- **Lightweight LLM:** Uses Google's open-weight `gemma2:2b` model for quick, local story generation.
- **Simple UI:** Minimalist Streamlit interface built for evening wind-down routines.

---

## 🛠️ Prerequisites & Setup

 **Install Ollama**  
   Download and install [Ollama](https://ollama.com/), then pull the Gemma 2 model in your terminal:
   ```bash
   ollama run gemma2:2b

**Clone the Repository**
   git clone [https://github.com/arpitarout32-sketch/offline-winddown-companion.git](https://github.com/arpitarout32-sketch/offline-winddown-companion.git)
cd offline-winddown-companion

**Install Python Dependencies**
pip install -r requirements.txt

**Run the Application**
python -m streamlit run sloth.py

____



📁 Repository Structure
sloth.py — Streamlit application interface and local inference pipeline.

requirements.txt — Python package dependencies (streamlit, ollama).

README.md — Project documentation.




   


   
