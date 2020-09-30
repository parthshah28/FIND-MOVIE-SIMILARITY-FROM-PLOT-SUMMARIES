# [FIND-MOVIE-SIMILARITY-FROM-PLOT-SUMMARIES](https://github.com/parthshah28/FIND-MOVIE-SIMILARITY-FROM-PLOT-SUMMARIES)
Natural Language Processing (NLP) is an exciting field of study for data scientists where they develop algorithms that can make sense out of conversational language used by humans. In this Project, I used NLP and Clustering to find the degree of similarity between movies based on their plots available on IMDb and Wikipedia.

## Dataset
Download [Dataset](https://github.com/parthshah28/FIND-MOVIE-SIMILARITY-FROM-PLOT-SUMMARIES/blob/master/movies.csv)

## Tokenization
Tokenization is the process by which we break down articles into individual sentences or words, as needed. Besides the tokenization method provided by NLTK, we might have to perform additional filtration to remove tokens which are entirely numeric values or punctuation.

Let us perform tokenization on a small extract from The Godfather.
### Output
['Today', 'May', 'is', 'his', 'only', 'daughter', "'s", 'wedding']

