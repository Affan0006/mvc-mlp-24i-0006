# mvc-mlp-24I-0006

**MVC Project — Multilayer Perceptron from Scratch**  
**Course:** Artificial Neural Networks  
**Student Roll No:** 24I-0006  
**Institution:** National University of Computer and Emerging Sciences (FAST-NUCES)

---

## Project Overview

This repository contains a complete, hand-computed and Python-implemented Multilayer Perceptron (MLP) trained on the MNIST handwritten-digit dataset. The project is divided into **Tasks 1–7** covering forward propagation, loss calculation, backpropagation, weight updates, gradient descent variants, optimizers, and a full NumPy implementation.

---

## Repository Structure

```
mvc-mlp-24I-0006/
├── src/
│   └── MVC_MLP_24I-0006.ipynb      # Main Jupyter Notebook (all cells executed)
├── report/
│   └── MVC_Report_24I-0006.pdf     # Compiled LaTeX report (Springer LNCS)
└── README.md                        # This file
```

> **Note:** MNIST data is downloaded automatically in the notebook via `tensorflow.keras.datasets.mnist`. No manual download required.

---

## How to Run (Google Colab — Recommended)

1. Go to [https://colab.research.google.com](https://colab.research.google.com)
2. Click **File → Upload Notebook** and upload `src/MVC_MLP_24I-0006.ipynb`
3. Click **Runtime → Run all** (or press `Ctrl+F9`)
4. All outputs (loss curve, sample predictions, confusion matrix) will be generated and automatically downloaded

**Expected runtime:** ~10–20 minutes on Colab CPU; ~3–5 minutes on Colab GPU

---

## How to Run Locally

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/mvc-mlp-24I-0006.git
cd mvc-mlp-24I-0006

# 2. Create a virtual environment (optional but recommended)
python3 -m venv venv && source venv/bin/activate

# 3. Install dependencies
pip install numpy matplotlib jupyter tensorflow

# 4. Launch Jupyter and open the notebook
jupyter notebook src/MVC_MLP_24I-0006.ipynb
```

---

## Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| Python | ≥ 3.8 | Core language |
| NumPy | ≥ 1.21 | All matrix operations & gradient computations |
| Matplotlib | ≥ 3.4 | Loss curves & visualisations |
| TensorFlow / Keras | any | MNIST data loading **only** |
| PyTorch | optional | Gradient verification only (Cell 16) |

> **Rule (as per project spec):** All forward pass, backpropagation, and weight-update code uses **NumPy only**. PyTorch is used exclusively for gradient numerical verification.

---

## Network Architecture

```
Input (784)  →  Hidden Layer 1 (128, Sigmoid)  →  Hidden Layer 2 (64, Sigmoid)  →  Output (10, Sigmoid)
```

- **Total parameters:** 784×128 + 128 + 128×64 + 64 + 64×10 + 10 = **109,386**
- **Weight init:** Uniform [−0.5, 0.5], biases = 0, `np.random.seed(42)`
- **Loss:** Mean Squared Error (MSE)
- **Optimiser:** Mini-Batch SGD — Batch size 32, η = 0.1, 20 epochs

---

## Results

| Metric | Value |
|--------|-------|
| Final Train MSE | see notebook output |
| Final Test MSE | see notebook output |
| **Final Test Accuracy** | **see notebook output** |
| Epochs | 20 |
| Batch Size | 32 |
| Learning Rate | 0.1 |

---

## Generated Outputs

| File | Description | Task Requirement |
|------|-------------|-----------------|
| `loss_curve.png` | MSE loss & accuracy vs epoch | Required Output 1 |
| `sample_predictions.png` | 10 test images (one per digit class) with true/predicted labels | Required Output 3 |
| `confusion_matrix.png` | 10×10 confusion matrix on test set | Bonus |
| `mnist_samples.png` | Sample MNIST images visualisation | Exploratory |

---

## Manual Tasks (Tasks 1–6) Summary

Assigned weights for Roll No. 24I-0006:

| w1 | w2 | w3 | w4 | w5 | w6 | w7 | w8 | w9 | w10 | b¹ | b² |
|----|----|----|----|----|----|----|----|----|----|----|----|
| −0.16 | −0.16 | 0.38 | −0.31 | 0.24 | −0.53 | −0.57 | 0.15 | −0.75 | −0.08 | 0.25 | 0.13 |

Key manual results:
- Initial MSE (3 samples): **0.2944**
- ŷ for s¹ (x1=0.2, x2=0.8): **0.3983**
- After 5 SGD iterations: MSE ≈ **0.2851**
- See `report/MVC_Report_24I-0006.pdf` for complete step-by-step working

---

## Academic Integrity

This is an **individual project**. All calculations, code, and written report are the sole work of the student identified above. Submitted in partial fulfilment of the Artificial Neural Networks course requirements.
