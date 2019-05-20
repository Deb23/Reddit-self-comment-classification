# Reddit-self-comment-classification
Classification of Reddit comments into their respective subreddits

# About the Dataset
The data was downloaded from one of the published Kaggle datasets - https://www.kaggle.com/mswarbrickjones/reddit-selfposts

The Kaggle data-set consists of 1.013M self-posts, posted from 1013 subreddits (1000 examples per class). For each post we give the subreddit, the title and content of the self-post. A manual annotation of about 3000 subreddits have also been provided, which went into the creation of this dataset, in subreddit_info.csv, this was the main criteria for selecting which subreddits went into this dataset. A top-level category and subcategory for each subreddit is included, and a reason for exclusion if this does not appear in the data. The last 20% of the data has been organised so that this is a random, stratified sample of all the data and will be used as a test set.

Since the data was too big to be processed without a GPU, for this analysis I sub sampled the data (both train and test) for only the following 10 subreddits chosen at random:
everquest, psychotherapy, ShieldAndroidTV, twentyonepilots, teslore, gopro, uBlockOrigin, dwarffortress, HongKong, araragi

# Goal of the analysis

1. Text Preprocessing (tokenization, removal of special character, digits and additional white spaces, stopword removal, lemmatization)
2. Feature Extraction (using bag-of-words model - TF-IDF with unigrama and Bi-gram)
3. Model Generation : 3 types of classification models have been tried i.e. Multinomial Naive Bayes, Support Vector Machine and Random Forest.
4. Test Data classification
5. Model validation (metric used - accuracy)

# Outcome of classification

Based on the analysis done, Multinomial Naive Bayes and Random Forest (tested for optimized parameter using Grid Search) gave the best results. Ultimately the best accuracy (95.3%) was given by a simple Multinomial Naive Bayes model with alpha = 0.1
