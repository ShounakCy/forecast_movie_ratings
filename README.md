# Movie Rating Case

![Sample poster](sample_posters/0.jpg) ![Sample poster](sample_posters/1.jpg) ![Sample poster](sample_posters/2.jpg)

# Introduction

Executives in the movie industry are curious about the potential of machine learning to predict the success of movies before they are made.

We provide a curated sample of a movie dataset that contains information about roughly 10000 movie titles with features including actors, crew, movie poster, tagline, and more.

Your task is to *predict movie ratings* from different modalities of input features, namely

- Categorical & numerical
- Text
- Image

# Src

- [main.ipynb](src/main.ipynb)

# Results

- [RESULTS](RESULTS.md)


# Data

## Summary

All data can be found under `data/filtered`. You are free to load it as you wish. The data is provided as

- Tabular data in .csv files:
  - [actors.csv](data/filtered/actors.csv): the *actors* that are credited in the movies
  - [directors.csv](data/filtered/directors.csv): the *directors* are credited in the movies
  - [movies.csv](data/filtered/movies.csv): movies along with some metadata, including the `rating` variable
  - [studios.csv](data/filtered/studios.csv): the studio(s) that produced the movies
- a [zipped file with posters](data/filtered/posters/posters.zip) - for each movie with a given `movie_id`, there is an image in the archive with the name `{movie_id}.jpg`.
- Pre-computed embeddings for poster, tagline and description data (more information below)

N.b. the column `original_movie_id` exists to preserve a key to the original dataset. You do not need to use it.

## Pre-computed embeddings

If you have limited computational resources at your disposal, processing images and text can be difficult. We therefore provide pre-computed embeddings for the poster, `tagline` and `description` features.

- The image embeddings have been generated using [OpenAI's CLIP model](https://huggingface.co/openai/clip-vit-base-patch32)
- The text embeddings have been generated using Nomic's [nomic-embed-text-v1.5](https://huggingface.co/nomic-ai/nomic-embed-text-v1.5)

If you choose to use these embeddings in your model(s), we expect that you possess a basic understanding of how the models that produced them work.

The embeddings provided as numpy arrays with shape `(n_movies, embedding_size)`. They can be loaded into memory using

```
import numpy as np
poster_embeddings = np.load("data/filtered/poster_embeddings.npy")

# To get the embedding for a particular movie:
poster_embeddings[movie_id]
```

# Tasks

**N.b.** you are not expected to spend more than 3-4 hours on this case. We recognize there may not be enough time to cover all tasks in depth. You are free to prioritize the tasks as you deem appropriate and leave some unfinished. Be prepared to reason about any omitted tasks and your rationale for omitting them.

1. Load the dataset.
2. Select the appropriate features to use in your model.
3. Perform preprocessing and cleaning steps of your choice.
4. Model training
    - Train separate models on one or more of the three different modalities (categorical/numerical, text, images) to predict the `rating` property. One modality per model. Choose methods / architectures you find suitable.
    - Validate your models’ performance in terms of predictive accuracy and generalizability and compare them. You are free to choose relevant metrics for this task.
5. If you have trained multiple models: combine them or train a new one, to predict `rating` using different modalities of input features. Validate the combined model’s performance.
6. Present your code, descriptive analysis, and model performance, for example, in  a Jupyter notebook.

## Optional questions

- Given a movie of your choice, can you modify some aspect of the movie for it to receive a higher rating according to the model(s)?
- Can you, given your model(s), create the ultimate movie? What would it look like?

# Acknowledgements

The dataset provided is based on a [Letterboxd dataset found on Kaggle](https://www.kaggle.com/datasets/gsimonx37/letterboxd/).

# Notes

- We provide the code for processing the full Letterboxd dataset in [this notebook](data/preparation.ipynb). You do not need to run (or even look at) this code to perform any of the tasks.
- When dealing with text and image features, you are free to start from or freeze weights from a pretrained model, provided it has not been trained specifically for this rating prediction task. Be prepared to explain your rationale for doing so.
- This is an open-ended case, and you are encouraged to solve it in a way that you find suitable. Some statements may be vague, such as "compare" the models, and in such cases, you are free to make your own interpretations and assumptions.
