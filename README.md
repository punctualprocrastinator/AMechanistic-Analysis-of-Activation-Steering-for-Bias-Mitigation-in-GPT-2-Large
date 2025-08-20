

---

# A Mechanistic Analysis of Activation Steering for Bias Mitigation in GPT-2 Large

This repository contains the official implementation for the paper "A Mechanistic Analysis of Activation Steering for Bias Mitigation in GPT-2 Large," accepted to the 2nd Workshop on Mechanistic Interpretability at NeurIPS 2024.

This project presents an end-to-end system that uses techniques from mechanistic interpretability to identify and actively mitigate bias within the internal workings of the GPT-2 Large model.

## 🚀 Overview

Rather than treating large language models as black boxes, this project explores the internal representations of GPT-2 Large to understand how concepts like social bias are encoded. By uncovering these mechanisms, we are able to directly intervene and reduce bias in model outputs.

## Key Findings

- Representations of bias become linearly separable and highly detectable in the later layers (16-35) of the GPT-2 Large architecture.
- By intervening at these precise locations, the system can mitigate bias in real-time, without retraining or fine-tuning the model.

## ✨ Core Features

- **Systematic Layer-wise Analysis:** Detailed, layer-by-layer analysis of where bias is represented across all 36 layers of GPT-2 Large.
- **End-to-End Reproducible System:** Complete pipeline from data generation to real-time steering.
- **Built with TransformerLens:** Implementation uses the standard TransformerLens interpretability library.
- **Real-Time Mitigation:** Demonstration of bias mitigation during inference without expensive retraining.

## 🛠️ Setup and Installation

This project is optimized for Google Colab with a GPU runtime.

1. **Clone the repository**
   ```bash
   git clone 
   cd AMechanistic-Analysis-of-Activation-Steering-for-Bias-Mitigation-in-GPT-2-Large
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## ⚡ How to Run

To run the full pipeline (training probes, computing steering vectors, and testing mitigation), execute the main script:

```bash
python main.py
```

The script will:

1. Load the GPT-2 Large model using TransformerLens.
2. Generate a synthetic dataset of biased and neutral statements.
3. Train a diagnostic linear probe for each of the 36 layers to detect bias.
4. Compute the steering vectors using Contrastive Activation Addition (CAA).
5. Run tests for both bias detection and bias mitigation, printing results to the console.

## 📄 License

This repository is released under the MIT License.

## 🤝 Contributions

Contributions, issues, and feature requests are welcome! Feel free to open an issue or submit a pull request.

---

Let me know if you want any further customization or to include other sections! If you'd like this new README committed to your repository, just say so.
