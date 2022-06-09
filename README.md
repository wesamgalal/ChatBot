# ChatBot
A jokes Chatbot as question-answer sytstem 
to be used as an expert that can predict and provide funny answers to the user through outlines of the mechanisms we used in our Jokes chatbot.
     "Jokes chatbot procedure"
     
A.	Tokenizing text data:

By using NLTK (natural language toolkit) we dividing the input text
Into a set of pieces of words or sentences depends on the method we using (sentence or word or word punct tokenizer) these pieces are called tokens. We used word tokenize function after importing NLTK package as following:

import nltk
sent=nltk. word_tokenize (x. lower ())



B.	Word Embedding:

Machine learning algorithms need numeric data to work with so that they can analyze the data and extract meaningful information. Gensim package allows us to calculate distances among the elements
using similarity measures such as cosine distance and inner products by embedding vectors models (word2vec, sen2vec, doc2vec, anything2vec which means embedding it to vectors) and position in the vector space words that share common contexts.

#train model
jokes_vec = Word2Vec (corpus, size=300, min_count=1)
#summarize vocabulary
words = list (jokes_vec.wv. vocab)
#explore semantic similarities
word = 'france'
lower_word = word. lower ()
jokes_vec. most_similar(lower_word)
#save model.bin
jokes_vec. save('jokes_vec.bin')

C.	Keras LSTM:

Long short-term memory (LSTM) units (or blocks) are a building unit for layers of a recurrent neural network (RNN). The expression long short-term refers to the fact that LSTM is a model for the short-term memory which can last for a long period of time. LSTMs were developed to deal with the exploding and vanishing gradient problem when training traditional RNNs.
#the Sequential way of building deep learning networks will be used:
model=Sequential ()
model.add (LSTM (output_dim=300, input_shape=x_train. shape[1:], return_sequences=True, init='glorot_normal', inner_init='glorot_normal', activation='sigmoid'))
model.add (LSTM (output_dim=300, input_shape=x_train. shape[1:],return_sequences=True, init='glorot_normal', inner_init='glorot_normal', activation='sigmoid')).

D.	Compiling and running the Keras LSTM:

After running the model, the compile function using ‘Adam’ optimizer will return the values of:
-	Loss function
-	Accuracy
modelmodel.compile(loss='cosine_proximity',optimizer='adam',
metrics=['accuracy']).

