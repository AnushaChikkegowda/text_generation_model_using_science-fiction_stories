# Language Model using Science Fiction Stories

## Overview

Brief overview of the language model project.

## Table of Contents

- [Data Preprocessing](#data-preprocessing)
- [Model](#model)
- [Model Training and Hyperparameters](#model-training-and-hyperparameters)
- [Conclusion](#conclusion)

## Data Preprocessing

The special characters and blank spaces are removed. Test corpus and a list of unique vocabulary are created. The whole text is divided into multiple strings, each of length 31 through sliding window. The last 500,000 words are selected as the subset to be trained, tokenized, and pre-padded for a length of 30 and stacked vertically. The first 30 words of each row are selected as features, and the 31st as the target variable.

## Model

The model uses LSTM to predict the next words. The model consists of an Embedding layer and 2 LSTM layers with 64 units each. A dense layer of 128 units and a dropout layer with a ratio of 0.2 are added to prevent overfitting.

## Model Training and Hyperparameters

The model is compiled with Adam optimizer of a learning rate of 0.001 for 110 epochs with a batch size of 32. A callback function is defined to save the checkpoints at each epoch. The patience in Early stopping is set to 10, and loss is monitored.

## Conclusion

The loss of the model at the 110th epoch is 4.1984. The model generates text when the input text and the number of words are provided. The subset of the dataset is taken, as the model kept on crashing on Google Colab Pro when the entire dataset was used. Simple LSTM layers are used as it is trained faster and computationally less expensive than pre-trained language models or complicated RNNs when training a large dataset.

