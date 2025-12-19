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
