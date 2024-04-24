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

This model is based upon DeBERTa model that was fine-tuned
      on 30K pairs of texts.

- **Developed by:** Zirui Li and Yuhan Wang
- **Language(s):** English
- **Model type:** Supervised
- **Model architecture:** Transformers
- **Finetuned from model [optional]:** deberta-base

### Model Resources

<!-- Provide links where applicable. -->

- **Repository:** https://huggingface.co/microsoft/deberta-base
- **Paper or documentation:** https://openreview.net/forum?id=XPZIaotutsD

## Training Details

### Training Data

<!-- This is a short stub of information on the training data that was used, and documentation related to data pre-processing or additional filtering (if applicable). -->

30K pairs of texts drawn from emails, news articles and blog posts.

### Training Procedure

<!-- This relates heavily to the Technical Specifications. Content here should link to that section when it is relevant to the training procedure. -->

#### Training Hyperparameters

<!-- This is a summary of the values of hyperparameters used in training the model. -->


      - learning_rate: 2e-05
      - train_batch_size: 8
      - eval_batch_size: 8
      - seed: N/A
      - num_epochs: 3
      - loss_function: ContrastiveLoss

#### Speeds, Sizes, Times

<!-- This section provides information about how roughly how long it takes to train the model and the size of the resulting model. -->


      - overall training time: 3 hours
      - duration per training epoch: 1 hour
      - model size: 492MB

## Evaluation

<!-- This section describes the evaluation protocols and provides the results. -->

### Testing Data & Metrics

#### Testing Data

<!-- This should describe any evaluation data used (e.g., the development/validation set provided). -->

A subset of the development set provided, amounting to 2K pairs.

#### Metrics

<!-- These are the evaluation metrics being used. -->


      - Precision
      - Recall
      - F1-score
      - Accuracy
      - ROC-AUC

### Results

The model obtained an F1-score of 93% and an accuracy of 85%.

## Technical Specifications

### Hardware


      - RAM: at least 16 GB
      - Storage: at least 2GB,
      - GPU: T4

### Software


      - Transformers 4.34.0
      - Pytorch 1.11.0+cu113
      - sentence-transformers

## Bias, Risks, and Limitations

<!-- This section is meant to convey both technical and sociotechnical limitations. -->

Any inputs (concatenation of two sequences) longer than
      256 subwords will be truncated by the model.

## Additional Information

<!-- Any other information that would be useful for other people to know. -->

The hyperparameters were determined by experimentation
      with different values.
