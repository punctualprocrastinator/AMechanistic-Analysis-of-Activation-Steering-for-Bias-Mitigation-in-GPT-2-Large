A Mechanistic Analysis of Activation Steering for Bias Mitigation in GPT-2 Large
This repository contains the official implementation for the paper "A Mechanistic Analysis of Activation Steering for Bias Mitigation in GPT-2 Large," accepted to the 2nd Workshop on Mechanistic Interpretability at NeurIPS 2025.

This project provides a complete, end-to-end system that uses techniques from mechanistic interpretability to both identify and actively mitigate bias directly within a model's internal workings. Our contribution is a systematic, layer-by-layer analysis of the foundational Contrastive Activation Addition (CAA) method, offering a reproducible baseline and educational tool for the community.

🚀 Overview
Instead of treating large language models as black boxes, this project "looks inside" to understand how and where gpt2-large represents abstract concepts like social bias. We use this understanding to perform real-time interventions, steering the model away from generating harmful content without any retraining.

Key Findings
Our analysis reveals that representations of bias become linearly separable and highly detectable in the later layers (16-35) of the gpt2-large architecture. By intervening at these precise locations, we can effectively mitigate biased outputs with minimal intervention.

Figure 1: Bias detection accuracy (AUC) of probes trained on the residual stream activations at each layer of gpt2-large. Performance increases dramatically and plateaus in the later layers.

Figure 2: PCA visualization of activations from the most predictive layer (blocks.16.hook_resid_post), showing a clear linear separation between neutral (blue) and biased (red) examples.

✨ Core Features
Systematic Layer-wise Analysis: The first detailed, layer-by-layer analysis of where bias is represented across all 36 layers of gpt2-large.

End-to-End Reproducible System: A complete, documented pipeline from data generation to real-time steering.

Built with TransformerLens: A clean, educational implementation using the standard TransformerLens interpretability library.

Real-Time Mitigation: A demonstration of bias mitigation during inference without costly fine-tuning or retraining.
🛠️ Setup and Installation
This project is optimized for Google Colab with a GPU runtime.

# 1. Clone the repository
git clone
cd Activation-Steering-for-Bias-Mitigation

# 2. Install dependencies
pip install -r requirements.txt

⚡ How to Run
To run the full pipeline (training probes, computing steering vectors, and testing mitigation), execute the main script:

python main.py

The script will perform the following steps:

Load the gpt2-large model using TransformerLens.

Generate the synthetic dataset of biased and neutral statements.

Train a diagnostic linear probe for each of the 36 layers to detect bias.

Compute the steering vectors using Contrastive Activation Addition (CAA).

Run tests for both bias detection on new sentences and bias mitigation on biased prompts, printing the results to the console.
