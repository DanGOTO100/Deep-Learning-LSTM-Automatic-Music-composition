# Automatic Music Composition with RNN
# Uses Keras interface,  TensorFlow backend and Music21
# Dataset:  Guitar God **Steve Vai's** music scores. 

This notebook pretends to create a model  for automatic music compostion. 
It will create a song based on the training input. For training we have used  **Steve Vai's songs** in midi format. Music21 will be used to convert midi files into training data. Actually, there are two models, one for the notes and other for the duration of each note. 

We will use a RNN, LSTM, with timestep = 7 and around 30K sequences of training data.

In the experiment, we will provide the first 7 notes of a well known Steve Vai's song: "For the love of god", and we will check what the model composes with those 7 notes as an input. We have the original song to compare.

There are many challenges here, but some of them for further work:
* The guitar scores have melodies and solos. The solos' parts have notes of very short duration, played very fast and very repetitive. Future work, will build models for melody and soloing - however there is not a clear boundary when building a solo or when building a melody
* The possible notes are given by the key of the song. If we are in Em, there are a set of allowed notes and other not allowed. The model is trained with the whole Vai's scores, who are in many different keys, hence keeping the tune is up for the model to have learned. Future work will explore working with intervals instead of notes themselves.
* Keeping a melody must remain estable in duration with no ups and down in duration, I will explore ways to have a melody built-up through the model.

