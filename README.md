# ✉️ Naive Bayes Spam Classifier

Used a [dataset](https://www.kaggle.com/datasets/abdallahwagih/spam-emails) from kaggle.

This project is a simple yet effective **spam detection system** built using Python and pandas. It uses the **Naive Bayes algorithm** with **Laplace smoothing** to classify user-input messages as either **spam** or **ham (normal)**.

## 🔍 What It Does

- Reads a dataset of labeled SMS messages (`spam.csv`)
- Calculates prior probabilities and word frequencies for both spam and ham
- Applies **log-based Naive Bayes classification** on new user input
- Supports custom user input from the command line
- Uses **Laplace smoothing** to handle unseen words

## 📄 Dataset

The script expects a CSV file named `spam.csv` with at least the following columns:

- `Category`: either `spam` or `ham`
- `Message`: the text content of the message

Example:

```
Category,Message
ham,Go until jurong point...
spam,Win a brand new car now!!!
```

## 🧠 How It Works

- Removes punctuation and lowercases all words
- Tokenizes and counts word frequencies in spam and ham messages separately
- Uses the **Bag of Words** model with Laplace smoothing
- Calculates:

  - `P(spam | message)` and `P(ham | message)`
  - Selects the class with the higher probability

## ✅ Sample Input/Output

```
Enter your email (press ENTER twice to finish):
Congratulations! You've won a free ticket to Bahamas!
(click enter again)

Spam mail!!
```

Or:

```
Enter your email (press ENTER twice to finish):
Hey are we still meeting at 6pm today?
(click enter again)

Normal mail!!!
```

## 📦 Requirements

- Python 3.x
- pandas

### Install requirements:

```bash
pip install pandas
```

## 📁 File Structure

```
spamfilter.py     # Main script
spam.csv               # Dataset file
README.md              # This file
```

## 🧪 Techniques Used

- Naive Bayes formula with logs:

  - `log(P(spam)) + sum(log(P(word|spam)))`
- Laplace smoothing:

  - `(frequency + 1) / (total words + vocabulary size)`
- Manual tokenization and frequency mapping

## 🔧 Improvements You Could Add

- Use `CountVectorizer` or `TfidfVectorizer` from `sklearn`
- Split data into training and testing sets
- Train on a larger dataset
- Add GUI or web interface for input
- Save model using `pickle` for faster reuse

## 📝 License

Open-source for learning and experimentation purposes.
