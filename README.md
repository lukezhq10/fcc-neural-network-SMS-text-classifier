# Neural Network SMS Text Classifier
This includes the Neural Network SMS Text Classifier project from FreeCodeCamp under the Machine Learning with Python course @ https://www.freecodecamp.org/learn/machine-learning-with-python/machine-learning-with-python-projects/neural-network-sms-text-classifier

Tensorflow tutorial on Text Classification RNNs was used as a reference @ https://www.tensorflow.org/text/tutorials/text_classification_rnn

# Project Description
We created a Sequential RNN model and trained it using the train dataset to create a text classifier, where given a text message, predicts whether it is spam or not (ham). Our model is a Sequential model containing the following layers:
1. Encoder layer
TextVectorization layer converts text to a sequence of token indices. We set the max tokens and output sequence length to 1000 in order to pad variable length texts to feed later to the model

2. Embedding layer
This converts the word indices to sequneces of vectors. After training, words with similar meanings often have similar vectors.

3. Bidirectional layer
We use a LSTM RNN with a Bidirectional wrapper to process the input sequence in both forward and backward directions to get a better context in making predictions. Here, we use two - one with 64 units and one with 32 units after in order to enhnace our model's feature extraction capability.

4. Dense layer
Final Dense layers does some processing to the single vector the RNN has converted the sequence to. Here, we use a relu activation function to differentiate between spam vs. ham

6. Classification
spam is anything the model predicts > 0.5 since we originally set spam = 1 and ham = 0
   
Originally, the model wasn't able to pass the challenge. The model was updated to be more accurate by:
1. Adding an extra LSTM layer
2. Adding a Dropout layer to counteract overfitting
