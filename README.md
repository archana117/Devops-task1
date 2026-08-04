# Twitter Dataset Analysis using TF-IDF, K-Means Clustering, and t-SNE Visualization

## Project Overview

This project performs text mining and visualization on a Twitter dataset. It preprocesses tweet text, converts it into numerical vectors using TF-IDF, groups similar tweets using K-Means clustering, and visualizes tweet clusters using t-SNE. In addition, the project generates several statistical visualizations to understand user activity, engagement, and tweet content.

---

# Objectives

- Clean and preprocess tweet text.
- Convert textual data into TF-IDF feature vectors.
- Cluster similar tweets using K-Means.
- Reduce high-dimensional text features into 2D using t-SNE.
- Visualize tweet clusters.
- Analyze likes, retweets, user activity, and monthly tweet trends.
- Generate a Word Cloud and identify the most frequent words.

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- WordCloud
- Regular Expressions (re)

---

# Required Libraries

Install all dependencies before running the project.

```bash
pip install pandas numpy matplotlib seaborn scikit-learn wordcloud
```

---

# Dataset

Input Dataset:

```
twitter_dataset.csv
```

Expected columns:

- Text
- Username
- Likes
- Retweets
- Timestamp

---

# Project Workflow

## Step 1: Import Libraries

Import all required Python libraries for:

- Data manipulation
- Visualization
- Machine Learning
- Text Processing

---

## Step 2: Load Dataset

```python
df = pd.read_csv("twitter_dataset.csv")
```

The dataset is loaded into a Pandas DataFrame.

---

## Step 3: Text Preprocessing

Each tweet is cleaned by:

- Converting to lowercase
- Removing URLs
- Removing usernames (@username)
- Removing hashtags (#)
- Removing special characters
- Removing numbers
- Keeping only alphabetic words

Example:

Before:

```
Love AI!! Visit https://abc.com #AI @OpenAI
```

After:

```
love ai visit ai
```

The cleaned tweets are stored in:

```
clean_text
```

---

## Step 4: TF-IDF Vectorization

Tweets are converted into numerical vectors using:

```
TfidfVectorizer(max_features=2000)
```

Output:

```
Sparse Matrix
```

Shape:

```
(Number of Tweets × 2000 Features)
```

---

## Step 5: K-Means Clustering

Tweets are grouped into

```
5 clusters
```

using

```
KMeans
```

Each tweet receives a cluster label.

New column:

```
cluster
```

---

## Step 6: Sampling

Since t-SNE is computationally expensive,

A maximum of

```
2000 tweets
```

are randomly selected.

---

## Step 7: t-SNE Dimensionality Reduction

The TF-IDF vectors are reduced from thousands of dimensions to

```
2 Dimensions
```

using

```
TSNE
```

Parameters:

- n_components = 2
- perplexity = 30
- learning_rate = 200
- random_state = 42

Output:

```
x
y
```

coordinates for each sampled tweet.

---

# Visualizations

The project generates the following visualizations.

---

## 1. t-SNE Scatter Plot

Displays tweet clusters in 2D space.

Color indicates cluster membership.

---

## 2. Cluster Visualization with Usernames

Displays:

- Tweet clusters
- Username labels
- Cluster separation

---

## 3. Likes Distribution

Histogram showing:

- Tweet likes
- Frequency distribution
- KDE curve

---

## 4. Retweet Distribution

Histogram showing retweet frequency.

---

## 5. Top Active Users

Bar chart showing

Top 10 users with the highest number of tweets.

---

## 6. Cluster Distribution

Pie chart showing percentage of tweets in each cluster.

---

## 7. Word Cloud

Visual representation of the most frequent words appearing in tweets.

---

## 8. Top 15 Frequent Words

Bar chart showing the fifteen most common words after preprocessing.

---

## 9. Monthly Tweet Activity

Line chart showing the number of tweets posted each month.

Timestamp is converted into datetime format before analysis.

---

## 10. Likes by Cluster

Box Plot comparing likes received by tweets belonging to different clusters.

---

# Output Files

Generated Output:

```
twitter_tsne_output.csv
```

Contains:

- Original tweet
- Cleaned tweet
- Cluster label
- t-SNE X Coordinate
- t-SNE Y Coordinate

---

# Machine Learning Techniques Used

## TF-IDF

Converts textual tweets into numerical vectors by considering the importance of words.

---

## K-Means Clustering

Groups similar tweets into clusters without using labels.

Number of clusters:

```
5
```

---

## t-SNE

Reduces high-dimensional TF-IDF vectors into two dimensions while preserving local similarities for visualization.

---

# Project Structure

```
Twitter-TSNE-Analysis/

│
├── twitter_dataset.csv
├── TSNE.ipynb
├── twitter_tsne_output.csv
├── README.md
```

---

# Expected Output

The project produces:

- Cleaned tweet dataset
- TF-IDF feature matrix
- K-Means cluster labels
- 2D t-SNE visualization
- User cluster visualization
- Likes distribution
- Retweet distribution
- Top active users chart
- Cluster distribution pie chart
- Word cloud
- Top frequent words chart
- Monthly tweet activity graph
- Likes by cluster box plot
- Output CSV containing cluster assignments and t-SNE coordinates

---

# Applications

This project can be used for:

- Social Media Analytics
- Trend Analysis
- Community Detection
- User Behavior Analysis
- Topic Discovery
- Marketing Analytics
- Public Opinion Analysis
- Twitter Data Mining
- Data Visualization
- Machine Learning Education

---

# Future Improvements

- Sentiment Analysis
- BERT or SentenceTransformer embeddings
- UMAP visualization
- Interactive Plotly dashboards
- Automatic cluster labeling
- Topic modeling using LDA
- Real-time Twitter API integration
- Deep learning-based tweet embeddings

---

# Author

Developed as a Machine Learning project demonstrating text preprocessing, unsupervised learning, dimensionality reduction, and data visualization techniques using Python.
