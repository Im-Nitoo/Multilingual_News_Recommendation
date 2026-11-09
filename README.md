# Multilingual News Recommendation
A personalized news recommendation system that uses multilingual transformer embeddings and user reading histories to recommend relevant news articles.

## Project Overview
This project builds an intelligent news recommendation system that understands user interests and surfaces relevant, personalized articles.

The current implementation uses the MIND-small dataset and a multilingual sentence-transformer model to generate semantic representations of news articles. User-interest profiles are built from historical reading interactions, and recommendations are ranked using cosine similarity.

Performance is benchmarked against a popularity-based baseline using standard information retrieval metrics.

Current scope: Content-based personalized news recommendation using multilingual-capable text embeddings. Full multilingual dataset evaluation and multimodal fusion are planned extensions.

## Objectives
Generate personalized news recommendations from user reading history

Represent news articles with multilingual transformer embeddings

Build user-interest profiles from historical interactions

Rank candidate articles by semantic similarity

Filter out articles a user has already read

Evaluate ranking quality with standard IR metrics

Compare personalized recommendations against a popularity baseline

Explore diversity, explainability, and cold-start strategies

## Technologies Used
Technology	Purpose
Python	Core implementation
Google Colab	Development environment
Google Drive	Dataset and model storage
Pandas	Data preprocessing and manipulation
NumPy	Embedding and vector operations
PyTorch	Transformer model execution
Sentence Transformers	Multilingual text embeddings
Hugging Face	Pretrained model access
Scikit-learn	Evaluation metrics
Matplotlib / Seaborn	Planned visualization
