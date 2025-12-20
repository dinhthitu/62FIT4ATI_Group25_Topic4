# Setup & Reproduction Guide

This document describes how to set up the environment and reproduce the results of this project.

---

## 1. Setup (Google Colab Recommended)

### 1.1 Open Google Colab
- Go to: https://colab.research.google.com
- Create a new notebook or open the provided `.ipynb` file
- Paste the full source code into the notebook or upload the notebook directly

---

### 1.2 Install Dependencies
Run the following cell to install all required libraries:

```bash
!pip install torch torchvision
!pip install transformers tqdm scikit-learn pandas matplotlib seaborn

### 1.3 Enable GPU
- Navigate to **Runtime → Change runtime type**
- Set **Hardware accelerator** to **GPU**
- Recommended: **T4 GPU or better**

---

## 2. Data Preparation

### 2.1 Download Dataset
The dataset can be downloaded from:  
https://drive.google.com/drive/folders/1b4KvfO_Vid9HputdJwATAQBmYImWhmgR?usp=share_link

**Required files:**
- `train.csv`
- `test.csv`

---

### 2.2 Upload Data to Colab
Upload `train.csv` and `test.csv` to the Colab working directory (e.g. `/content/`).

The files can be provided using any of the following methods:
- Upload via the **Colab Files panel**
- Mount **Google Drive** and place the files in Drive
- Clone from a **GitHub repository** (if applicable)

> **Note**  
> The code assumes that `train.csv` and `test.csv` already exist in the working directory.  
> No specific upload method is required.

---

## 3. Reproducing the Results

Follow the steps below to reproduce the results:

1. Open the notebook in **Google Colab**  
   (or run the `.py` script locally on a machine with GPU support)
2. Ensure that:
   - All dependencies are installed
   - GPU acceleration is enabled
   - `train.csv` and `test.csv` are present in the working directory
3. Run all cells sequentially from top to bottom

---

## 4. Execution Workflow

Running the notebook will perform the following steps:

- Load and preprocess the dataset
- Train a **RoBERTa-based model** using **5-fold cross-validation**
  - Approximate training time: **~3–4 hours per fold on a T4 GPU**
- Save the best model checkpoint for each fold:
  ```text
  best_roberta_fold_X.pth
