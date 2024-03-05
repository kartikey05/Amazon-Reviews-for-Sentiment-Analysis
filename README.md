# Amazon Customer Reviews Sentiment Analysis Dataset

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## About the Dataset

This dataset contains millions of Amazon customer reviews paired with star ratings. It serves as a powerful resource for training fastText models for sentiment analysis.

### Key Features

- **Scale:** The dataset is substantial, reflecting real business data on a reasonable scale, making it suitable for practical applications.
- **Efficiency:** Despite its size, the dataset can be trained in minutes on a modest laptop, making it ideal for fastText applications.
- **Realistic:** The reviews represent genuine customer sentiments, providing a valuable insight into real-world opinions.

### Data Format

The dataset adheres to the format required for the fastText supervised learning tutorial:

```plaintext
__label__<X> __label__<Y> ... <Text>
```

- `X` and `Y` represent class names (e.g., __label__1, __label__2).
- Reviews are categorized into classes with no quotes, all on one line.
- For this dataset, __label__1 corresponds to 1- and 2-star reviews, and __label__2 corresponds to 4- and 5-star reviews.
- Reviews with neutral sentiment (3-star) were not included in the original dataset.
- Review titles, followed by ':' and a space, are prepended to the text.
- While most reviews are in English, there are some in other languages, such as Spanish.

## Source

The data was sourced from Xiang Zhang's Google Drive directory. Note that the original data was in .csv format, which was reformatted for compatibility with fastText.

## Training and Testing

Follow the instructions in the fastText supervised learning tutorial to set up the directory.

### Training

Use the following command to train the model:

```bash
./fasttext supervised -input train.ft.txt -output model_amzn
```

This process typically takes just a few minutes.

### Testing

Verify the accuracy of the trained model with the following test command:

```bash
./fasttext test model_amzn.bin test.ft.txt
```

If everything is in order, you should expect a precision and recall of 0.916.

Additionally, you can perform training and testing using Python; refer to the provided Kernel for details.

Happy analyzing! 🚀
