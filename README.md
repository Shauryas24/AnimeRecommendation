# AnimeRecommendation
# AniRoll: Campus Anime Recommendation & Event Engine

AniRoll is a high-performance, full-stack recommendation platform designed specifically for the IIT Kanpur AniSoc community. It leverages existing machine learning collaborative filtering architectures to deliver hyper-local, personalized recommendations to students while optimizing club event curation.

##  Key Features

* **Hyper-Local Personalization:** Fine-tunes standard anime recommendations by blending global metadata with campus-specific preferences.
* **Production-Grade Backend:** Wraps ML models inside an optimized FastAPI microservice framework ensuring low-latency inference (<200ms).
* **Multi-Algorithm Pipeline:** Evaluates user tastes across structural, content-based, and deep learning paradigms[cite: 1].
* **Real-Time Event Voting:** Features a Redis-backed queue allowing students to request and upvote anime for upcoming Open Air Theatre (OAT) screenings.

##  Recommendation Algorithms Implemented

This project implements and evaluates four core recommender system paradigms[cite: 1]:

### 1. Non-Personal Recommendations
Designed to handle cold-start problems for new users. Recommendations are calculated by weighting an anime's raw rating against its global popularity (multiplying the average rating by the total number of members who have watched it)[cite: 1].

### 2. Item-Item Nearest Neighbor Collaborative Filtering
Constructs a large sparse matrix using user IDs as rows and anime IDs as columns[cite: 1]. By computing similarity metrics (such as correlation coefficients) across columns, the system instantly suggests highly correlated titles once a user interacts with an anime they enjoy[cite: 1].

### 3. Content-Based Recommendations
Independent of user ratings, this engine groups media by item descriptions[cite: 1]. It builds a bag-of-words representation based on `Genre` tags and calculates cosine similarity to suggest textually and structurally related shows[cite: 1].

### 4. Neural Collaborative Filtering (NCF)
A deep learning approach utilizing separate embedding layers for both users and items[cite: 1]. These high-dimensional vectors are optimized through training to map complex, non-linear relationships and directly predict a user's latent preference score for any given item[cite: 1].
