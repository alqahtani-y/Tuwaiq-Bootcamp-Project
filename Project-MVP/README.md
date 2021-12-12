# Preliminary data analysis and baseline classifiers results

### Introduction

Parts of EDA were presented on one multi-domain dataset in MSA (resturants, products, movies, hotels), followed by few primary experiments using basline classifiers.
Below is a summary of work and findings (details and charts in [MVP notebook](https://github.com/alqahtani-y/Tuwaiq-Bootcamp-Project/blob/main/Project-MVP/mvp_submit.ipynb))

### Dataset analysis:

The number of reviews after execluding the neutral class:
* Resturants    10705
* Products      3964
* Hotels        13422
* Movies        1353
* **TOTAL         29444**

The data was found to be **imbalanced** in all domains, with a general ratio of **0.776899 positive** and **0.223101 negative** on the whole dataset.
Therfore, accuracy will not be the best metric for evaluation.
Since both classes have similar importance to the sentiment classification task, **F1-score** will be the best choice.

### Pre-processing:

* Remove unwanted parts (Tashkel, URLs, punctuations, numbers and english letters)
* Remove Arabic stopwords (amonge 234110 unique words in all domains, 86329 were removed)
* Normalization.
* Stemming (light)

### More information in the notebook..

* Reviews length (number of words) in Histogram for each domain.
* Top 20 words in Bar chart for each domain.
* Wordclouds of top 500 words in each domain.

### Experiments:

Many experiments with different settings on each domain, as follows:
* Preprocessing:
  * With stemming
  * Without stemming
* Features:
  * Uni-grams
  * Uni-grams and bi-grams
* Vectorizers:
  * Count
  * Tf-idf
* Classifiers
  * Linear Support Vector Classification
  * C-Support Vector Classification

**Max F1-score results:**

* Resturants
  * no stemming  0.917 (Tfidf on uni-grams and bi-grams : linear SVM)
  * stemming     0.922 (Tfidf on uni-grams and bi-grams : linear SVM)           
* Products
  * no stemming  0.913 (Tfidf on uni-grams and bi-grams : linear SVM)
  * stemming     0.910 (Tfidf on uni-grams and bi-grams : linear SVM)         
* Hotels
  * no stemming  0.972 (Tfidf on uni-grams : linear SVM)
  * stemming     0.972 (Tfidf on uni-grams and bi-grams : linear SVM)          
* Movies
  * no stemming  0.896 (Count on uni-grams and bi-grams : linear SVM)
  * stemming     0.895 (Tfidf on uni-grams : linear SVM)

**Discussion**

* Reviews on **hotels** get the highest result while reviews on **movies** get the lowest among domains,
although hotels domain has higher **imbalance** (0.802786 vs 0.197214) than movies (0.716186 vs 0.283814).
However, if we go back to the **size** of data, we can see that hotels domain is far away larger (13422 reviews) than movies domain (1353 reviews)!

* Light stemming has no impact on the conducted experiments.

* Linear SVM using Tfidf on uni-grams and bi-grams gave the best results in almost all domains.
