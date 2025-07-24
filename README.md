# Naive Bayes Spam Classifier

This project is a simple spam detection system implemented in Python using the Naive Bayes algorithm with Laplace smoothing. It classifies messages as spam or ham based on learned word probabilities from a dataset.

## Dataset
- [Dataset](https://www.kaggle.com/datasets/abdallahwagih/spam-emails) used from kaggle.
- File: `spam.csv`
- Columns required:

  - `Category`: contains labels (`spam` or `ham`)
  - `Message`: contains the message text

## Features

- Manual implementation of Naive Bayes from scratch
- Handles punctuation and case sensitivity
- Applies Laplace smoothing to prevent zero probabilities
- Accepts multi-line user input from the command line

## Preprocessing

- Messages are tokenized after:
  - Converting to lowercase
  - Removing all punctuation using Python's `string.punctuation`
- Words are split and counted separately for spam and ham categories

## Training

- Calculates prior probabilities:

  - `P(spam) = count(spam) / total`
  - `P(ham) = count(ham) / total`
- Builds frequency dictionaries for spam and ham messages
- Computes conditional probabilities:

  - `P(word | spam)` and `P(word | ham)`
- Stores these probabilities for use during classification

## Classification Logic

- Prompts the user to input a message (supports multi-line input; press ENTER twice to finish)
- For each word:

  - Applies Laplace smoothing:

    - `P(word | class) = (count + 1) / (total words + vocabulary size)`
  - Computes:

    - `log(P(spam)) + Σ log(P(word | spam))`
    - `log(P(ham)) + Σ log(P(word | ham))`
- Compares total log probabilities:

  - If spam score > ham score → "Spam mail!!"
  - Else → "Normal mail!!!"

## Requirements

- pandas
- Python 3.x

## License

Open-source and free to use for educational purposes.
