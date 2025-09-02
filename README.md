#  Movie Recommendation System (Collaborative + Content-Based)
A machine learning-based movie recommendation system built using collaborative filtering, content-based filtering.

This project is a **Movie Recommendation System** built in **Google Colab** using built-in libraries (`pandas`, `numpy`, `scikit-learn`).  

It combines:
- **Collaborative Filtering** (Item-Item similarity using cosine similarity on user–movie ratings)
- **Content-Based Filtering** (TF-IDF on movie titles & genres)
- A **Hybrid Model** (weighted average of the two)

Dataset: [MovieLens Latest Small](https://grouplens.org/datasets/movielens/latest/) (~100k ratings, ~9.7k movies).

---


---

## ⚙️ Features
- Download & preprocess **MovieLens dataset** automatically
- Build **user–movie rating matrix**
- Compute **item-item similarity matrix** (Collaborative Filtering)
- Generate **TF-IDF vectors** from movie titles + genres (Content-Based)
- Blend both recommenders with a **hybrid score**
- Functions for:
  - `recommend_for_user(user_id, top_n=10, alpha=0.5)`
  - `similar_to_movie(title, top_n=10, method="hybrid")`
  - `search_titles(query)`

---

##  Functions in Detail

### `recommend_for_user(user_id, top_n=10, alpha=0.5)`

Recommends movies for a given user:

- **user_id**: integer ID from MovieLens dataset  
- **top_n**: number of recommendations  
- **alpha**: weight for collaborative (0.0 = only content, 1.0 = only collaborative)  

---

### `similar_to_movie(title, top_n=10, method="hybrid")`

Finds movies similar to a given title:

- **title**: partial or full movie title (case-insensitive)  
- **method**: `"content"`, `"item"`, or `"hybrid"`  

---

### `search_titles(query)`

Searches for movies containing a given keyword (useful to check exact dataset titles).  

---

##  Example Usage

```python
# Recommend movies for a user
recommend_for_user(1, top_n=10, alpha=0.6)

# Find similar movies
similar_to_movie("Toy Story", top_n=10, method="hybrid")

# Search movie titles
search_titles("star wars")

