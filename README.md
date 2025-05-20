# DL_Assignment_3 – Seq2Seq Transliteration with and without Attention

This repository contains the implementation of a character-level sequence-to-sequence (Seq2Seq) model for transliteration using the [Dakshina dataset](https://storage.googleapis.com/gresearch/dakshina/dakshina_dataset_v1.0.tar). It compares models trained **with attention** and **without attention** using PyTorch.

---

## 📁 Repository Structure

```
DL_Assignment_3/
│
├── WithAttention/
│   ├── assignment_3_with_attention.py            # Script with attention mechanism
│   ├── Assignment_3_with_attention.ipynb         # Notebook version
│   ├── readme.md                                 # Readme for attention model
│
├── WithoutAttention/
│   ├── assignment_3_without_attention.py         # Script without attention mechanism
│   ├── Assignment_3_without_attention.ipynb      # Notebook version
│   ├── readme.md                                 # Readme for non-attention model
│
├── predictions_attention/
│   ├── withAttention_correct_predictions.txt     # Correct predictions from attention model
│   └── withAttention_incorrect_predictions.txt   # Incorrect predictions from attention model
│
├── predictions_vanilla/
│   ├── withoutAttention_correct_predictions.txt  # Correct predictions from vanilla model
│   └── withoutAttention_incorrect_predictions.txt# Incorrect predictions from vanilla model
│
└── README.md                                     # Root README (this file)
```

---

## 🧠 Project Overview

The task is to transliterate from Latin-script input to the native script of Indian languages using Seq2Seq models. Two architectures are implemented:

- `WithAttention`: Uses Bahdanau Attention for improved sequence modeling.
- `WithoutAttention`: Basic encoder-decoder model without attention mechanism.

---

## 🔧 Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/Dhanushsirigineedi/DL_Assignment_3.git
   cd DL_Assignment_3
   ```

2. Install dependencies:
   ```bash
   pip install torch pandas numpy matplotlib wandb
   ```

3. (Optional) Login to Weights & Biases for tracking:
   ```bash
   wandb login
   ```

---

## 🚀 How to Run

Navigate to one of the folders (`WithAttention` or `WithoutAttention`) and run:

```bash
python assignment_3_with_attention.py
```

or

```bash
python assignment_3_without_attention.py
```

You can also open the `.ipynb` notebooks in Colab or Jupyter to visualize training step-by-step.

---

## 📊 Output

- Model predictions are evaluated and written to:
  - `withoutAttention_correct_predictions.txt`
  - `withoutAttention_incorrect_predictions.txt`
- Accuracy and loss are logged for training, validation, and optionally test sets.
- Visual and quantitative performance comparison between attention and non-attention models.

---

## 📂 Dakshina Dataset

The script automatically downloads and processes the dataset. If needed, you can download it manually from [Google Research](https://storage.googleapis.com/gresearch/dakshina/dakshina_dataset_v1.0.tar).

---

## 📈 Experiment Tracking

This project supports [Weights & Biases](https://wandb.ai) for experiment tracking. You can log training/validation metrics and visualize results online.

---

## ✍️ Authors

- Dhanush Sirigineedi

---
