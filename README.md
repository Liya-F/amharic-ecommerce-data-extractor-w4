

This project fine-tunes and compares different models for Named Entity Recognition (NER) on a custom multilingual dataset. The goal is to identify entities such as product names, prices, and locations from informal text.

## Overview

The dataset was scraped from five Telegram channels and processed for training a token classification model. Currently, the project pipeline consists of the following stages:

- **Data Collection**: Messages were scraped from Telegram using the `telethon` Python library.
- **Data Cleaning**: Text was cleaned and normalized using standard Python tools to prepare for labeling.
- **Annotation**: Cleaned text was manually labeled using the `docanno` tool in CoNLL format.
- **Model Fine-Tuning**: The `xlm-roberta-base` model was fine-tuned using Hugging Face Transformers for the token classification task.

## Features

- Multilingual token classification
- Custom entity label mapping
- Training and evaluation using Hugging Face `Trainer`
- Dataset formatting with the `datasets` library

## Dependencies

- `transformers`
- `datasets`
- `torch`
- `telethon`
- `pandas`
- `docanno` 
