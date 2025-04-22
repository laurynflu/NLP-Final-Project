
# NLP Auto-Suggest Model

## Project Overview

The goal of this project is to create an auto-suggest system by exploring the performance of different n-gram model sizes on a dataset of Google queries. The project implements an n-gram model and evaluates how the size of the n-gram affects the quality of word prediction for auto-suggest systems.

## Background

Auto-suggest features are widely used in search engines and applications to help users complete their queries. This project explores n-gram models of varying sizes (unigram, bigram, trigram, and 4-gram) to evaluate how different n-gram sizes impact the prediction quality.

The datasets used to train and test the models were gathered from the online platform Hugging Face:
- **Training Dataset**: `google_wellformed_query` dataset (25,100 queries annotated for well-formedness).
- **Testing Dataset**: `jordane95/trec-dl-2019-query` dataset (200 complete English queries).

## Approach

### Pre-processing

1. Tokenized all the queries in the dataset by splitting them into individual words.
2. Lowercased all words and handled unknown words by replacing them with "UNK" based on their frequency in the dataset.
3. Ensured that the dataset only included complete queries (to avoid issues seen in the Yahoo! query dataset).

### N-gram Model

- The model supports varying n-gram sizes (unigram, bigram, trigram, and 4-gram).
- The training process involves calculating the probability of each n-gram in the dataset and using these probabilities to predict the next word based on the context (previous n-1 words).
- The model outputs the top five suggested words based on the highest probability.

### Model Evaluation

- The model was tested using 200 queries from the test dataset.
- Each n-gram model was evaluated to see how often it predicted the correct word from the query.
- The performance was measured by comparing how often each n-gram size suggested the correct next word.

### Results

- The **bigram** model performed the best for the given dataset, as it suggested the correct word more frequently than the unigram, trigram, and 4-gram models.
- The unigram model and 4-gram model performed poorly due to their inability to capture enough context for accurate predictions.

### Future Improvements

- Further testing with standardized query lengths might improve model performance.
- Building a front-end feature to demonstrate the auto-suggestion functionality in real-time.

## Technologies Used

- Python
- Hugging Face Datasets
- NLTK (for n-gram model implementation)

## Works Cited

- Ashraf, Shawon. “Demystifying Autocomplete - Part 1.” Medium, Towards Data Science, 13 Oct. 2020. https://towardsdatascience.com/index-48563e4c1572.
- “Google_wellformed_query · Datasets at Hugging Face.” Hugging Face, https://huggingface.co/datasets/google_wellformed_query.
- Li, Zehan. “Jordane95/TREC-DL-2019-Query · Datasets at Hugging Face.” Hugging Face, https://huggingface.co/datasets/jordane95/trec-dl-2019-query.
- Matalka, Luay. “How to Easily Create Tables in Python.” Medium, Towards Data Science, 21 Nov. 2022. https://towardsdatascience.com/how-to-easily-create-tables-in-python-2eaea447d8fd.
- Tan, Liling. “N-Gram Language Model with NLTK.” Kaggle, https://www.kaggle.com/code/alvations/n-gram-language-model-with-nltk.
