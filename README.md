# Tamil Tokenization: Task-Specific vs. Pretrained Models

##Overview
This repository contains the models, and dataset used for the research paper **"Optimizing Tamil Tokenizers: The Limits of Pretrained Models."** The study focuses on training task-specific tokenizers for Tamil and comparing them against pretrained tokenizers like IndicBERT and mBERT. Soon the paper will get published.

## Project Description
Tamil is a morphologically rich and agglutinative language, making tokenization a challenging task. Generic pretrained tokenizers often fail to segment Tamil text effectively. This project introduces three task-specific tokenizers trained on a Tamil news dataset and evaluates their performance using multiple metrics.

## Repository Structure
```
├── dataset/                     
│   ├── train.csv                 
│   ├── test.csv                 
│   ├── val.csv                  
│   ├── tokenizer_training_data.txt 
│
├── tokenizers/                   
│   ├── tokenizer_bpe_32k.model
│   ├── tokenizer_unigram_8k.model
│   ├── tokenizer_wordpiece_8k.model
│
├── vocab/                   
│   ├── tokenizer_bpe_32k.model
│   ├── tokenizer_unigram_8k.model
│   ├── tokenizer_wordpiece_8k.model
│
├── README.md
```

# Dataset Details

The dataset consists of Tamil news headlines categorized into six domains:

- Tamil Nadu
- India
- Cinema
- Sports
- Politics
- World

**Dataset Splits:**
- Train Set: 14,521 samples
- Test Set: 3,631 samples
- Validation Set: 1,815 samples

**Preprocessing Steps:**
- Text normalization
- Punctuation handling
- Whitespace correction
- Noise removal

These steps ensure high-quality tokenization.

## Trained Tokenizers

The following models are trained on the Tamil news dataset:

- BPE-32K
- Unigram-8K
- WordPiece-8K

Each model is stored in the `tokenizers/` directory and can be loaded using the `sentencepiece` library.

## Evaluation Metrics

The tokenizers were evaluated based on the following metrics:

- **Out-of-Vocabulary (OOV) Rate**: Measures how well the tokenizer handles unseen words.
- **Perplexity**: Assesses tokenization efficiency by modeling word distributions.
- **BLEU Score & Self-BLEU Score**: Determines tokenization consistency and diversity.
- **Compression Ratio**: Evaluates text compression effectiveness.
- **Token Variance & Distinct Token Ratio**: Analyzes token distribution and fragmentation.

## Key Findings

- BPE-32K outperformed other tokenizers, achieving the best balance between segmentation efficiency and vocabulary coverage.
- IndicBERT and mBERT struggled with Tamil-specific segmentation, leading to higher perplexity and token fragmentation.
- Task-specific tokenization significantly improved performance, reinforcing the importance of dataset-aware tokenizers for Tamil NLP.
