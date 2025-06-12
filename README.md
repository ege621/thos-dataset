# Two-Hand On-Skin Gesture Recognition: A Dataset and Classification Network for Enhanced Human-Computer Interaction
---
## Introduction

- This is the official repo for the Tensorflow implementation of "Two-Hand On-Skin Gesture Recognition: A Dataset and Classification Network for Enhanced Human-Computer Interaction"
- THOS is the first dataset that solely conists of two-hand on-skin gestures, presented as landmarks.
- We also present THOSnet, a hybrid model based on transformer decoders and BiLSTM to classify two-hand gestures.

---
![Image (18)](https://github.com/user-attachments/assets/edb19e27-e0ed-4b3f-9876-96e53d2ffb34)


The Gesture_X predictions you see below should be treated as Gesture_(X-1) according to the above enumerations, since the gesture IDs start from 0 in our trial.
![output1](https://github.com/user-attachments/assets/5d704a2c-2f42-4645-a59e-fc8077fb896b)



## Dataset Access

The **THOS dataset** is available for download via [Google Drive](https://drive.google.com/drive/folders/1yynw27QOgJgfaQRcwvHpx7KFkSsOYKZE?usp=drive_link). The processed_datasets folder includes the augmented and non-augmented data for all three subjects in .npy format. In total, there are 3,096 non-augmented samples across nine two-hand on-skin gesture classes.

---

### Dataset Features
- Hand landmarks extracted using [Mediapipe](https://google.github.io/mediapipe/).
- See [Mediapipe Hands](https://mediapipe.readthedocs.io/en/latest/solutions/hands.html) for a detailed documentation.
- Includes gestures requiring physical contact between both hands.
- Formatted as a lightweight 3D array for compatibility with various ML models.

---

## Dataset Usage

Outisde of the processed_datasets folder, `dataset_20240709_X_3096.npy` and `dataset_20240709_y_3096.npy` consist of the entire non-augmented dataset. The first %60 percent of these arrays are the first subject, the next %20 is the second, and the remaining is the third subject. X should be in the shape of (3096,30,126) and y should be in the shape of (3096,9).

Kindly follow the below ${ROOT} folder structure while implementing this repository.
```
${ROOT}
|-- processed_datasets
|   |-- X_subject1_aug.npy
|   |-- X_subject1_original.npy
|   |-- X_subject2_aug.npy
|   |-- X_subject2_original.npy
|   |-- X_subject3_aug.npy
|   |-- X_subject3_original.npy
|   |-- y_subject1_aug.npy
|   |-- y_subject1_original.npy
|   |-- y_subject2_aug.npy
|   |-- y_subject2_original.npy
|   |-- y_subject3_aug.npy
|   |-- y_subject3_original.npy
|-- dataset_20240709_X_3096.npy
|-- dataset_20240709_y_3096.npy
|-- THOSnet_train.ipynb
|-- README.md
```


## Getting Started

### Prerequisites
Ensure you have the following installed:
- TensorFlow > 2.4.0 (The MultiHeadAttention block was introduced at this version.)
- Mediapipe is **not** necessary to go through the notebook, since the landmarks are already extracted.
- The latest version of Numpy might not be compatible with the specific version of Tensorflow that you use. This will mostly throw errors regarding `protobuf`.
- To utilize GPUs for training, check the `Python / Cuda / cudnn / Tensorflow` compatibility table [here](https://www.tensorflow.org/install/source#gpu)
- We highly recommend creating a virtual environment with the below configurations. This is the same configuration that we used for evaluation and training.

Commands below work on the Anaconda prompt on Windows, and on the regular Linux terminal, and thus, MacOS.
Create the virtual environment with Python version 3.8
```
conda create -n THOSenv python=3.8
conda activate THOSenv
```

Install cuda version 11.2 and cudnn version 8.1
```
conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1
```
Upgrade pip, and install Tensorflow version 2.10. Depending on your kernel, double equal symbol might give an error so use a single equal symbol or put tensorflow==2.10.* in quotations " ". 
```
pip install --upgrade pip
pip install tensorflow==2.10.*
```

Check if the installation is successful and your GPUs are showing up.
```
python -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
```

If for any reasyon your GPUs are not showing up, or the cuda installation in the virtual environment conflicts with an already existing NVIDIA driver, run the following command to only consider the cuda version present within the virtual environment, bypassing the system installation of cuda. This might especially be the case if you are accessing a cluster that is used by multiple people. 
```
export LD_LIBRARY_PATH=$CONDA_PREFIX/lib:$LD_LIBRARY_PATH
```

## Running the code
- You can split the jupyter notebook to multiple cells if desired.
- The code iterates over a hyperparameter tuning loop, in which the hyperparameters can be manually entered.
- The code supports the utilization of GPUs. Memory growth is also enabled. If your GPU has a compute capability greater than 7, you can also enable mixed precision.
- The nested for-loop in the code should not cause a compute bottleneck, since the code should be training-bound and epoch iterations take a considerably larger time than the for loop iterations.
- The dataset can easily be cached to system memory on most mid-tier rigs. Use a lower batch size if you encounter any OOM (Out of memory) errors during training.

This repo implements THOSnet on the THOS dataset. Here is the network architecture.
![Gesture user study roadmap - Frame 2](https://github.com/user-attachments/assets/b8c98399-3443-472c-8d68-006237ec11f6)


## Reference
Please cite our paper if you use the THOS dataset or THOSnet model in your research.

`Waiting for publication`
