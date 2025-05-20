# Seq2Seq Transliteration Model with Attention

## Overview

This project implements an attention-based sequence-to-sequence (Seq2Seq) model for transliteration tasks using the Dakshina dataset. The model converts text from Latin script to native Indian scripts (e.g., Telugu) using Bahdanau attention mechanism to improve translation accuracy.

## Key Features

- **Attention Mechanism**: Implements Bahdanau (additive) attention for better alignment between input and output sequences
- **Flexible Architecture**: Supports multiple RNN types (RNN, GRU, LSTM) with configurable layers
- **Bidirectional Encoder**: Optional bidirectional processing of input sequences
- **Teacher Forcing**: Configurable ratio for training stability
- **Visualization Tools**: Includes attention visualization for model interpretability
- **WandB Integration**: Comprehensive hyperparameter tuning and experiment tracking

## Requirements

- Python 3.6+
- PyTorch
- pandas
- wandb
- requests (for dataset download)
- matplotlib (for attention visualization)

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

### Training with Attention

1. Log in to WandB:
   ```bash
   wandb login
   ```

2. Run the attention model:
   ```bash
   python assignment_3_with_attention.py
   ```

### Key Differences from Non-Attention Version

- Uses Bahdanau attention mechanism
- Additional attention visualization capability
- Typically achieves higher accuracy than non-attention version
- More complex decoder architecture to handle attention context

## Configuration

The sweep configuration includes all parameters from the non-attention version plus:

- **Attention-specific parameters**:
  - Automatic attention context integration
  - Attention weight visualization capability

## Model Architecture

1. **Encoder**:
   - Embedding layer
   - Bidirectional RNN (RNN/GRU/LSTM)
   - Handles variable-length sequences with packing

2. **Attention Mechanism**:
   - Bahdanau (additive) attention
   - Computes alignment scores between decoder hidden state and encoder outputs

3. **Decoder**:
   - Embedding layer
   - Attention context integration
   - RNN layer (RNN/GRU/LSTM)
   - Output projection with combined features

## Results

The model provides:
- Training/validation loss and accuracy metrics
- Test set evaluation
- Example predictions with attention visualization
- Best model saved as `best_model.pt`

## Visualization

Use the `visualize_attention()` function to:
1. Generate attention heatmaps
2. Show alignment between source and target characters
3. Interpret model decisions

Example usage:
```python
prediction, attn_weights = visualize_attention(model, "example", src_vocab, tgt_vocab, device)
plt.imshow(np.array(attn_weights), cmap='hot', interpolation='nearest')
plt.show()
```
