# English to French Translation using a RNN Model
This project demonstrates how to train a RNN model for English to French translation using the Keras deep learning library.

## Part 1: Data Preparation
This part involves preparing the data for training the sequence-to-sequence model. The data used in this project is the English-French corpus from this link [Click here](https://www.manythings.org/anki/) to access the dataset used in this project, which consists of sentence pairs of English and French translations. The following steps are performed in this part:

This code performs data preprocessing on a language translation dataset. The dataset is loaded from a file, and then split into English-French pairs. The pairs are then cleaned by removing non-printable characters, punctuation, and tokens containing numbers. The cleaned pairs are saved to a pickle file.
Next, the clean dataset is loaded from the pickle file, reduced to 15,000 sentences, randomly shuffled, and split into a training set of 12,000 sentences and a test set of 3,000 sentences. The resulting datasets are saved to separate pickle files.

## Part 2: Model Training
This part defines and trains a neural machine translation (NMT) model using Keras and TensorFlow. The model translates sentences from French to English.

Here's a summary of what the code does:

* The code imports the necessary libraries and functions, including loading the cleaned dataset using the pickle library.
* It defines functions to load and preprocess the data. The create_tokenizer function creates a tokenizer for each language and the max_length function determines the maximum length of the sentences in the dataset. The encode_sequences and encode_output functions encode the input and output sequences respectively and pad the sequences to a maximum length.
* The define_model function defines the architecture of the NMT model using Keras layers such as Embedding, LSTM, RepeatVector, and TimeDistributed.
* The code loads the dataset and splits it into training and test sets.
* It creates tokenizers for each language and determines the maximum length of the sentences in each language.
* The code encodes and pads the training and test sets using the tokenizers and maximum lengths.
* It defines the NMT model using the define_model function and compiles it using the Adam optimizer and categorical cross-entropy loss function.
* The code prints a summary of the model architecture and saves a visualization of the model to a file.
* The code trains the model for 30 epochs on the training data, with a batch size of 64 and using the validation set for evaluation. It also saves the best model weights to a file using the ModelCheckpoint callback.

## Part 3: Model Evaluation
The final part of the code is loading the trained model using the load_model() function from the Keras library. Then, the model is evaluated on the training and test datasets using the evaluate_model() function. This function takes as input the model, the English tokenizer, the encoded German sentences (source), and the raw dataset (both for training and test sets). It outputs the predicted translation for each source sentence along with the actual target sentence and the corresponding BLEU-1, BLEU-2, BLEU-3, and BLEU-4 scores. BLEU scores are a way to measure the quality of machine-generated text compared to human-generated text. BLEU-1 measures the unigram overlap between the predicted and actual sentences, while BLEU-4 measures the 4-gram overlap. Finally, the results are printed on the screen.


Note that the BLEU score ranges from 0 to 1, where 1 indicates a perfect translation. A higher BLEU score indicates a better translation performance of the model.
