
## Overview

This repository showcases a complete OCR solution tailored for Vietnamese scene text recognition. It utilizes the MC_OCR dataset and follows a two-step architecture:

- **Text Detection** powered by PaddleOCR
- **Text Recognition** via a custom-built CNN + Transformer model implemented in PyTorch

---

## Key Highlights

- **Modular Two-Stage Pipeline**: separates detection and recognition for improved flexibility and precision
- **Custom Recognition Architecture**: combines CNN-based feature extraction with Transformer-based decoding
- **Vietnamese Dataset Integration**: supports polygon-labeled data from MC_OCR
- **Performance Metrics**: evaluated using Character Error Rate (CER) and Sequence Accuracy
- **Visual Feedback**: overlays bounding boxes and recognized text directly on input images

---

## Model Architecture

### CNN Encoder

- Based on the CRNN architecture
- Transforms text-line images into sequential visual representations

### Decoder – Transformer

- Incorporates both self-attention and cross-attention mechanisms
- Generates character sequences in an autoregressive manner

---

## Execution Guide

This project is fully implemented within a single Google Colab notebook.

### Requirements

- A Google Account with access to Google Drive
- Upload the MC_OCR dataset to your Drive
- Update the following paths in the notebook:

```python
DRIVE_PATH = '/content/drive/MyDrive/DeepLearning/Final/'
TRAIN_CSV_PATH = DRIVE_PATH + 'Dataset/mcocr_public/mcocr_train_data/mcocr_train_df.csv'
TRAIN_IMG_DIR = DRIVE_PATH + 'Dataset/mcocr_public/mcocr_train_data/train_images/'
````

### Workflow

1. **Launch the notebook** in Google Colab
2. **Enable GPU support** via runtime settings
3. **Mount Google Drive** and install necessary libraries
4. **Execute notebook cells in order**:

   * Preprocessing: parses polygon-based annotations from MC_OCR csv
   * Model: builds the CNN + Transformer OCRModel
   * Training: saves the best-performing model based on validation CER
   * Evaluation: calculates final Character Error Rate and Sequence Accuracy
   * Inference: displays predictions on sample images

---

## Evaluation Summary

| Metric                     | Score        |
| -------------------------- | ------------ |
| Test Loss                  |    0.4042    |
| Character Error Rate (CER) |    0.1502    |
| Sequence Accuracy          |    59.03%    |


---

## Acknowledgments

This project was developed by me as part of the **Deep Learning final project** at **Ton Duc Thang University**.

For inquiries or collaboration, feel free to reach out: [nguyentrungthang2901@gmail.com](mailto:nguyentrungthang2901@gmail.com)

---





