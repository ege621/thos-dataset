# THOS: A Two-Hand On-Skin Dynamic Gesture Dataset and Classification Network for HCI
---
## Introduction

- This is the official repo for the Tensorflow implementation of "THOS: A Two-Hand On-Skin Dynamic Gesture Dataset and Classification Network for HCI"
- THOS is the first dataset that solely conists of two-hand on-skin gestures, presented as landmarks
- We also present THOSnet, a hybrid model based on transformer decoders and BiLSTM to classify two-hand gestures.

---
![Image (18)](https://github.com/user-attachments/assets/edb19e27-e0ed-4b3f-9876-96e53d2ffb34)



## Dataset Access

The **THOS dataset** is available for download via [Google Drive](https://drive.google.com/drive/folders/1JLaI7e01bHce2x0jsbi_Ql_fiOTsSmVk?usp=sharing). The processed_datasets folder includes the augmented and non-augmented data for all three subjects in .npy format. In total, there are 3,096 non-augmented samples across nine two-hand on-skin gesture classes.



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
