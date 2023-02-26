# English to French Translation using a Sequence-to-Sequence Model
This project demonstrates how to train a sequence-to-sequence model for English to French translation using the Keras deep learning library.

## Part 1: Data Preparation
This part involves preparing the data for training the sequence-to-sequence model. The data used in this project is the English-French corpus from this link [Click here](https://www.manythings.org/anki/) to access the dataset used in this project, which consists of sentence pairs of English and French translations. The following steps are performed in this part:

* Load the raw text data from the downloaded file.
* Clean the data by removing non-printable characters, punctuation, and whitespace.
* Tokenize the data into sentences and create sentence pairs of English and French translations.
* Filter out sentence pairs that are too long or too short.
* Save the cleaned and filtered sentence pairs into a single file.

## Part 2: Model Training
This part involves training the sequence-to-sequence model using the prepared data. The model architecture used in this project is an encoder-decoder model with attention. The following steps are performed in this part:

* Load the cleaned and filtered sentence pairs from the prepared file.
* Tokenize the English and French sentences using the Keras Tokenizer.
* Pad the tokenized sequences to have the same length.
* Split the data into training and testing sets.
* Train the sequence-to-sequence model using the training data.
* Save the trained model to a file.

## Part 3: Model Evaluation
This part involves evaluating the performance of the trained sequence-to-sequence model on new data. The evaluation is done by calculating the BLEU score, which is a metric commonly used to evaluate the quality of machine translation. The following steps are performed in this part:

* Load the trained sequence-to-sequence model from the saved file.
* Tokenize the English sentences from the test set using the same tokenizer used in Part 2.
* Pad the tokenized sequences to have the same length.
* Generate translations of the French sentences using the trained model.
* Calculate the BLEU score of the generated translations against the actual translations of the French sentences in the test set.

Note that the BLEU score ranges from 0 to 1, where 1 indicates a perfect translation. A higher BLEU score indicates a better translation performance of the model.
