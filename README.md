# Depression Detection

This repository contains the code for [Detecting Signs of Depression from Social Media Text-LT-EDI@ACL 2022](https://competitions.codalab.org/competitions/36410)

## Generating emotion features using BERT model

Fine-tuning BERT-base-uncased on argilla/twitter-coronavirus to generate emotion features. The fine-tuned model can be found [here](https://huggingface.co/kwang123/bert-sentiment-analysis).

[Code for fine-tuning](https://github.com/KaishuoWang/Depression-Detection/blob/main/fine-tune-bert-for-sentiment_analysis.ipynb)

[Code to generate emotion features](https://github.com/KaishuoWang/Depression-Detection/blob/main/generating-emotion-scores.ipynb)

## Traditional classification approach

The model can be found [here](https://drive.google.com/file/d/107vHAbHNqG05WlDmNSzV7m9vET72AVe_/view?usp=sharing).

[Code for fine-tuning](https://github.com/KaishuoWang/Depression-Detection/blob/main/depression-detection-classification.ipynb)

F1: 0.7686

## Masked Language Modeling approach

The model can be found [here](kwang123/MaskedLM-roberta-large).

[Code for fine-tuning](https://github.com/KaishuoWang/Depression-Detection/blob/main/masked_language_modeling.ipynb)

F1: 0.6160

## Voting System

Weight for MaskedLM model: $0.6160 \div (0.6160 + 0.7686) = 0.4449$

Weight for Classification model: $0.7686 \div (0.6160 + 0.7686) = 0.5551$

[Code for voting system](https://github.com/KaishuoWang/Depression-Detection/blob/main/voting_system.ipynb)

F1: 0.8487601324211029
