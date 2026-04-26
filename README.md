# FinCrime-Anomaly-Engine: VAE-Based Zero-Day Fraud Detection

## Project Overview (AUSTRAC Context)
In the Australian financial landscape, traditional rule-based systems often fail to detect sophisticated **"Zero-Day" fraud**—new patterns that haven't been previously identified. This project implements a **Variational Autoencoder (VAE)** to identify anomalies in banking applications, specifically targeting **Structuring (Smurfing)** and **Synthetic Identity Fraud**.

By analyzing the "Latent Space" of transaction behaviors, this engine identifies deviations that suggest a breach of AUSTRAC compliance thresholds without requiring labeled historical fraud data.

## Features
* **Unsupervised Learning:** Uses a VAE architecture to learn the "Normal" baseline of Australian banking customers.
* **Behavioral Biometrics:** Incorporates 'Time-on-App' as a feature to detect automated synthetic ID bot behavior.
* **Threshold Tuning:** Includes a model-risk management phase to adjust sensitivity and reduce false positives.

## Technical Execution & Model Tuning
The project was developed in two distinct phases to simulate a professional Model Risk Management (MRM) workflow:

### Phase 1: Initial Anomaly Detection
The model was first run with a high-sensitivity threshold (**0.02**). While effective at catching all deviations, this resulted in "Alert Fatigue," flagging minor behavioral shifts as High Risk.

### Phase 2: Sensitivity Optimization (Threshold Adjustment)
I edited the engine logic to implement an **Adjusted Sensitivity Threshold (1.0)**. 
* **Reasoning:** This optimization ensures that manual investigation resources are prioritized for **Critical Alerts** (Extreme Structuring or clear Synthetic ID patterns), effectively managing the bank's operational capacity while maintaining AUSTRAC reporting standards.

## Visual Proof
### Detection Map (Latent Space Analysis)
![Detection Map]
<img width="801" height="688" alt="Screenshot 2026-04-25 204200" src="https://github.com/user-attachments/assets/f671f11f-bd15-4623-a44a-96eb895c709a" />



*This graph illustrates how the VAE separates 'Normal' AU patterns from 'Red' Fraudulent anomalies in the Latent Space.*

### Terminal Execution
![Bash Output]
<img width="1469" height="754" alt="Screenshot 2026-04-25 203942" src="https://github.com/user-attachments/assets/d8e6582c-7027-469a-bf4e-bc97cf7dcdc1" />


*Evidence of successful training and the Phase 1 vs Phase 2 threshold results.*

## Tools Used
* **Python 3.13**
* **TensorFlow / Keras** (Deep Learning Engine)
* **Matplotlib** (Data Visualization)
* **Scikit-Learn** (Data Scaling)
