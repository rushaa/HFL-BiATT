```markdown
# FedFinGuard: Trust-Aware Federated Learning for Adversarially Robust Financial Fraud Detection

This repository contains the official implementation of the **FedFinGuard** framework, as proposed in the paper **"Trust-Aware Federated Learning with Prototype Contrastive Attention for Adversarially Robust Financial Fraud Detection"**.

The framework introduces a privacy-preserving federated learning approach for credit card fraud detection. It integrates a feature tokenizer, bidirectional LSTM, and multi-head attention to capture complex sequential dependencies in transaction data. To address severe class imbalance and prevent minority class forgetting in non-independent and identically distributed (non-IID) settings, the architecture employs focal loss alongside a novel prototype contrastive loss. Furthermore, a trust-aware aggregation (TAA) mechanism dynamically evaluates client updates using norm clipping and cosine similarity, effectively neutralizing Byzantine gradient manipulation attacks.

The model was trained and evaluated on two widely used financial datasets: the **European Credit Card Fraud** dataset and the **Taiwan Credit Card Default** dataset.

---

## Datasets

If you wish to use the original datasets, please refer to the official sources below:

1. **European Credit Card Fraud** (Kaggle / ULB):  
   https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

2. **Taiwan Credit Card Default** (UCI Machine Learning Repository):  
   https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients

---

## Framework Architecture

The FedFinGuard architecture consists of four primary components:

1. **Feature Tokenizer**: Projects raw input features into multiple semantic groups to capture distinct aspects of transaction data.
2. **Bidirectional LSTM**: Captures sequential patterns and temporal dependencies among the tokenized features.
3. **Multi-Head Attention**: Models complex interactions between different feature representations.
4. **Trust-Aware Aggregation (TAA)**: A server-side defense mechanism that applies norm clipping, consensus scoring, and asymmetric reputation tracking to filter out malicious or anomalous client updates during federated averaging.

*(Note: Please ensure the framework diagram image path in your repository is updated to reflect the FedFinGuard architecture.)*

---

## Requirements

To run the experiments, ensure your environment meets the following dependencies:

- Python 3.8+
- PyTorch 1.8.0+
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- TQDM
- XGBoost (required for reproducing centralized baseline comparisons)

---

## Quick Start

### Installation

Clone the repository and install the required dependencies:

```bash
git clone https://github.com/Musaed98/FedFinGuard.git
cd FedFinGuard
pip install -r requirements.txt
```

### Usage

Below is an example command to initiate federated training on the European Credit Card Fraud dataset. Adjust the parameters according to your specific experimental setup:

```bash
python train.py --dataset european --clients 10 --rounds 15 --alpha 0.5 --local_epochs 3
```

For detailed configurations regarding dataset splits, model architectures, federated settings, and hyperparameters, please refer to Table 4 in the associated paper.

---

## Citation

If you find this work useful in your research, please consider citing the paper:

```bibtex
@article{alhuthaifi2026fedfinguard,
  title={Trust-Aware Federated Learning with Prototype Contrastive Attention for Adversarially Robust Financial Fraud Detection},
  author={Al-huthaifi, Musaed and Al-huthaifi, Rasha and Jamil, Izaan and Hijazi, Mohd},
  journal={Preprint submitted to Elsevier},
  year={2026}
}
```

---

## Contact

For questions, issues, or collaboration inquiries, please open an issue in this repository or contact the corresponding author:  
**Izaan Jamil** (izaan@ums.edu.my)
```
