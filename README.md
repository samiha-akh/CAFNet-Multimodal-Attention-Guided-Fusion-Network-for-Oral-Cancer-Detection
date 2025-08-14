# CAFNet: Multimodal Attention-Guided Fusion Network for Oral Cancer Detection

This repository contains the implementation of **CAFNet** (Cross-Attention Fusion Network), a deep learning model designed for **oral cancer detection** using **multimodal microscopy images** — specifically **Brightfield (BF)** and **Fluorescence (FL)** images.  

The model integrates **channel attention** and **adaptive fusion blocks** to combine features from multiple imaging modalities, leveraging both low-level and high-level representations for improved classification accuracy.

---

##  Features

- **Multimodal Input Support**: Simultaneously processes Brightfield (RGB) and Fluorescence (RGBA) microscopy images.  
- **CAFNet Architecture**: Combines **Channel Attention (CABlock)** and **Adaptive Fusion (AFBlock)** for cross-modal feature alignment.  
- **Custom Swish Activation**: Implements a trainable, memory-efficient variant of the Swish activation function.  
- **Mixed Precision Training**: Uses `torch.cuda.amp` for faster and memory-efficient training.  
- **Patient-Wise Data Splitting**: Prevents data leakage by stratifying train/validation sets on patient IDs.  
- **Training Visualization**: Plots loss and AUC curves for easy monitoring.  
- **Early Stopping**: Stops training if validation performance plateaus.  

---

##  Dataset Structure

Expected input directory structure:

- **BF**: Brightfield images (RGB)  
- **FL**: Fluorescence images (RGBA)  
- **train.csv**: CSV file with columns:
    - `Name` – filename of the sample
    - `Diagnosis` – label (0 or 1 for cancer diagnosis)

---

## Results

- Loss vs Accuracy Curve
<img width="1189" height="490" alt="cafnet loss vs auc" src="https://github.com/user-attachments/assets/c8aa03c3-ea85-4de7-9ed3-619d24e43a6c" />


- Score on Hidden Test Set: 0.7538
