# 🎬 Personalized Movie Recommendation System TCC

## 📖 Introduction
This project aims to develop a **Personalized Movie Recommendation System** using **machine learning, collaborative filtering, and content-based approaches**. 

---

## 📂 IMDb Dataset Processing

### ✅ **Datasets Used**
We utilized three official **IMDb datasets** from [IMDb Datasets](https://datasets.imdbws.com/):

1. **`title.basics.tsv`** – Contains movie metadata (title, genre, etc.)
2. **`title.ratings.tsv`** – Contains IMDb ratings (average rating, number of votes)
3. **`name.basics.tsv`** – Contains people (actors, directors) and their known movies

---

### 🔧 **Steps Taken**
#### **1️⃣ Data Loading**
- Loaded IMDb datasets using `pandas` in Python.
- Handled large files efficiently using `low_memory=False` and `na_values="\\N"` to replace missing values.

#### **2️⃣ Data Cleaning**
- **Removed unnecessary columns**:
  - `title.basics`: Kept `tconst`, `primaryTitle`, and `genres`
  - `title.ratings`: Kept `tconst` and `averageRating`
  - `name.basics`: Kept `nconst`, `primaryName`, and `knownForTitles`
- Converted `knownForTitles` (comma-separated movie IDs) into separate rows.

#### **3️⃣ Merging Datasets**
- **Merged `title.basics` (movies) with `title.ratings` (ratings)** using `tconst`.
- **Expanded `knownForTitles` in `name.basics`** to link actors & directors to movies.
- **Merged actors & directors into the final dataset** using `tconst`.

#### **4️⃣ Handling Missing Data**
- Some movies **had no associated actors/directors**.
  - **We keep them** with `NaN` values in `primaryName`

#### **5️⃣ Saving the Final Dataset**
- The final dataset was **saved as `merged_imdb_data.csv`**, ready for recommendation models.

---

## 📊 **Next Steps**
With the cleaned and merged dataset, we are ready to:
1. **Explore the data** (top-rated movies, genre distributions, most frequent actors/directors).
2. **Train a Movie Recommendation System**:
   - 🎭 **Content-Based Filtering** (Recommend movies based on genres)
   - 🤝 **Collaborative Filtering** (Recommend based on user preferences)
   - 🔄 **Hybrid Model** (Combines both approaches)
---

## 💡 **Technologies Used**
- 🐍 **Python**
- 📊 **Pandas**
- 🗄️ **IMDb Datasets**
- 🔢 **Machine Learning (Upcoming)**
