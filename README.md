# Sentimental Analysis Using Bidirection LSTM

## Overview

This project showcases a Sentimental Analysis Model that utilizes RNN and LSTM. The Model predicts your text is positive or negative along giving a score between 0 and 1.

## Methodology

**1. Data Pre-processing**

**Dataset**: the dataset is 50% of [Kaggle's 50k IMDB Movie review](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)

**Pre-processing:**

First we clean out data from noise as reviews general contains mainy things which will not effect polarity of a sentence.

* Removing URLs
* Removing Emails
* Removing single/double quotes
* Removing HTML tags
* Removing Punctuations
* Removing stop words

Then we convert whole sentence to lower case to remove distinction on the basis of case.

Last step of pre-processing is tokenization which will convert data to numeric vectors so that neural network can understand it.

**2. Building Model**

After spliting data to train and test categories we will start building our RNN model.

Our model will be Sequential type which is made of stack of layers.

Our model will consists of these layers:

1. Embedding layer with batch_size = 128
2. Bidirection LSTM layer with 128 units
3. Next are three dense layers with ReLU activation function. First and second with 64 units and third one with 16 units.
4. Model also has dropout layers, which will prevent overfitting
5. Last one is the output layer with is a Dense layer with single neuron.

After building our model only thing left is to train out model.....and we are done

**3. Prediction**

Model predicts very well as shown in notebook...

Flaws in model:

- Accuracy is about 70%-80%
- As these are movie reviews so, not all negative word data will be present
- neutral sentences give random results
