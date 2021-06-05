# Hotel-Recommendation
Hotel Recommendation


# Table of Contents
1. [Introduction](#introduction)
2. [Data Background](#data-background)
3. [Prerequisite](#prerequisite)
4. [Project Status](#project-status)
5. [Versioning](#versioning)
6. [Authors](#authors)
7. [Acknowledgement](#acknowledgement)
8. [Reference](#reference)

## Introduction
All online travel agencies are scrambling to meet the Artificial Intelligence driven personalization standard set by Amazon and Netflix. In addition, the world of online travel has become a highly competitive space where brands try to capture our attention (and wallet) with recommending, comparing, matching, and sharing. For this assignment, we aim to create the optimal hotel recommendations for Expedia’s users that are searching for a hotel to book. For this assignment, we need to predict which “hotel cluster” the user is likely to book, given his (or her) search details. In doing so, we should be able to demonstrate our ability to use four different algorithms (of your choice). The data set can be found at Kaggle: Expedia Hotel Recommendations. To get you started, we should use train.csv which captured the logs of user behavior and destinations.csv which contains information related to hotel reviews made by users. We are also required to write a one page summary of the approach in getting to the prediction methods. We will use a combination of R and Python in answer.

[back to top](#table-of-contents)
## Data Background
Expedia has provided logs of customer behavior. These include what customers searched for, how they interacted with search results (click/book), whether or not the search result was a travel package. The data in this competition is a random selection from Expedia and is not representative of the overall statistics.

Expedia is interested in predicting which hotel group a user is going to book. Expedia has in-house algorithms to form hotel clusters, where similar hotels for a search (based on historical price, customer star ratings, geographical locations relative to city center, etc) are grouped together. These hotel clusters serve as good identifiers to which types of hotels people are going to book, while avoiding outliers such as new hotels that don't have historical data.

Goal is to predict the booking outcome (hotel cluster) for a user event, based on their search and other attributes associated with that user event.

The train and test datasets are split based on time: training data from 2013 and 2014, while test data are from 2015. The public/private leaderboard data are split base on time as well. Training data includes all the users in the logs, including both click events and booking events. Test data only includes booking events. 

destinations.csv data consists of features extracted from hotel reviews text. 

Note that some srch_destination_id's in the train/test files don't exist in the destinations.csv file. This is because some hotels are new and don't have enough features in the latent space. Your algorithm should be able to handle this missing information.

[back to top](#table-of-contents)
## Prerequisite
You will need the following applications to execute this project-

* Python 3 (or Anaconda distribution with Python 3)
* Jupyter or any other notebook
* Seaborn and sklearn package and other basic packages.

[back to top](#table-of-contents)

## Project Status
Completed modeling using 4 different methods \
[back to top](#table-of-contents)

## Versioning
Git is used for project versioning. \
[back to top](#table-of-contents)

## Authors
Shani Kumar \
[back to top](#table-of-contents)

## Acknowledgement
1. **Support Vector Machine (SVM)** Support Vector Machines (SVMs) is good at finding pairwise interactions in data, so I through it should be good at recommending a hotel cluster to a certain user. Though natively, they don’t support multiclass classification, there are techniques we can use to it viably classify one out of 100 hotel clusters.

The benefit is that we can capture much more complex relationships between the datapoints without having to perform difficult transformations on our own. The downside is that the training time is much longer as it's much more computationally intensive. It provided highest & best cross validation score.

2. **Naive Bayes classifier** Naive Bayes is a relatively simple classifier that can natively be run on multiclass data, so I thought at least try this type of classifier and see what kind of results we get initially.
But it has the worst performance of the four models. Therefore, this classifier is not recommended for the problem at hand.
3. **Logistic Regression** We chose to test Logistic Regression because it was a simple model we learned in class that can handle non-linear decision boundaries, which we were clearly dealing with.
Logistic Regression was close to the performance of SVM but slightly worse.
4. **K-Nearest Neighbor classifier** KNN was a good simple model to try because it ‘trains’ very quickly by offsetting most of the computation to the actual testing portion. Additionally it is relatively intuitive how the model works.
5. **Random Forest classifier** One of the largest weakness of Random Forest Classifiers is large class imbalances. In addition with many classes, the decision trees become very deep and complex which goes against the marginal differences that RF averaging is going for.
KNN performed very similar to Logistic Regression for the model in question but it was much faster than Logistic Regression. \
[back to top](#table-of-contents)

## Reference
https://www.kaggle.com/c/expedia-hotel-recommendations/data

[back to top](#table-of-contents)
