# Predicting movie ratings on IMDB from movie reviews using machine learning on historical data
-----------------------------------------------------------------------------------------------
## *Group - The Four Analyzers (TFA)*
### Contributors - Somanath Tripathy (st3187), Param Awasthi (pa2529), Ayushee Nigam (an2875), Zeana Kaynat (zk2219)
**Section - 2**

Introduction
------------

IMDb, an acronym for Internet Movie Database, is an online database of information related to world films, television programs, home videos and video games, and internet streams, including cast, production crew, and personal biographies. It has approximately 5.3 million titles, 83 million registered users, and millions of reviews. Many of the reviews on the website have no ratings, and these reviews are not accounted for while calculating the mean ratings. Our dataset comprises of 25000 such reviews.

The objective of this project is to compute the ratings based on the reviews if the given reviewer has not rated the movie. This can also be used by IMDb to validate the scores given by a registered user based on their reviews.

Data Source
-----------

The dataset used in this project is a subset of the IMDb movie review dataset and has been obtained from `this website
<http://ai.stanford.edu/~amaas/data/sentiment/>`_ . A review comes from one of the eight categories (class label). In the data, class label represents rating given by the user along with the review. There are four files, which have been uploaded in the GitHub repository as mentioned in the **Files** section below, viz. i) Train text ii) Train labels iii) Test text iv) Test labels. Text files contain one review in each line and label files contain the corresponding rating.


Files
-----
In the Github, we have the following files to be downloaded:

Input Files: 
  - imdb_test_text.txt
  - imdb_test_labels.txt
  - imdb_train_text.txt
  - imdb_train_labels.txt
  
Source Code:
  - TFA_Project_IMDb_Rating_Prediction.ipynb

Requirements:
  - requirements.txt -- specifies which packages to be installed and imported
