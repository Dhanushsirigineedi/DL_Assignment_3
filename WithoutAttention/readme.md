# Seq2Seq Transliteration Model without Attention

## Overview

This project implements a sequence-to-sequence (Seq2Seq) model for transliteration tasks using the Dakshina dataset. The model converts text from Latin script to native Indian scripts (e.g., Telugu) without using attention mechanisms.

## Features

- Character-level vocabulary handling with special tokens
- Configurable encoder-decoder architecture
- Support for different RNN types (RNN, GRU, LSTM)
- Bidirectional encoder option
- Teacher forcing during training
- WandB integration for hyperparameter tuning

## Requirements

- Python 3.6+
- PyTorch
- pandas
- wandb
- requests (for dataset download)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/seq2seq-transliteration.git
   cd seq2seq-transliteration
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Training the Model

1. First, log in to WandB:
   ```bash
   wandb login
   ```

2. Run the main script:
   ```bash
   python assignment_3_without_attention.py
   ```

### Configuration

The model uses WandB for hyperparameter tuning. The sweep configuration includes:

- Model architecture parameters:
  - Embedding size
  - Hidden size
  - Number of encoder layers
  - RNN cell type (RNN, GRU, LSTM)
  - Bidirectional encoder

- Training parameters:
  - Dropout rate
  - Learning rate
  - Batch size
  - Number of epochs
  - Teacher forcing ratio
  - Optimizer choice

### Data

The script automatically downloads and processes the Dakshina dataset for Telugu transliteration. The dataset contains parallel text in Latin script and native Indian scripts.

## File Structure

- `assignment_3_without_attention.py`: Main implementation file containing:
  - Vocabulary and dataset classes
  - Model architecture (encoder, decoder, Seq2Seq)
  - Training and evaluation functions
  - Main execution logic

## Results

The model outputs:
- Training and validation loss/accuracy
- Test set accuracy
- Example predictions from the validation set

The best model weights are saved as `best_model.pt`.

## Customization

To use a different language from the Dakshina dataset:
1. Modify the `language` parameter in the `main()` function
2. Ensure the corresponding dataset files are available

