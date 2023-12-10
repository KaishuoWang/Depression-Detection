# Depression Detection

This repository is for [Detecting Signs of Depression from Social Media Text-LT-EDI@ACL 2022](https://competitions.codalab.org/competitions/36410)

## Generating emotion features using BERT model

Fine-tuning BERT-base-uncased on argilla/twitter-coronavirus to generate emotion features. The fine-tuned model can be found [here](https://huggingface.co/kwang123/bert-sentiment-analysis).

[Code for fine-tuning](https://github.com/KaishuoWang/Depression-Detection/blob/main/fine-tune-bert-for-sentiment_analysis.ipynb)

[Code to generate emotion features](https://github.com/KaishuoWang/Depression-Detection/blob/main/generating-emotion-scores.ipynb)

Weighted F1 score: 0.8926, Macro F1 score: 0.8967

## Traditional classification approach

The model can be found [here](https://drive.google.com/file/d/107vHAbHNqG05WlDmNSzV7m9vET72AVe_/view?usp=sharing).

[Code for fine-tuning](https://github.com/KaishuoWang/Depression-Detection/blob/main/depression-detection-classification.ipynb)

Weighted F1 score: 0.7686, Macro F1 score: 0.7278, Accuracy: 0.7679

## Prompt-based classification approach

The model can be found [here](kwang123/MaskedLM-roberta-large).

[Code for fine-tuning](https://github.com/KaishuoWang/Depression-Detection/blob/main/masked-language-modeling.ipynb)

Weighted F1 score: 0.6160, Macro F1 score: 0.3786, Accuracy: 0.6743

## Zero-shot classification approach

The model can be found [here](https://huggingface.co/kwang123/roberta-base-nli).

Weighted F1 score: 0.7410, Macro F1 score: 0.7410， Accuracy: 0.7411

## Voting System

[Code for voting system](https://github.com/KaishuoWang/Depression-Detection/blob/main/voting_system.ipynb)

### Classification + MaskedLM

Weight for MaskedLM model: $0.3786 \div (0.7278 + 0.3786)$

Weight for Classification model: $0.7278 \div (0.7278 + 0.3786)$

Weighted F1 score: 0.8488, Macro F1 score: 0.8044, Accuracy: 0.8453

### Classification + Zero-shot Classification

Weight for zero-shot classification model $0.7410 \div (0.7278 + 0.7410)$

Weight for classification model $0.7278 \div (0.7278 + 0.7410)$

Weighted F1 score: 0.8358, Macro F1 score: 0.7909, Accuracy: 0.8351

### Classification + MaskedLM + Zero-shot Classification

Weight for zero-shot classification $0.7410 \div (0.7278 + 0.7410 + 0.3786)$

Weight for classification $0.7278 \div (0.7278 + 0.7410 + 0.3786)$

Weight for MaskedLM $0.3786 \div (0.7278 + 0.3786 + 0.7410)$

Weighted F1 score: 0.8358, Macro F1 score: 0.7909, Accuracy: 0.8351
