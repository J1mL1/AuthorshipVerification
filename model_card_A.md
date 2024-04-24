---
{}
---
language: en
license: cc-by-4.0
tags:
- text-classification
repo: https://github.com/J1mL1/AuthorshipVerification

---

# Model Card for f60163yw-c00182zl-AV

<!-- Provide a quick summary of what the model is/does. -->

This is a classification model that was trained to
      detect whether two pieces of text were written by the same author.


## Model Details

### Model Description

<!-- Provide a longer summary of what this model is. -->

This model is based upon a Logistic regression model that was fine-tuned
      on 30K pairs of texts.

- **Developed by:** Yuhan Wang and Zirui Li
- **Language(s):** English
- **Model type:** Supervised
- **Model architecture:** Binary classification
- **Finetuned from model [optional]:** Logistic regression

### Model Resources

<!-- Provide links where applicable. -->

- **Repository:** None
- **Paper or documentation:** https://www.biochemia-medica.com/en/journal/24/1/10.11613/BM.2014.003

## Training Details

### Training Data

<!-- This is a short stub of information on the training data that was used, and documentation related to data pre-processing or additional filtering (if applicable). -->

30K pairs of texts drawn from emails, news articles and blog posts.

### Training Procedure

<!-- This relates heavily to the Technical Specifications. Content here should link to that section when it is relevant to the training procedure. -->

#### Training Hyperparameters

<!-- This is a summary of the values of hyperparameters used in training the model. -->


      - andom_state:42

#### Speeds, Sizes, Times

<!-- This section provides information about how roughly how long it takes to train the model and the size of the resulting model. -->


        None

## Evaluation

<!-- This section describes the evaluation protocols and provides the results. -->

### Testing Data & Metrics

#### Testing Data

<!-- This should describe any evaluation data used (e.g., the development/validation set provided). -->

A subset of the development set provided, amounting to 6K pairs.

#### Metrics

<!-- These are the evaluation metrics being used. -->


      - Precision
      - Recall
      - F1-score
      - Accuracy

### Results

The model obtained an F1-score of 56% and an accuracy of 56%.

## Technical Specifications

### Hardware


      - RAM: at least 16 GB
      - Storage: at least 2GB,
      - GPU: V100

### Software


      - joblib
      - scikit-learn

## Bias, Risks, and Limitations

<!-- This section is meant to convey both technical and sociotechnical limitations. -->

Any inputs (concatenation of two sequences) longer than
      512 subwords will be truncated by the model.

## Additional Information

<!-- Any other information that would be useful for other people to know. -->

use TF-IDF to extract Feature before any train and test,parameter is TfidfVectorizer(min_df=3, max_features=None, strip_accents='unicode', analyzer='word', token_pattern=r'\w{1,}', ngram_range=(1, 3), use_idf=1, smooth_idf=1, sublinear_tf=1) 
