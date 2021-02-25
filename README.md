# Capstone Project: Spotify Popularity Prediction And Recommender

General Assembly DSI 19 Capstone Project Adrian Teng

## Project Introduction

1. Using the Spotify datas from kaggle 'data.csv' that contains more than 175k songs collected from Spotify Web API.
2. Coming out with a recommender with 'data.csv' and 'data_genre' from the same source. 

## Problem Statement 

Music have been revolving around life in many different events. An event company hopes to come out with albums that matches their theme of event and keeping the similarities of each song tightly. Especially, during this period of time, when live performance is not allowed due to pandemic and using music playlist will be the most optimal choice.

The goal of this project is to come out with a recommender that will recommend song with similar attributes from Spotify and also find out which model will be best to predict the popularity of a song.

## Executive Summary

In this project, it is splitted into three parts respectively:

1. [EDA](code/01_eda.ipynb)
2. [Modelling](code/02_modelling.ipynb)
3. [Clustering and Recommender](code/03_clustering_recommendation.ipynb)

In the first notebook, 01_eda, exploration was done to better understand the data that will provide assistance in the other two notebooks. 

In the second notebook, 02_modelling, Recursive Feature Elimination to do feature selection and gridsearch was done in another notebook to save time for the regression model to predict and find the casual effect relationship between variables. 

Regression Models: Linear Regression, RandomForestRegressor, AdaBoostRegressor, DecisionTreeRegressor will be used for accessment with the pre-processed data. They are also tested for R2-score, mean_squared_error, mean_absolute_error. 

In the third notebook, 03_clustering_recommender, data was regrouped and merged between 'data.csv' and 'data_gen.csv' to fulfill the recommender. TSNE AND PCA on Kmeans to run clustering, clustered by 10 and comapared with the top 10 genre. A recommender was coded to filter by the songs parameters and decades to fulfill the problem statement.


## Datasets and data dictionaries

The dataset is split into 2 files:
1.data.csv
2.data_genre.csv

The datas are scraped from Spotify API from kaggle.

- duration_ms - The duration of the track in milliseconds.
key - The estimated overall key of the track. Integers map to pitches using standard Pitch Class notation . E.g. 0 = C, 1 = C♯/D♭, 2 = D, and so on. If no key was detected, the value is -1.

- mode - Mode indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived. Major is represented by 1 and minor is 0.

- acousticness - A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic.

- danceability - Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable.

- energy - Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, while a Bach prelude scores low on the scale. Perceptual features contributing to this attribute include dynamic range, perceived loudness, timbre, onset rate, and general entropy.

- instrumentalness - Predicts whether a track contains no vocals. “Ooh” and “aah” sounds are treated as instrumental in this context. Rap or spoken word tracks are clearly “vocal”. The closer the instrumentalness value is to 1.0, the greater likelihood the track contains no vocal content. Values above 0.5 are intended to represent instrumental tracks, but confidence is higher as the value approaches 1.0.

- liveness - Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live. A value above 0.8 provides strong likelihood that the track is live.
loudness - The overall loudness of a track in decibels (dB). Loudness values are averaged across the entire track and are useful for comparing relative loudness of tracks. Loudness is the quality of a sound that is the primary psychological correlate of physical strength (amplitude). Values typical range between -60 and 0 db.

- speechiness - Speechiness detects the presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audio book, poetry), the closer to 1.0 the attribute value. Values above 0.66 describe tracks that are probably made entirely of spoken words. Values between 0.33 and 0.66 describe tracks that may contain both music and speech, either in sections or layered, including such cases as rap music. Values below 0.33 most likely represent music and other non-speech-like tracks.

- valence - A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).

- tempo - The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration.

- id - The Spotify ID for the track.

- popularity - The popularity of the track. The value will be between 0 and 100, with 100 being the most popular. The popularity is calculated by algorithm and is based, in the most part, on the total number of plays the track has had and how recent those plays are. Generally speaking, songs that are being played a lot now will have a higher popularity than songs that were played a lot in the past. Artist and album popularity is derived mathematically from track popularity. Note that the popularity value may lag actual popularity by a few days: the value is not updated in real time.



## Conclusion

- In modelling i believe alot more can be done to improve the prediction as the song atrributes may not be the only factors that contribution to the song to be popular or not. For example, song lyrics it may be another reason for a song to be popular.

- When doing the recommender, we can see that songs from the popular artists, songs are naturally more popular than those with the same attributes as well. 

- Tsne have higher sihoulette score but it takes very to run for huge datasets and also treat outliners more effectively. 

- The smaller the clusters, the higher the silhouette score, which also mean that cohension will be lower and separation higher.

- Kmean and Cosine are naturally different calculate differently, but majority of the songs predicted are similar.



