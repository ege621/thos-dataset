# THOS: A Two-Hand On-Skin Dynamic Gesture Dataset and Classification Network for HCI
---
## Introduction

- This is the official repo for the Tensorflow implementation of "THOS: A Two-Hand On-Skin Dynamic Gesture Dataset and Classification Network for HCI"
- THOS is the first dataset that solely conists of two-hand on-skin gestures, presented as landmarks
- We also present THOSnet, a hybrid model based on transformer decoders and BiLSTM to classify two-hand gestures.

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
