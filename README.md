# wine-variety-prediction

I will frame this as a Sentiment Analysis problem where the review will be used to determine the variety of wine
I will be using a Recurrent Neural Network to predict the classes by passing each review as a sequence of vectors. I will also keep text descriptions in their original form.

Embedding the Text
The natural choice for embedding each word as its own vector is to use neural based embedding techniques such as word2vec, GloVe or fastText. We also have the option of training our own embedding model or to use pre-trained vectors.

we will use pre-trained word embeddings.
But which family of embeddings shall we use? I will eliminate fastText right away as it builds word vectors by summing vectors of character n-gram level. Since the type of text we are working with is not likely to contain out of vocabulary words (no misspellings, unusual slang or abbreviations), it will not benefit from this granularity.

we will use pre-trained GloVe vectors
Several pre-trained GloVe word vectors can be downloaded here. I will be using the Common Crawl with 840B tokens as it contains the largest vocabulary and is also case sensitive. Each word vector from glove.840B.300d has 300 coordinates.

we just need to download the vectors     Download from https://nlp.stanford.edu/projects/glove/   glove.840B.300d.zip


Training the Classifier
Since the text descriptions are generally short, I will be using GRU units as opposed to LSTM units. With shorter descriptions, we have less need for a memory unit and can benefit from GRU’s more efficient learning algorithm.
