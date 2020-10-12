# [FIND-MOVIE-SIMILARITY-FROM-PLOT-SUMMARIES](https://github.com/parthshah28/FIND-MOVIE-SIMILARITY-FROM-PLOT-SUMMARIES)
Natural Language Processing (NLP) is an exciting field of study for data scientists where they develop algorithms that can make sense out of conversational language used by humans. In this Project, I used NLP and Clustering to find the degree of similarity between movies based on their plots available on IMDb and Wikipedia.

## Dataset
Download [Dataset](https://github.com/parthshah28/FIND-MOVIE-SIMILARITY-FROM-PLOT-SUMMARIES/blob/master/movies.csv)

## Tokenization
Tokenization is the process by which we break down articles into individual sentences or words, as needed. Besides the tokenization method provided by NLTK, we might have to perform additional filtration to remove tokens which are entirely numeric values or punctuation.

Let us perform tokenization on a small extract from The Godfather.
### Output:
['Today', 'May', 'is', 'his', 'only', 'daughter', "'s", 'wedding']

## Stemming
Stemming is the process by which we bring down a word from its different forms to the root word. This helps us establish meaning to different forms of the same words without having to deal with each form separately. For example, the words 'fishing', 'fished', and 'fisher' all get stemmed to the word 'fish'.

Consider the following sentences:

"Young William Wallace witnesses the treachery of Longshanks" ~ Gladiator
"escapes to the city walls only to witness Cicero's death" ~ Braveheart

here are different algorithms available for stemming such as the Porter Stemmer, Snowball Stemmer, etc. I used the Snowball Stemmer.
### Output:
Without stemming:  ['Today', 'May', 'is', 'his', 'only', 'daughter', "'s", 'wedding']
After stemming:    ['today', 'may', 'is', 'his', 'onli', 'daughter', "'s", 'wed']

## Club together Tokenize & Stem
We are now able to tokenize and stem sentences. But we may have to use the two functions repeatedly one after the other to handle a large amount of data, hence we can think of wrapping them in a function and passing the text to be tokenized and stemmed as the function argument. Then we can pass the new wrapping function, which shall perform both tokenizing and stemming instead of just tokenizing, as the tokenizer argument while creating the TF-IDF vector of the text.

What difference does it make though? Consider the sentence from the plot of The Godfather: "Today (May 19, 2016) is his only daughter's wedding." If we do a 'tokenize-only' for this sentence, we have the following result:

'today', 'may', 'is', 'his', 'only', 'daughter', "'s", 'wedding'

But when we do a 'tokenize-and-stem' operation we get:

'today', 'may', 'is', 'his', 'onli', 'daughter', "'s", 'wed'

## Model Building
To determine how closely one movie is related to the other by the help of unsupervised learning, we can use clustering techniques. Clustering is the method of grouping together a number of items such that they exhibit similar properties. According to the measure of similarity desired, a given sample of items can have one or more clusters.

I used K-Means algorithm.K-means is an algorithm which helps us to implement clustering in Python. The name derives from its method of implementation: the given sample is divided into K clusters where each cluster is denoted by the mean of all the items lying in that cluster.

![](https://github.com/parthshah28/FIND-MOVIE-SIMILARITY-FROM-PLOT-SUMMARIES/blob/master/images/bar_clusters.png)

## Dendrogram
We shall plot a dendrogram of the movies whose similarity measure will be given by the similarity distance we previously calculated. The lower the similarity distance between any two movies, the lower their linkage will make an intercept on the y-axis. For instance, the lowest dendrogram linkage we shall discover will be between the movies, It's a Wonderful Life and A Place in the Sun. This indicates that the movies are very similar to each other in their plots.

![](https://github.com/parthshah28/FIND-MOVIE-SIMILARITY-FROM-PLOT-SUMMARIES/blob/master/images/download.png)

## Wrap-up
Which movie is most similar to the movie Braveheart?
### Answer:
Gladiator



