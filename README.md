# Movie Recommendation Methods  

## Overview  
This repository explores the implementation of **recommender system methods** on a movie dataset. The main focus is on applying **Collaborative Filtering** and **Matrix Factorization** techniques to predict user preferences and generate recommendations.  

📌 *Note: This project was provided by the university as part of the coursework to understand the fundamentals of recommender systems. It is an educational exercise, not a production system.*  

The project was developed as part of the **Recommender Systems course** in the Master’s in Business Analytics at the **Pontificia Universidad Católica de Chile (MANE 2025)**.  

---

## Dataset  
The dataset consists of:  
- **User ratings** for movies (on a 1–5 scale).  
- **Movie metadata** such as:  
  - Genres (binary encoded: 1 if the movie belongs to a genre, 0 otherwise).  
  - Release year (movies span from **1922 to 1998**, with most concentrated between 1950–1960).  
  - IMDb links and other descriptive fields.  

**Examples:**  
- *Toy Story (1995)* → Animation, Children, Comedy  
- *Star Wars*, *Fargo*, *Return of the Jedi* among the most frequently rated movies.  

---

## Exploratory Analysis  
Before implementing models, the dataset was explored to understand its structure and distribution:  

- **Ratings distribution**: Most users rate only a few items, while a small fraction of users provide hundreds of ratings.  
- **Movie popularity**: Some films receive hundreds of ratings, while many have very few (long-tail distribution).  
- **Temporal trends**: Rating patterns change with movie release years.  

These findings highlight two classic recommender system challenges:  
- **Cold Start Problem** – new users with very few ratings cannot be effectively recommended.  
- **New Item Problem** – new movies without ratings cannot be recommended until interactions are collected.  

---

## Methods Implemented  

### 1. Collaborative Filtering (KNN-based)  
- Uses **user–item rating interactions** to find similarities.  
- Implemented with both **User-based KNN** and **Item-based KNN**.  
- Similarity metrics tested: **Cosine similarity** and **Pearson correlation**.  
- Implemented using the **Surprise library** (`KNNBasic`).  

### 2. Matrix Factorization (SVD)  
- Approximates the user–item rating matrix using two lower-dimensional matrices:  
  - **User latent vectors**  
  - **Item latent vectors**  
- Learns hidden features of users and movies that explain rating patterns.  
- Implemented using the **Surprise library** (`SVD`).  
- More efficient for larger datasets compared to pure collaborative filtering.  

---

## Evaluation  

The models are evaluated using standard error metrics:  
- **RMSE (Root Mean Square Error)** – penalizes larger errors more strongly.  
- **MAE (Mean Absolute Error)** – average absolute difference between predicted and actual ratings.  

**Key findings:**  
- Increasing the number of neighbors (K) reduces error up to a point, but too many neighbors lead to **underfitting**.  
- Very small K values cause **overfitting**, making the model too sensitive to noise.  
- Matrix factorization provides lower error and better scalability.  

---

## Future Work  
- Incorporate **context-aware recommendation methods** (e.g., using movie metadata such as genres, release year).  
- Experiment with **hybrid recommenders** combining collaborative and content-based methods.  
- Explore more advanced techniques (e.g., **Neural Collaborative Filtering, Deep Learning-based models**).  

---

## License  
This project is for **educational purposes** as part of my coursework. Some materials are adapted from university resources (MANE), others were developed independently.  

---

## Tools and Libraries  
- **Python 3**  
- **Surprise** – for collaborative filtering and matrix factorization methods  
- **Pandas, Numpy** – for data processing  
- **Matplotlib** – for visualizations  

---

## Usage  

1. Clone this repository:  
   ```bash
   git clone https://github.com/your-username/movie-recommender.git
   cd movie-recommender


## Install dependencies  

```bash
pip install -r requirements.txt

---

## 3. Run the notebooks to explore the dataset and train models  

```bash
jupyter notebook

