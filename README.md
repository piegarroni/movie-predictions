# Movie-predictions-CNN


link for subtitles and (imdb) meta data: https://www.kaggle.com/datasets/adiamaan/movie-subtitle-dataset?select=movies_meta.csv
link for rotten tomatoes data: https://www.kaggle.com/datasets/stefanoleone992/rotten-tomatoes-movies-and-critic-reviews-dataset

## Hypothesis:

The hypothesis of this experiment is: to what extent the subtitles of a movie predict the critique's score?

The hypothesis is tested by training a DecisionTree on the IMDB metadata, the CNN output vector and on the prediction of a language model.

## Method

the first step consists in creating a baseline, which is a DecisionTree classifier that predict the movie score uniquely by its metadata (genre, year, title...).

The second step is to predict the rotten tomatoes status with a GPT language model.

The third step is to obtain the semantic matrices for the movies and train a CNN to extract the features.

the fourth step consists in combining the baseline with the data obtained by the neural networks.


### CNN Method:

#### Step 1:

the imdb dataset and the rotten tomatoes dataset were combined, selecting only certain genres and certain years to reduce as much as possible external variables

#### Step 2:

The subtitles of every movie was cleaned and normalized.

#### Step 3: 

The semantics vectors for every chunk were retrieve of every movie with GPT-2

#### Step 4: 
 
for every movie, a matrix containing the semantic vectors was created. example of matrix:

![Screenshot](images/matrix.png)

#### Step 5

CNN was trained on the matrices to predict the tomatometer. The structure of the model is: 

![Screenshot](images/structure.png)




The csvs were note uploaded to the GitHub repo because the dimension of some files is too large.

