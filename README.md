# Multilingual Named Entity Recognition on Telegram Commerce Data

This project fine-tunes and compares transformer-based models for Named Entity Recognition (NER) on a custom multilingual dataset. The goal is to identify key entities like **product names**, **prices**, and **locations** from informal e-commerce text messages scraped from Telegram channels. The project also develops a vendor analytics engine to score micro-lending potential.

## Overview

The dataset was scraped from five Telegram vendor channels and processed for training a token classification model. The project pipeline consists of the following stages:

### Data Collection
- Telegram messages were scraped using the `telethon` Python library.
- Metadata like views, timestamps, and channel IDs were preserved for later use.

### Cleaning & Annotation
- Text cleaning and normalization were done with standard Python tools.
- Annotation was performed using `docanno` and exported in CoNLL format.
- Labels include product, price, and location.

### Model Fine-Tuning
- Fine-tuned `xlm-roberta-base` and `distilbert-base-multilingual-cased` using the Hugging Face `Trainer` API.
- Token classification models were trained on the annotated dataset.
- Output directories (`xlm-roberta-output`, `distilbert-output`) store the best model checkpoints.

### Model Comparison
- Both models were evaluated and compared on a validation set.
- Metrics such as `eval_loss`, `eval_runtime`, and `eval_samples_per_second` were recorded.
- **DistilBERT** showed better performance in loss and speed, making it suitable for deployment.

###Model Interpretability
- Used **SHAP** and **LIME** to visualize and explain entity-level decisions made by the NER model.
- Interpreted predictions for difficult cases with ambiguous or overlapping entities.
- Highlighted token contributions to model outputs.

### Vendor Analytics Engine (Micro-Lending Scorecard)
- Combined NER-extracted entities with metadata to profile vendors.

##  Features
- Multilingual transformer-based NER
- SHAP & LIME model interpretability
- Vendor micro-lending potential scoring
- Integration of entity recognition with engagement metadata
- Visual and tabular reports for model and vendor analysis