# Yelp Review Classification

## Description

Millions of people share a great number of reviews about business on [Yelp.com](https://www.yelp.com/) and Yelp mobile app everyday. These reviews and ratings help other users to make a choice. My instructor used [Yelp APIs (application programming interface)](https://www.yelp.ca/developers) to collect over 35,000 reviews of 1,000 restaurants in New York City. We split this dataset into 90\% TRAIN set (28,000 reviews), 10\% DEV set (3,500 reviews), and 10\% TEST set (3,500 reviews). Each review has text review content and a corresponding label (i.e., 5-level rating star). This table shows the class ditribution of TRAIN and DEV sets.

|    Rating      |     |    # of reviews  |
|--------|-------------------|-----|
|| Train             | Dev |
| 1star      | 5,619              | 683 |
| 2star      | 5,616              | 677 |
| 3star      | 5,583              | 713 |
| 4star      | 5,532              | 733 |
| 5star      | 5,650              | 694 |


This task is trying to solve a 5-class classification by deep learning networks. Here I used a uni-directional LSTM model to approach the task. 

My final choices for hyperparameters are:

| Hyperparameter | Choice |
|----------------|--------|
| Text-lowercase | Yes |
| Text-remove stopwords | No |
| Text-tokenizer | nltk-tokenizer |
| Text-max vocabulary | None |
| Text-minimum frequency | 3 |
| Batch size | 32 |
| Embedding size | 300 |
| Embedding initialization | GloVe 840B |
| Dropout rate | 0.2 |
| Core model | LSTM RNN : bidirectional = False|
| Activation function | None |
| Use linear layer | Yes |
| Output layer | Softmax |
| Hidden size | 512 |
| Number of layers | 4 |
| Learning rate | 0.2 |
| Criterion | NLLLoss |
| Regularization | L2, weight decay = 0.00001 |
| Optimizer | SGD, momentum = 0.9 |
| Epoch | 20


By using these hyperparameters, the best validation score I get is 0.6046 with F1 score is 0.6006.

## Credits

This task is designed and mentored by the instructor team led by [Muhammad Abdul-Mageed](https://mageed.arts.ubc.ca/). 