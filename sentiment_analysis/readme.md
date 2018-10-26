NLP: Sentiment Analysis:

Training Data: I use the Sentiment140 dataset provided by Stanford. 
Details about this project can be found here: http://help.sentiment140.com/for-students/
This dataset can be downloaded from the link: http://cs.stanford.edu/people/alecmgo/trainingandtestdata.zip

Data Preprocessing Steps:
1. Remove unwanted columns. We only need tweet text and its sentiment
2. Convert html encoding to text
3. Remove/replace utf encoded characters (emoticons)
4. Remove urls, links, @user_handles
5. Remove hashtags (only the symbol # and not the entire trend markers)
6. Contractions handling - replace i’ve with i have, etc. (replace all apostrophes with single quotes first)
7. Negation handling - replace can’t with can not, etc. (subsumed in contraction handling)
8. Remove numbers, special characters (keep only text)
9. Remove very short words (single letter words)
10. Simple spell correction (like multiple repetition of characters replaced by 2 repeats - loooooooovvvvee replaced with loovvee)
11. class imbalance problem - training set has only sentiments 0 and 4 (negative and positive) but test set has sentiments 0, 2 and 4 (negative, neutral and positive). So I have removed the isntances belonging to class neutral fromt he test set.

Frequency based Word Embeddings are used as features: TFIDF with Unigram, Bigram and Trigram variants.

Machine Learning Algorithms used for model building:
a. Naive Bayes
b. Logistic Regression
c. SVM

Metric Used: Accuracy
