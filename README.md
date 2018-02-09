This is a simple proof of concept of how we can apply basic nltk techniques to perform sentiment analysis of The Message (MSG) translation of the bible leveraging tensorflow.

High level approach:

* Create an array of the most frequntly occuring ([lemmatized](https://nlp.stanford.edu/IR-book/html/htmledition/stemming-and-lemmatization-1.html)) words from the training samples
* Create feature/label sets for positive and negative sentiment data by counting the number of popular words in each sample, from the array created above
* Using the above labelled features as inputs, train a 3 layer feedfoward neural network which will output an array containing probability percentages for True and False
* We save the model for later use and later run it on the Bible (MSG) saving the results in a sqlite database

Note, the basis for this comes largely from [Rachit Mishra's work](https://becominghuman.ai/deep-learning-using-tensorflow-and-nltk-analyzing-corpuss-sentiments-part-1-bec9d6c1051). I amended with the below:

* added a method to create the layers of the neural network
* saved the model after training for later re-use
* logged training results to be able to view in tensorboard
* ran the model on every verse from 3 books of the bible
    * Ecclesiastes
    * Proverbs
    * Psalms
* saved the results of the above predictions to a sqlite db

