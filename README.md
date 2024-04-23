# Text Analysis

The objective of this document is to explain the methodology adopted to perform text analysis to drive sentimental opinion, sentiment scores, readability, passive words, personal pronouns, etc.

## Table of Contents
1. [Sentimental Analysis](#sentimental-analysis)
   - [Cleaning using Stop Words Lists](#cleaning-using-stop-words-lists)
   - [Creating a dictionary of Positive and Negative words](#creating-a-dictionary-of-positive-and-negative-words)
   - [Extracting Derived variables](#extracting-derived-variables)
2. [Analysis of Readability](#analysis-of-readability)
3. [Average Number of Words Per Sentence](#average-number-of-words-per-sentence)
4. [Complex Word Count](#complex-word-count)
5. [Word Count](#word-count)
6. [Syllable Count Per Word](#syllable-count-per-word)
7. [Personal Pronouns](#personal-pronouns)
8. [Average Word Length](#average-word-length)

## Sentimental Analysis

Sentimental analysis is the process of determining whether a piece of writing is positive, negative, or neutral. The algorithm designed below is for use in Financial Texts. It consists of the following steps:

### Cleaning using Stop Words Lists

The Stop Words Lists (found in the folder StopWords) are used to clean the text so that Sentiment Analysis can be performed by excluding the words found in the Stop Words List.

### Creating a dictionary of Positive and Negative words

The Master Dictionary (found in the folder MasterDictionary) is used to create a dictionary of Positive and Negative words. Only those words are added to the dictionary if they are not found in the Stop Words Lists.

### Extracting Derived variables

We convert the text into a list of tokens using the nltk tokenize module and use these tokens to calculate the following variables:

- Positive Score
- Negative Score
- Polarity Score
- Subjectivity Score

## Analysis of Readability

Analysis of Readability is calculated using the Gunning Fox index formula described below.

## Average Number of Words Per Sentence

The formula for calculating is:
Average Number of Words Per Sentence = the total number of words / the total number of sentences

## Complex Word Count

Complex words are words in the text that contain more than two syllables.

## Word Count

We count the total cleaned words present in the text by removing the stop words and any punctuations like ? ! , . from the word before counting.

## Syllable Count Per Word

We count the number of syllables in each word of the text by counting the vowels present in each word. We also handle some exceptions like words ending with "es," "ed" by not counting them as a syllable.

## Personal Pronouns

To calculate Personal Pronouns mentioned in the text, we use regex to find the counts of the words - “I,” “we,” “my,” “ours,” and “us”. Special care is taken so that the country name US is not included in the list.

## Average Word Length

Average Word Length is calculated by the formula: Sum of the total number of characters in each word / Total number of words
