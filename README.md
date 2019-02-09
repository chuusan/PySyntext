# PySyntext

Team Members

|Name | Github |
|---|---|
| Harjyot Kaur |[harjyotkaur](https://github.com/HarjyotKaur)  |
| Alexander Pak | [pak-alex](https://github.com/pak-alex) |
| Yenan Zhang |[YenanZ](https://github.com/YenanZ)  |

### Summary

There are many packages that cover summary statistics for numerical data. However, when it comes to text data, there is a lack of selection for packages of similar functionality. Our group would like to tackle this problem by creating `PySyntext`. This package will allow users to input passages and receive summary information and sentiment analysis on the text, giving the user valuable information on how best to proceed with their data.

Sample functionality included in this package for a given text passage:

* Most common word
* Most frequent n-gram
* Overall Sentiment (Positive, Negative)
* Number of spelling mistakes
* ...etc.


### Function 1: `TextSummarize`

`TextSummarize` function of class `PySyntext` takes in `string` as an input and produces `DataFrame` as an output containing a quantitative summary of the input. The quantitative summary entails the following:

- Number of Words
- Number of Sentences
- Most Common Word/Words
- Least Common Word/Words
- Average Word Length
- Average Sentence Length

| Name | Type |
|---|---|
| Input | String |
| Output | Dataframe |

#### Output: Dataframe

| Column | Type|
|---|---|
| word_count | int |
| sentence_count | int |
| most_common | int |
| least_common | int |
| avg_word_len | int |
| avg_sentence_len| int |

The function takes in the following arguments:

| Name | Type | Default|
|---|---|---|
| string | str | NA |  
| stopwords_remove | boolean | True |
| stopwords_remove | boolean | True |
| lemitize | boolean | False |
| remove_punctuation | boolean | True |
| remove_numbers |  boolean | True |
| case_sensitive |  boolean | False |
| gibberish_remove |  boolean | True  |


### Function 2: `TextGrams`

`TextGrams` function of class `PySyntext` takes in `string` as an input and produces `DataFrame` as an output containing lists of top 5 ngrams. The top `k` ngrams and `n` are user based inputs with default values (k=5 and n=(2,3))

| Name | Type |
|---|---|
| Input | String |
| Output | Dataframe |

#### Output: Dataframe

| Column | Type|
|---|---|
| ngrams | list |

*Number of rows are dependent on the input  `n` of the user*
*Size of the list is dependent on the input `k` of the user*

The function takes in the following arguments:

| Name | Type | Default|
|---|---|---|
| string | str | NA |
| k | int | 5 |
| n | int,list | (2,3) |
| stopwords_remove | boolean | True |
| lemitize | boolean | False |
| remove_punctuation | boolean | True |
| remove_numbers |  boolean | True |
| case_sensitive |  boolean | False |
| gibberish_remove |  boolean | True  |


### Function 3: `TextQuality`

`TextQuality` function of class `PySyntext` takes in `string` as an input and produces `DataFrame` as an output a qualitative summary of the input. The qualitative summary would include the following:

- Spelling Mistakes: Words spelt wrong/Total words
- Overall Sentiment: "Positive" or "Negative"

| Name | Type |
|---|---|
| Input | String |
| Output | Dataframe |

#### Output: Dataframe

|Column| Type|
|---|---|
| spell_error | float |
| toxicity | float |

The function takes in the following arguments:

| Name | Type | Default|
|---|---|---|
| string | str | NA |


### Python Ecosystem

There are several popular Natural Language Processing packages that exist in the Python landscape. [NLTK](https://www.nltk.org/) and [spaCy](https://spacy.io/) are the most popular packages for dedicated natural language processing. [sci-kit learn](https://scikit-learn.org/stable/), another popular machine learning package, provides the framework for general machine learning models, and includes functions for text analysis.

Although these packages provide the framework for tokenizing and fitting models to text data, it is difficult to create a quick-and-dirty summary of your data using these packages. By using PySyntext, summary and sentiment of text data is quickly achievable, allowing users to determine the worth of their dataset.
