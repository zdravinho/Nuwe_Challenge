# Nuwe_Challenge
➡️ Context:
Welcome to the Lights, Camera, Action Challenge! 🌟🎥 In this thrilling competition, you will dive into the world of movies and TV shows, predicting the IMDB score classes like a seasoned film critic. The IMDB score is a well-established metric in the film industry, serving as a barometer for a title's quality. Ready for your close-up? Let's roll!

✍️ Dataset:
For this challenge, you will have 4 csv files: train_titles.csv, train_credits.csv, test_titles.csv, and test_credits.csv.

In train_titles.csv and test_titles.csv, each row is a unique title, with the following scenes:

id: A unique identifier for each title.
title: The name of the title.
type: The type of the title (e.g., movie, show).
description: The synopsis of the title.
release_year: The year the title was released.
age_certification: The age certification of the title.
runtime: The runtime of the title.
seasons: The number of seasons (relevant for shows).
genres: The list of genres of the title.
production_countries: The list of countries where the title was produced.
streaming: The streaming platform offering the title.
imdb_votes: The number of IMDB votes the title has received.
The train_titles.csv file also includes:

imdb_score: The IMDB score of the title.
target: The score class of the title. This is the transformation of the IMDB score using the following method:
def get_imdb_score_class(score):
  if score < 2:  # 1 <= score < 2
    return 0
  elif score < 3:
    return 1
  elif score < 4:
    return 2
  elif score < 5:
    return 3
  elif score < 6:
    return 4
  elif score < 7:
    return 5
  elif score < 8:
    return 6
  elif score < 9:
    return 7
  else:  # 9 <= score <= 10
    return 8

# Using pandas apply method
train_titles['target'] = train_titles['imdb_score'].apply(get_imdb_score_class)
The train_credits.csv and test_credits.csv files are your supporting cast, providing extra information about the actors and directors of each title:

id: The identifier of the title, corresponding to the id in the titles datasets.
person_id: A unique identifier for each person.
name: The name of the person.
character: The name of the character played in the film.
role: The role of the person (e.g., actor, director).
Although adding the titles credits information can boost your model performance, it is not required to use the credits datasets.

🎯 Objectives and tasks:
Your only objective is:

Predicting the IMDB score for the test titles.
Please note that your model should predict the IMDB score, and then transform this score into the target column using the get_imdb_score_class function provided.

✍️ Evaluation & submission format
Your performance will be judged using the F1 macro score with the target column.
