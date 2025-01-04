# THOS: A Two-Hand On-Skin Dynamic Gesture Dataset and Classification Network for HCI

Welcome to the official repository for the **THOS dataset** and evaluation codes! This repository accompanies our paper: *THOS: A Two-Hand On-Skin Dynamic Gesture Dataset and Classification Network for Human-Computer Interaction*. The repository contains evaluation codes to experiment with our dataset and reproduce the results discussed in the paper.

---

## Repository Contents

- **Evaluation Codes:** Python scripts to train and evaluate models using the THOS dataset.
- **Models:** Implementations of the Transformer Encoder, BiLSTM, and THOSnet architectures.
- **Utilities:** Helper scripts for preprocessing, metrics calculation, and visualization.
- **Documentation:** Detailed instructions on how to use the evaluation codes.

---

## Dataset Access

The **THOS dataset** is available for download via [Google Drive](#). The dataset includes 3,096 samples across nine two-hand on-skin gesture classes, recorded from three subjects.

### Dataset Features
- Hand landmarks extracted using [Mediapipe](https://google.github.io/mediapipe/).
- Includes gestures requiring physical contact between both hands.
- Formatted as lightweight 3D arrays for compatibility with various ML frameworks.

---

## Getting Started

### Prerequisites
Ensure you have the following installed:
- Python 3.8+
- TensorFlow 2.x
- Other dependencies listed in `requirements.txt`

Install the required packages using:
```bash
pip install -r requirements.txt
