# THOS: A Two-Hand On-Skin Dynamic Gesture Dataset and Classification Network for HCI
---
## Introduction

- This is the official repo for the Tensorflow implementation of "THOS: A Two-Hand On-Skin Dynamic Gesture Dataset and Classification Network for HCI"
- THOS is the first dataset that solely conists of two-hand on-skin gestures, presented as landmarks
- We also present THOSnet, a hybrid model based on transformer decoders and BiLSTM to classify two-hand gestures.

---
![Image (18)](https://github.com/user-attachments/assets/edb19e27-e0ed-4b3f-9876-96e53d2ffb34)



## Dataset Access

The **THOS dataset** is available for download via [Google Drive](https://drive.google.com/drive/folders/1yynw27QOgJgfaQRcwvHpx7KFkSsOYKZE?usp=drive_link). The processed_datasets folder includes the augmented and non-augmented data for all three subjects in .npy format. In total, there are 3,096 non-augmented samples across nine two-hand on-skin gesture classes.

---

### Dataset Features
- Hand landmarks extracted using [Mediapipe](https://google.github.io/mediapipe/).
- Includes gestures requiring physical contact between both hands.
- Formatted as lightweight 3D arrays for compatibility with various ML frameworks.

---

## Dataset Usage

Outisde of the processed_datasets folder, `dataset_20240709_X_3096.npy` and `dataset_20240709_y_3096.npy` consist of the entire non-augmented dataset. The first %60 percent of these arrays are the first subject, the next %20 is the second, and the remaining is the third subject. X should be in the shape of (3096,30,126) and y should be in the shape of (3096,9).

${ROOT}
|-- processed_datasets
|   |-- dataset_1.npy
|   |-- dataset_2.npy
|   |-- dataset_3.npy
|   |-- dataset_4.npy
|   |-- dataset_5.npy
|   |-- dataset_6.npy
|   |-- dataset_7.npy
|   |-- dataset_8.npy
|   |-- dataset_9.npy
|   |-- dataset_10.npy
|   |-- dataset_11.npy
|   |-- dataset_12.npy
|-- original_data.npy
|-- original_labels.npy
|-- THOSnet_train.ipynb
|-- README.md



## Getting Started

### Prerequisites
Ensure you have the following installed:
- TensorFlow > 2.4.0 (The MultiHeadAttention block was introduced at this version.)
- Mediapipe is **not** necessary to go through the notebook, since the landmarks are already extracted.

## Running the code
- You can split the jupyter notebook to multiple cells if desired.
- The code iterates over a hyperparameter tuning loop, in which the hyperparameters can be manually entered.
- The code supports the utilization of GPUs. Memory growth is also enabled. If your GPU has a compute capability greater than 7, you can also enable mixed precision.
