
![cover_photo](./README_files/26brooksWeb-superJumbo.jpg)
# What is Dr.Peterson Saying?

*Jordan Peterson is a prolific psychology professor who has gained an audience in the millions in recent years. His writings, interviews and lectures cover a wide range of topics, including morals and ethics, psychology, religions, politics, education and many others. This data science project aims to parse a large enough sample of his corpus to derive an intelligible summary of the different topics Dr. Peterson discusses using Scikit-learn’s Tfidf Vectorization, K-means modeling, and Gensim’s Latent Dirichlet Allocation modeling.*

## Reference

I learnt a great deal about topic modeling with humanities text from this youtube channel called [Python Tutorials for Digital Humanities](https://www.youtube.com/@python-programming/)

## 1. Data Source

This data for this project comes from Dr. Jordan Peterson’s official website. I used all the transcripts available on the website as of July 31st, 2023. These transcripts are from interviews conducted and given by Dr. Peterson, as well as public lectures. Due to difficulty in dealing with copyright materials, Dr. Peterson’s published books are not included. But I think this actually helps with the uniformity of the data, since most written material are structured differently than spoken material.

> * [Jordan Peterson's Official Website](https://www.jordanbpeterson.com)


## 2. Data Cleaning

* Once the data is downloaded as text files from the website. I manually cleaned the text to ensure only words spoken by Dr. Peterson are included.
* The rest of the cleaning process includes the fairly standard procedure of removing the stop words, using all lower case, and lemmatization.
* After some initial modeling, the text files are sample to detect any peculiarities. Contractions and special characters are further removed.

## 3. Exploratory Data Analysis:

Before we apply any modeling, we need to break down the text files into smaller data points. The first strategy is simply break the text files down into smaller documents that each contains 25 sentences. We will first use this strategy on the sample data, and then try other text partition methods that might improve the data modeling.

## Modeling

[Data Cleaning Report](https://drive.google.com/open?id=195wcooDtT2XhfpRXREWmLovm8XZPNymy)

In a collaborative-filtering system there are only three columns that matter to apply the machine learning algorithms: the user, the item, and the explicit rating (see the example matrix above). I also had to clean & normalize all the reference information (location, difficulty grade, etc.) to the route so that my user could get a useful and informative recommendation.

* **Sklearn.Tfidf and KNN clustering:**
  1. We use Sklearn’s Term Frequency Inverse Document Frequency to vectorize the document list.
  2. We then use K means to cluster the documents and try to use the keywords to guess what each cluster could possibly mean.
  3. We play around with the K value, while checking both the keywords compositions and their corresponding 2D PCA plot to derive the best topic identification and separation.
  4. We use the “Elbow Method”, plotting the within-cluster-sum-of-squares against the number of potential clusters to find the possible optimal number of clusters.
  5. We plot the silhouette score against different number of clusters.

* **Advanced Topic Modeling:**
    1. This project will further explore topic modeling using Latent Dirichlet Allocation to see if better interpretable results can be produced.
