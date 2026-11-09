# Multilingual_News_Recommendation



A personalized news recommendation system using multilingual transformer embeddings and user reading histories to recommend relevant news articles.

📌 Project Overview

This project aims to develop an intelligent news recommendation system that understands users' interests and recommends relevant, personalized news articles.

The current implementation uses the MIND-small dataset and a multilingual sentence-transformer model to generate semantic representations of news articles. User-interest profiles are constructed from historical reading interactions, and recommendations are generated using cosine similarity.

The system is evaluated against a popularity-based recommendation baseline using standard information retrieval metrics.

«Current implementation: Content-based personalized news recommendation using multilingual-capable text embeddings. Full multilingual dataset evaluation and multimodal fusion are planned extensions.»

🎯 Objectives

- Develop personalized news recommendations based on user reading history.
- Represent news articles using multilingual transformer embeddings.
- Generate user-interest profiles from historical interactions.
- Recommend relevant articles using semantic similarity.
- Avoid recommending articles users have already read.
- Evaluate recommendation performance using ranking metrics.
- Compare personalized recommendations against popularity-based recommendations.
- Explore diversity, explainability, and cold-start recommendation strategies.

🧠 Technologies Used

Technology| Purpose
Python| Core implementation
Google Colab| Development environment
Google Drive| Dataset and model storage
Pandas| Data preprocessing and manipulation
NumPy| Embedding and vector operations
PyTorch| Transformer model execution
Sentence Transformers| Multilingual text embeddings
Hugging Face| Pretrained model access
Scikit-learn| Evaluation metrics
Matplotlib / Seaborn| Planned visualization

📂 Dataset

MIND-small

The project uses the Microsoft News Dataset (MIND-small), a dataset designed for news recommendation research.

Dataset components:

- Training news articles
- Training user behavior records
- Validation news articles
- Validation user behavior records

The dataset contains article metadata, reading histories, candidate news impressions, and click labels.

Dataset source: "Microsoft News Dataset (MIND)" (https://msnews.github.io/)

The dataset is used for academic and research purposes. Please refer to its official terms and conditions before redistribution.

🏗️ System Architecture

The current recommendation pipeline consists of the following stages:

1. Dataset acquisition and preprocessing
2. News article text preparation
3. Multilingual transformer embedding generation
4. Historical interaction extraction
5. User-interest profile generation
6. Content-based recommendation
7. Validation impression processing
8. Recommendation evaluation
9. Popularity baseline comparison

Recommendation Pipeline

MIND Dataset
     |
     v
Data Cleaning and Preprocessing
     |
     v
News Article Text
     |
     v
Multilingual Transformer
     |
     v
News Embeddings
     |
     v
Historical User Interactions
     |
     v
User Interest Profiles
     |
     v
Cosine Similarity Ranking
     |
     v
Personalized News Recommendations
     |
     v
Evaluation and Baseline Comparison

🤖 Multilingual Embedding Model

The project uses the following pretrained model:

Model: "sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2"

Hugging Face model page:

https://huggingface.co/sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2

The model generates 384-dimensional semantic embeddings for news articles.

These embeddings enable semantic similarity calculations between news articles and user-interest profiles.

Although the embedding model supports multiple languages, the current MIND-small evaluation is based on English-language news.

👤 User Interest Modelling

User profiles are generated from historical article interactions.

For each user:

1. Retrieve previously interacted-with articles.
2. Obtain their corresponding article embeddings.
3. Aggregate the embeddings into a user-interest vector.
4. Normalize the resulting vector.
5. Compare the user profile against candidate news articles.

The current implementation uses historical article embeddings to represent user interests.

📰 Recommendation Method

The recommendation engine uses content-based filtering.

Cosine similarity is used to measure the semantic similarity between a user's interest profile and candidate news articles.

The system ranks candidate articles based on their similarity scores and excludes previously read articles during recommendation generation.

Cosine Similarity

The similarity between a user profile and an article embedding is calculated as:

[
\operatorname{similarity}(u,n)=
\frac{u\cdot n}{|u||n|}
]

Where:

- (u) represents the user-interest vector.
- (n) represents the news article embedding.

Articles with higher similarity scores are considered more relevant to the user's interests.

📊 Dataset Statistics

The current implementation has processed the following data:

Component| Statistics
Training news articles| 51,282
Validation news articles| 42,416
Unique combined articles| 65,238
Embedding dimensions| 384
Historical user-article interactions| 915,011
Users with generated profiles| 49,108
Validation impressions| 73,152
Validation candidate records| 2,740,998

📈 Experimental Evaluation

The recommendation system is evaluated using the following metrics:

Metric| Description
AUC| Measures ranking discrimination between clicked and non-clicked candidates
MRR| Measures the ranking position of the first relevant article
NDCG@10| Measures ranking quality among the top 10 recommendations
Precision@10| Measures the proportion of clicked candidates among the top 10
Recall@10| Measures the proportion of clicked candidates retrieved among the top 10

Initial Evaluation Results

The current content-based recommender achieved the following results on the validation dataset:

Metric| Content-Based Model
AUC| 0.6469
MRR| 0.3595
NDCG@10| 0.4007
Precision@10| 0.0849
Recall@10| 0.6449

The model was evaluated on 70,938 eligible validation impressions.

Popularity Baseline Comparison

The personalized content-based model was compared against a popularity-based recommendation baseline.

Metric| Content-Based| Popularity-Based
AUC| 0.6469| 0.4877
MRR| 0.3595| 0.2250
NDCG@10| 0.4007| 0.2705
Precision@10| 0.0849| 0.0631
Recall@10| 0.6449| 0.5107

The initial results indicate that the content-based recommender achieved higher average scores across all five evaluation metrics.

Statistical validation is planned to assess the reliability of these differences.

🚀 Current Implementation Status

Completed

- [x] MIND-small dataset acquisition and preprocessing
- [x] Training and validation dataset preparation
- [x] Historical user interaction extraction
- [x] Multilingual transformer embedding generation
- [x] User-interest profile generation
- [x] Content-based recommendation engine
- [x] Previously read article filtering
- [x] Combined training and validation embedding index
- [x] Validation impression parsing
- [x] Embedding coverage verification
- [x] Initial recommendation evaluation
- [x] Popularity-based baseline comparison

Planned Improvements

- [ ] Statistical significance testing
- [ ] Diversity-aware recommendation
- [ ] Explainable recommendations
- [ ] Cold-start recommendation handling
- [ ] Robustness testing
- [ ] Ablation experiments
- [ ] Recommendation visualization
- [ ] Interactive demonstration interface
- [ ] Cross-lingual recommendation evaluation
- [ ] Multimodal news recommendation

🔮 Future Scope

The project can be extended in several directions:

1. Multilingual Recommendation

Evaluate recommendations using news articles in multiple languages and investigate cross-lingual semantic matching.

2. Multimodal Recommendation

Incorporate additional news modalities such as images and video using suitable feature extraction models.

3. Collaborative Filtering

Integrate user-item interaction patterns to complement content-based recommendation.

4. Diversity and Novelty

Improve recommendation diversity and reduce repetitive article suggestions.

5. Explainable AI

Provide understandable explanations for why specific news articles are recommended.

6. Cold-Start Recommendation

Develop recommendation strategies for new users and newly published articles.

💻 Development Environment

The project is developed using Google Colab with GPU acceleration where available.

Datasets, embeddings, user profiles, and evaluation results are stored in Google Drive.

⚙️ Installation

Install the required libraries:

pip install pandas numpy sentence-transformers scikit-learn tqdm

Additional dependencies may be required depending on the final implementation.

▶️ Usage

The project is currently implemented as a Google Colab notebook.

General workflow:

1. Open the project notebook in Google Colab.
2. Mount Google Drive.
3. Load the processed MIND dataset.
4. Load the pretrained multilingual transformer.
5. Load or generate news embeddings.
6. Generate user-interest profiles.
7. Run the recommendation engine.
8. Evaluate recommendations using the validation dataset.

The exact notebook execution order and file paths depend on the project configuration.

📁 Project Structure

The intended project organization is:

News_Recommendation_Project/
│
├── data/
│   ├── train_news.csv
│   ├── train_behaviors.csv
│   ├── validation_news.csv
│   └── validation_behaviors.csv
│
├── embeddings/
│   ├── train_news_embeddings.npy
│   ├── validation_news_embeddings.npy
│   ├── combined_news_embeddings.npy
│   └── user_interest_profiles.npy
│
├── mappings/
│   ├── combined_news_mapping.csv
│   └── user_profile_mapping.csv
│
├── evaluation/
│   ├── baseline_evaluation_results.csv
│   ├── popularity_evaluation_results.csv
│   └── baseline_comparison.csv
│
└── README.md

This structure describes the intended organization. The actual notebook and saved files may currently be organized differently.

⚠️ Limitations

- The current evaluation uses the English-language MIND-small dataset.
- The pretrained model is multilingual-capable, but multilingual recommendation performance has not yet been experimentally established.
- The current system primarily uses textual article content.
- Image and video features are not yet integrated.
- The current recommendation architecture is content-based rather than a complete multimodal recommendation framework.
- Additional statistical validation and robustness experiments are required.

🎓 Academic Context

This project is being developed as an academic research and implementation project focused on personalized news recommendation using multilingual-capable semantic embeddings.

The current implementation serves as a baseline framework for further development toward multilingual and multimodal news recommendation.

👥 Contributors

- Project Team: [Add team member names]
- Institution: [Add institution name]
- Supervisor: [Add supervisor name]

📄 License

This repository is intended for academic and research purposes.

Add an appropriate license before publicly distributing the source code.

🙏 Acknowledgements

- Microsoft Research for the MIND news recommendation dataset.
- Hugging Face for pretrained transformer models.
- Sentence Transformers for semantic embedding tools.
- Google Colab for the development environment.

---

Project Status: Research prototype under development.

More advanced multilingual, multimodal, and recommendation capabilities will be added as the project progresses.
