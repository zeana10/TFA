# Predicting movie ratings on IMDB from movie reviews using machine learning on historical data
-----------------------------------------------------------------------------------------------
## *Group - The Four Analyzers (TFA)*
### Contributors - Somanath Tripathy (st3187), Param Awasthi (pa2529), Ayushee Nigam (an2875), Zeana Kaynat (zk2219)
### *Section - 002*

Introduction
------------

IMDb, an acronym for Internet Movie Database, is an online database of information related to world films, television programs, home videos and video games, and internet streams, including cast, production crew, and personal biographies. It has approximately 5.3 million titles, 83 million registered users, and millions of reviews. Many of the reviews on the website have no ratings, and these reviews are not accounted for while calculating the mean ratings. Our dataset comprises of 25000 such reviews.

The objective of this project is to compute the ratings based on the reviews if the given reviewer has not rated the movie. This can also be used by IMDb to validate the scores given by a registered user based on their reviews.

Data Source
-----------

The dataset used in this project is a subset of the IMDb movie review dataset and has been obtained from this website - 
<http://ai.stanford.edu/~amaas/data/sentiment/> . A review comes from one of the eight categories (class label). In the data, class label represents rating given by the user along with the review. There are four files, which have been uploaded in the GitHub repository as mentioned in the **Files** section below, viz. i) Train text ii) Train labels iii) Test text iv) Test labels. Text files contain one review in each line and label files contain the corresponding rating. 

In the entire collection, no more than 30 reviews are allowed for any given movie because reviews for the same movie tend to have correlated ratings. Further, the train and test sets contain a disjoint set of movies, so no significant performance is obtained by memorizing movie-unique terms and their associated with observed labels.  In the labeled train/test sets, a negative review has a score <= 4 out of 10, and a positive review has a score >= 7 out of 10. Thus reviews with more neutral ratings are not included in the train/test sets.

Data Preprocessing and Cleaning
-------------------------------

We read the input data from the specified files using pandas. Then we merged the IMDb movie reviews & ratings data & cleaned the index names. We merged the train & test data. After merging we cleaned the table columns.


Preparing the Datasets for fitting the Model
--------------------------------------------

This step transforms the data into Series Object for model fitting. There are following substeps in this step:
Splitting the data into test and train dataset by using inbuilt train_test_split function by using 20% of the dataset as test data and rest as train data.
Encoding the data into series object to make it ready for fitting into model.


Fitting Different ML Models
---------------------------

After creating the required dataset, we have now started to fit it into different Machine Learning Models. We have also created a function, which fits the model as per requirement and predict the accuracy. The models are being fit into the dataset in following order:
1. Naive Bayes
2. Neural Network
3. Random Forest Classifier
4. XG Boost

**Naive Bayes**
  a) We have used TF-IDF vectorizer for word level, ngram level and character level featuring. Multiple iterations were done to find      best estimate parameters.
  b) We have also used count-vectorizer for feature vectoring.
	
These feature vectors were fit to find the accuracy in each case.

**Neural Network**
We have used TF-IDF vectorizer for word level, ngram level and character level featuring. Multiple iterations were done to find best estimate parameters.
These feature vectors were fit to find the accuracy in each case.

**Random Forest Classifier**
We have created a function to find the maximum parameters for maximum accuracy in tf-idf word level featuring. We found out maximum accuracy at 1000 features and implemented the RF classifier for that many features to find the accuracy.

**XG Boost**
We have taken the CPU count to utilize maximum CPU processing power, as this is very intensive algorithm. We have defined the classifier and set the parameters using grid search for XG Boost. We fitted the model to find best score, best parameter set and best estimator score.


Results
-------

We calculated the accuracy of our ratings predicted by different models. Giving the accuracy below for each model:
Naive Bayes:
  1. Word_level : 39.5%
  2. Character : 39%
  3. N_Gram : 37.7%
  4. Count Vectorizer: 38.9%
Neural Networks:
  1. Word_level : 20.2%
  2. Character : 20.2%
  3. N_Gram : 20.2%
Random Forest Classifier:
  1. Word_level : 33.3% (maximum at max_features=1000)
  2. Count Vectorizer: 32.4%
XG Boost:
     35.3% (maximum accuracy at learning_rate = 0.1, max_depth = 5, min_child_weight = 1 and best estimator score=0.349)


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
Refer <https://github.com/zeana10/TFA/blob/master/requirements.txt> for more information.

Run Instructions
----------------

1.In the requirements.txt file attached, check if all the packages are installed.
2.Go to <https://github.com/zeana10/TFA.git>
3.Go to Clone or Download. Download the zip file. From the multiple iPython notebooks, select the final merged source code–TFA_Project_IMDb_Rating_Prediction.ipynb.
4. Upload the file on Anaconda Jupyter Notebook. Change the path in the pandas.read_table function for both test and train data.
5. Open the file and run all the individual cells of the file in an ordered fashion.
  
Bibliography
------------ 
_Maas-EtAl:2011:ACL-HLT2011_ <http://ai.stanford.edu/~amaas/papers/wvSent_acl2011.bib>
