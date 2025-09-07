# Semantic Book Recommender

The Semantic Book Recommender is an intelligent book recommendation system powered by NLP techniques, Hugging Face models, and a Kaggle books dataset. Unlike traditional recommenders that rely only on metadata, this project leverages semantic embeddings, zero-shot classification, and sentiment analysis to provide recommendations tailored to the user’s query, desired category, and emotional tone.

## 📂 Project Structure

1. books_with_emotions.csv – Final dataset with books and their emotion scores (created through preprocessing).
2. data_sorting.ipynb – Notebook for cleaning and preparing raw book data.
3. vector_search.ipynb – Builds semantic embeddings and enables similarity-based retrieval.
4. sentiment_analysis.ipynb – Performs zero-shot classification and emotion tagging for books.
5. frontend.py – Main application file; integrates embeddings, sentiment scores, and a Gradio interface.
6. tagged_descriptions.txt – Stores processed book descriptions with unique numeric identifiers for retrieval.
7. cover-not-found.jpg – Placeholder cover image for books without available thumbnails.
8. requirements.txt – Python dependencies for running the project.

## ⚙️ Features

- 🔎 Semantic Search – Uses Hugging Face embeddings to match books based on natural language queries.
- 🎭 Emotion-Aware Recommendations – Re-ranks books according to emotional tones like Happy, Sad, Suspenseful, Surprising, Angry.
- 📚 Category Filtering – Refines recommendations by genre or category.
- 🖼️ Book Covers & Previews – Displays thumbnails (or fallback placeholder) alongside book details.
- 🌐 Interactive Gradio Dashboard – Clean UI for searching and retrieving book recommendations in real time.

## 🚀 How It Works

1. Data Preparation

 - Raw Kaggle dataset → processed via data_sorting.ipynb.
 - Descriptions tagged with IDs (tagged_descriptions.txt).

2. Embedding & Indexing

 - Semantic vectors generated using sentence-transformers/all-MiniLM-L6-v2.
 - Indexed using Chroma for fast similarity search.

3. Emotion Classification

 - Books annotated with emotion probabilities using zero-shot classification.
 - Stored in books_with_emotions.csv.

4. Frontend Application

 - frontend.py integrates semantic search + emotion scores.
 - Runs an interactive Gradio dashboard for querying recommendations.

## 🛠️ Installation & Setup

1. Clone this repository:  
git clone https://github.com/AA-KH/Semantic-Book-Recommender.git   
cd Semantic-Book-Recommender  

2. Create a virtual environment:  
python3 -m venv bookrec_venv  
source bookrec_venv/bin/activate # Mac/Linux  
bookrec_venv\Scripts\activate # Windows  

3. Install dependencies:  
pip install -r requirements.txt  

4. Run the application:  
python frontend.py  

## 📊 Tech Stack

- Python (pandas, numpy)
- LangChain (Chroma, text splitters, Hugging Face embeddings)
- Hugging Face Models (all-MiniLM-L6-v2, zero-shot classifiers)
- Gradio – Interactive UI for recommendations
- Jupyter Notebooks – Data preprocessing, sentiment analysis, embedding search
