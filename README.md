# Multi-Agent Movie Recommender System

This repository contains the code for a hierarchical multi-agent movie recommendation system built with LangGraph. The system is designed to provide personalized and context-aware movie suggestions based on user queries, leveraging the power of Large Language Models (LLMs) and semantic search.

## Project Overview

The system uses a sophisticated multi-agent architecture to generate high-quality recommendations. Instead of a single model, it employs a team of specialized agents that collaborate to handle different parts of the recommendation process. This allows for a more robust and intelligent system that can interpret user context, filter relevant movies, and provide clear explanations for its choices.

## System Architecture

The core of the system is a hierarchical graph built with **LangGraph**, which manages the workflow between specialized agents and tools.

1.  **Master Router:** Directs the user query to the appropriate subgraph based on its content.
2.  **Recommendation Subgraph:**
    * Uses a **Movie Data Simulator** tool to retrieve candidate movies. This tool performs a semantic search using embeddings from `sentence-transformers/all-MiniLM-L6-v2` and applies genre filtering.
3.  **Personalization Subgraph:**
    * A **Context Parser** agent interprets the user's mood or context (e.g., "a relaxed comedy," "an action-packed thriller") to refine the recommendations.
4.  **Explanation Subgraph:**
    * An **Explanation Formatter** agent generates a natural language justification for why the specific movies were recommended.

The entire system is powered by the `google/flan-t5-small` LLM for text generation tasks within the agents.

## Key Achievements

The system was evaluated on a custom suite of metrics and demonstrated excellent performance:

* **High Relevance:** Achieved **92% genre relevance**, ensuring the recommendations closely match the user's request.
* **Perfect Context Alignment:** Scored a perfect **1.00** on context alignment, proving its ability to understand and adapt to the user's mood.
* **Efficient Performance:** Maintained a fast average response time of just **0.129 seconds**.
* **Robust & Scalable:** The system successfully handled a variety of queries, including invalid ones, with an efficient average of 9.6 state transitions per successful run.

## Technologies & Frameworks

* **Agentic Framework:** LangGraph, LangChain
* **LLM:** `google/flan-t5-small` (via Hugging Face `transformers`)
* **Embeddings:** `sentence-transformers/all-MiniLM-L6-v2`
* **Data Handling & Visualization:** Pandas, NumPy, Matplotlib, Scikit-learn (for t-SNE), Graphviz
* **Dataset:** TMDB 5000 Movie Dataset

## How to Run

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/ahmedimaddd/LangGraph-Movie-Recommender-System]
    ```
2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Run the notebook:**
    Open and run the Jupyter Notebook to see the agent setup, evaluation, and inference examples.

For a comprehensive analysis of the methodology and results, please see the full project report included in this repository.
