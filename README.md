# Sentiment Analysis on SST-2 with Classical and Transformer Models

### Comparative Study of CNN and BERT-based Architectures for Binary Sentiment Classification

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-orange)
![PyTorch](https://img.shields.io/badge/PyTorch-Transformers-red)
![HuggingFace](https://img.shields.io/badge/HuggingFace-BERT-yellow)
![Dataset](https://img.shields.io/badge/Dataset-SST--2-green)

This project investigates sentiment classification on the Stanford Sentiment Treebank 2 (SST-2) dataset using three different approaches:

* CNN Baseline Model
* Off-the-Shelf BERT Model
* Fine-Tuned BERT Model

The objective is to compare classical deep learning methods with modern transformer-based architectures and analyze the performance gains achieved through transfer learning and fine-tuning.

---

## 📊 Models Evaluated

### CNN Baseline

A traditional convolutional neural network trained from scratch on the SST-2 dataset.

**Characteristics**

* Lightweight architecture
* Faster training
* Lower computational requirements
* Serves as a classical baseline

---

### Off-the-Shelf BERT

Evaluation of a pretrained BERT model without additional training.

**Characteristics**

* Zero task-specific training
* Direct transfer learning
* Measures pretrained language understanding capabilities

---

### Fine-Tuned BERT

Task-specific fine-tuning of BERT on SST-2.

**Characteristics**

* End-to-end supervised training
* Higher computational cost
* Expected best performance
* Utilizes mixed-precision (FP16) training

---

## 📂 Repository Structure

```text
Project/
│
├── README.md
├── requirements.txt
├── Report.pdf
│
└── Code/
    ├── 1_CNN_Baseline.ipynb
    ├── 2_BERT_Off_The_Shelf.ipynb
    └── 3_BERT_Fine_Tuned.ipynb
```

---

## 🛠️ Environment Setup

### Create Virtual Environment

```bash
python -m venv your_env_name
```

### Activate Environment

Windows:

```bash
activate
```

Linux / macOS:

```bash
source bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Launch JupyterLab

```bash
jupyter-lab
```

Open the notebooks inside the `Code` directory and execute the cells sequentially.

---

## 🚀 Running the Experiments

### CNN Baseline

```text
Code/1_CNN_Baseline.ipynb
```

* Trains CNN from scratch
* Prints validation accuracy
* Saves trained Keras model

---

### Off-the-Shelf BERT

```text
Code/2_BERT_Off_The_Shelf.ipynb
```

* No training required
* Evaluates pretrained BERT
* Reports Accuracy and F1 Score

---

### Fine-Tuned BERT

```text
Code/3_BERT_Fine_Tuned.ipynb
```

* Fine-tunes BERT on SST-2
* Approximately 1 hour training time
* Saves best model checkpoint
* Reports final evaluation metrics

---

## ⚙️ Reproducibility

To improve reproducibility:

* Fixed random seed: `SEED = 42`
* Run notebook cells sequentially
* Saved checkpoints have been removed to reduce repository size
* Re-running notebooks will regenerate all outputs and models

---

## ⚠️ GPU & Memory Requirements

A GPU is strongly recommended.

In Google Colab:

```text
Runtime → Change Runtime Type → GPU
```

### FP16 Training

The fine-tuning notebook uses mixed-precision training:

```python
fp16 = True
```

If your GPU does not support FP16:

```python
fp16 = False
```

If memory issues occur:

```python
per_device_train_batch_size = 2
```

or

```python
per_device_train_batch_size = 1
```

---

## 📈 Expected Results

* Results should closely match those reported in `Report.pdf`
* Minor variations are expected due to stochastic neural network training
* CNN results may vary slightly across runs
* Fine-tuned BERT should provide the strongest performance among the evaluated models

---

## 📄 Report

A detailed discussion of:

* Dataset preparation
* Model architectures
* Experimental setup
* Evaluation methodology
* Results and analysis

can be found in:

```text
Report.pdf
```

---

## 🧰 Technology Stack

* Python
* TensorFlow / Keras
* PyTorch
* Hugging Face Transformers
* Jupyter Notebook
* SST-2 Dataset

---

## 👨‍💻 Author

### Zoeb Ali Khan

* GitHub: [https://github.com/zoeb7184](https://github.com/zoeb7184)
* LinkedIn: [https://linkedin.com/in/zoeb-ali-khan](https://linkedin.com/in/zoeb-ali-khan)

---

## 📚 Academic Context

Developed as part of coursework exploring sentiment analysis, transfer learning, and transformer-based natural language processing models using the SST-2 benchmark dataset.

---
