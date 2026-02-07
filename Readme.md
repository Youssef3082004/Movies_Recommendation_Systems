# Movie Recommendation Systems 🎬


<div align="center">

[![Python](https://img.shields.io/badge/Python-3.13+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-2.2.3+-3776AB?style=for-the-badge&logo=pandas&logoColor=white)](https://python.org)
[![NumPy](https://img.shields.io/badge/NumPy-1.26+-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.4+-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.9+-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)](https://matplotlib.org)
[![Seaborn](https://img.shields.io/badge/Seaborn-0.13+-4C72B0?style=for-the-badge&logo=python&logoColor=white)](https://seaborn.pydata.org)


</div>



## 📑 Description
A comprehensive collection of movie recommendation engines designed to provide personalized suggestions and identify trending content based on historical movie data.

## 📂 Dataset

The project uses a subset of the **MovieLens** dataset, consisting of two primary CSV files 
:

### 1. `movies.csv`
Contains metadata for movies.
* **movieId**: Unique identifier for each movie.
* **title**: Title of the movie (includes the release year in parentheses, e.g., "Toy Story (1995)").
* **genres**: Pipe-separated list of genres associated with the movie (e.g., "Adventure|Animation|Children").

### 2. `ratings.csv`
Contains user ratings for movies.
* **userId**: Unique identifier for each user.
* **movieId**: Reference to the movie being rated.
* **rating**: User rating on a scale (e.g., 0.5 to 5.0).
* **timestamp**: Time when the rating was recorded.

> 👉 Press here to download [**Dataset**](https://www.kaggle.com/datasets/parasharmanas/movie-recommendation-system/data) from *`Kaggle`*

## 🚀 Overview

The project is divided into two main recommendation methodologies:

### 1. Popularity-Based Recommender

This system recommends movies based on their overall popularity across the entire user base. It uses a **Weighted Rating** formula (similar to the one used by IMDb) to ensure that movies with a high average rating but very few votes don't unfairly dominate the top charts.

**Key Features:**

* **Feature Engineering:** Extracts production years from movie titles and cleans the data.
* **Weighted Scoring:** Implements a mathematical formula considering vote counts (), average ratings (), minimum vote thresholds (), and global average ratings ().
* **Global Trends:** Perfect for new users where specific preference data isn't available yet ("Cold Start" problem).

### 2. Content-Based Recommender

This system provides personalized recommendations based on the genres of movies a specific user has already liked. It analyzes the "content" of the items to find similarities.

**Key Features:**

* **TF-IDF Vectorization:** Converts movie genres into a mathematical matrix to understand the weight of each category.
* **Cosine Similarity:** Calculates the distance between movie vectors to find the most "similar" films.
* **User Profiling:** Recommends the top 10 movies most relevant to a specific user's high-rated history.
* **Data Visualization:** Includes visual insights into a user's most-watched categories using `seaborn` and `matplotlib`.

## 🛠️ Tech Stack

* **Language:** Python
* **Data Manipulation:** `pandas`, `numpy`
* **Machine Learning:** `scikit-learn` (TF-IDF, Cosine Similarity)
* **Visualization:** `matplotlib`, `seaborn`
* **Regex:** `re` (for data cleaning and feature extraction)

## 📁 Repository Structure

```bash
├── Datasets/
│   ├── movies.csv          # Movie IDs, titles, and genres
│   └── ratings.csv         # User IDs, movie IDs, and ratings
├── Content_based.ipynb      # Content-based filtering implementation
└── Popularity_based.ipynb   # Weighted popularity scoring implementation

```

## ⚙️ How it Works

1. **Preprocessing:** The notebooks clean movie titles and extract the release year as a separate numerical feature.
2. **Vectorization:** In the content-based approach, genres are tokenized and weighted using TF-IDF.
3. **Scoring:** * **Popularity:** Uses the formula  to calculate a robust popularity score.
* **Similarity:** Uses Cosine Similarity to find movies with overlapping genre profiles.


4. **Inference:** Call the `Recommend_Movie(user_id, ...)` function to get a list of the top 10 recommendations for any specific user.

## 📊 Sample Visualizations

The system provides graphical representations of a user's favorite genres, helping to visualize the underlying logic of the content-based recommendations.

---

*Developed as part of a movie analytics and recommendation study.*