# Cooking Prediction Kaggle

Author: Zihan Qu

Email: ziqu@ucsd.edu

username (team name) in Kaggle: 404

PID: A15446332

## Submitted Files: 

- predictions_Made, predictions_Minute, predictions_Rate are files that predict whether the user cook the recipe, the time that the recipe consumes, and the rate of recipe that the user commented. 

****
# Task 1

**Steps implements as follows:**
- loop through the train dataset and find the appear time of each recipe
- ranking them from large to small
- through the negative (created) and positive valid set, plot all threshold and find the best
- set a threshold that found as 0.695 of the whole word set which is the best threshold for current model
- implement Jaccard sim, and set maxsim threshold as more than 0.015
- find similarity to those valid set, if they satisfies above standard, then, marks as 1, else 0. 
- set the satisfaction as or when print label

In this task, I also try to implement Beyasian Personalized Ranking, 
but the performance is little bit worse than above method, 
so the final result did not include this way. 


****

# Task 2

**Steps implements as follows:**
- set bow punctuation as sp
- create a count word set and rank them from more to less when remove the punctuation from each steps

**implement TF-IDF:**
- create a df set with remove puntuation and count frequency of each word
- set a dictionay size as 2600, which [2500, 2600] is good
- let words set be those first 2600 words in the count set
- set wordID and wordSet
- set tf is 1 for each word without punctuations in steps 
- for each existed word in df, calculate: 
tf_idf = tf[w] * math.log2(len(data) / df[w]) for w in words
- initialized def feature(datum) with a empty feat in the function and set feat[wordID[w]] = tf_idf
- feat append 1, len("steps"), len("ingredients")
- implement hw3 solution code for initialized X for feature(data[i]) for i in range(len(data))
- Train used linear_regression
- report MSE as 2733







