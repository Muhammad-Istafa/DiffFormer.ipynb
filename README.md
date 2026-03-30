# Hyperspectral Image Classification with Deep Spatial-Spectral Transformer (DSST)

## Project Overview
This project implements a Deep Spatial-Spectral Transformer (DSST) model for hyperspectral image (HSI) classification. It demonstrates the model's application on two well-known HSI datasets: Pavia University and WHU-Hi-HanChuan. The goal is to accurately classify land-cover types using both spatial and spectral information from HSI data.

## Problem Description
Hyperspectral image classification is a challenging task due to the high dimensionality of spectral data, limited labeled samples, and the need to effectively combine spatial and spectral features. Traditional methods often struggle with these complexities. This project addresses these issues by leveraging a transformer-based architecture to capture intricate spatial-spectral relationships.

## Datasets Used

### 1. Pavia University Dataset
*   **Description**: An urban area dataset captured by the Reflective Optics System Imaging Spectrometer (ROSIS) sensor over Pavia, Italy. It features a high spatial resolution with 103 spectral bands.
*   **Key Characteristics**: Contains 9 distinct land-cover classes.

### 2. WHU-Hi-HanChuan Dataset
*   **Description**: A dataset of a rural area in HanChuan, China, collected by the Headwall Nano-Hyperspec sensor. It has a high spatial resolution with 274 spectral bands.
*   **Key Characteristics**: Contains 16 distinct land-cover classes.

## Method: Deep Spatial-Spectral Transformer (DSST)
The DSST model is designed to process hyperspectral data by extracting spatial-spectral patches and employing a transformer architecture. This approach allows the model to:
*   **Capture Spatial Features**: Convolutional layers are used to extract local spatial context within each patch.
*   **Model Spectral Dependencies**: The transformer encoder effectively captures long-range dependencies across spectral bands, which is crucial for distinguishing between spectrally similar materials.
*   **Integrate Information**: The model integrates these features to make robust pixel-wise classifications.

## Results
The DSST model demonstrated strong performance on both datasets:

### Pavia University Dataset
*   **Test Accuracy**: Approximately 96.83%
*   **Test Loss**: Approximately 0.0789

### WHU-Hi-HanChuan Dataset
*   **Test Accuracy**: Approximately 94.78%
*   **Test Loss**: Approximately 0.1539

Detailed classification reports and confusion matrices for both datasets are generated during the training process, providing per-class precision, recall, and F1-scores.

## How to Run the Project

### Prerequisites
*   Python 3.x
*   Git
*   Access to Google Drive with the datasets (if running in Colab or a similar environment).

### Setup
1.  **Clone the repository**:
    ```bash
    git clone https://github.com/mahmad000/DiffFormer.git
    cd DiffFormer
    ```

2.  **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3.  **Download Datasets**:
    *   Place `PaviaU.mat`, `PaviaU_gt.mat`, `WHU_Hi_HanChuan.mat`, and `WHU_Hi_HanChuan_gt.mat` into a directory named `diffFormer` in your Google Drive's root, or ensure they are accessible at the `DATA_PATH` specified in `train.py` (default: `/content/drive/MyDrive/diffFormer/`).
    *   The `train.py` script includes logic to copy these files to a local `/content/DiffFormer/HSI/` directory for faster access if running in a Colab-like environment.

### Execution
To run the training and evaluation for both datasets, execute the `train.py` script:
```bash
python train.py
