# Distractor_Generation
Distractor generation for MCQs on english essays
This file consists of python code to generate distractors for MCQs for english essays

<br> Distractors are the options given in MCQs other than the correct answer text.

<br> In this project we train the data having columns question, answer_text and distractor. We need to predict the distractors for any newly gven question and answer text.

## Preprocessing Steps
1. removed all special symbols of all the columns
2. replaced 'nt with nt
3. replaced missing values with empty strings

## Featurization
This problem can be viewed as classification task where the target variable will be 1 for the distractors and 0 for all other options for other questions.
1. The text is featurized using word2vec model
2. many other features are used like, number of words, length of the string, common words between ques/distractor and answer_distractor etc
3. Fuzzy features from fuzzywuzzy library are also used.

## Model
XGBoost classifier has been used for this problem.

## Extensions
When we classiy the distractors, we get lot of options, if we need furthur to rank these options we can use the pairwise distances of each of these options and the answer to get more fine tuned results.

