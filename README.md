# 🌊 FloatChat — AI-Powered ARGO Ocean Data Explorer

<p align="center">
  <b>Natural Language • AI Querying • ARGO Ocean Data • Interactive Visualization</b>
</p>

<p align="center">
  An AI-powered conversational interface for exploring and visualizing ARGO float oceanographic data using natural language.
</p>

<p align="center">

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-Vector_DB-FF6B35?style=for-the-badge)
![Plotly](https://img.shields.io/badge/Plotly-Visualization-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-Transformers-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)

</p>

---

## 🌊 Overview

**FloatChat** is an AI-powered conversational data exploration application designed to make **ARGO oceanographic data easier to query and understand**.

Instead of requiring users to manually write SQL queries or navigate complex datasets, FloatChat provides a conversational interface where users can ask questions about oceanographic data using natural language.

The application combines:

- 🤖 Local language-model based query interpretation
- 🗄️ PostgreSQL for structured ARGO data
- 🧠 ChromaDB for semantic/vector-based retrieval
- 💬 Streamlit conversational interface
- 📊 Interactive Plotly visualizations
- 🌍 Geographic visualization of ARGO float locations
- 📈 Oceanographic parameter analysis

The project was developed as a **hackathon-oriented proof of concept** for conversational exploration of ARGO data.

---

# 🎯 Problem Statement

Oceanographic datasets can contain large amounts of structured information that is difficult to explore without technical knowledge.

Users may want to ask questions such as:

> "Show the average salinity near the equator."

or:

> "Show me the ARGO floats in the Indian Ocean."

Traditional database systems require users to understand:

- Database schemas
- SQL syntax
- Column names
- Geographic filtering
- Data visualization tools

This creates a barrier for researchers, students, and other users who want to explore ocean data without writing database queries manually.

---

# 💡 Proposed Solution

FloatChat introduces a conversational interface between the user and the ARGO dataset.

The user enters a natural-language question.

The system then:

1. Receives the user's question.
2. Sends the question to the AI query-processing pipeline.
3. Generates a PostgreSQL query.
4. Corrects known column-name and date formatting issues.
5. Executes the query against PostgreSQL.
6. Queries ChromaDB for semantic retrieval.
7. Returns the results through the Streamlit interface.
8. Generates interactive visualizations from ARGO data.

This creates a workflow where users can interact with oceanographic data through natural language rather than directly writing SQL.

---

# ✨ Key Features

## 💬 Conversational Interface

FloatChat provides a chatbot-style interface designed around natural-language interaction.

Features include:

- Chat-style user and AI messages
- Session-based conversation history
- Floating input field
- AI processing indicator
- Automatic scrolling
- Dedicated Chat and About pages

---

## 🤖 AI-Assisted Query Processing

The backend uses a local **FLAN-T5 Base** model through Hugging Face Transformers.

The model is prompted to generate PostgreSQL queries from natural-language questions.

Example:

```text
User:
Show average salinity near the equator in March 2025
