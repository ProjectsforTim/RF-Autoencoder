#RF-Autoencoder

Anomaly Detection in RF Signals Using Autoencoders

A compact, reproducible implementation for detecting anomalous RF activity using reconstruction error.
Built around the RML2016.10a wireless dataset, this project uses an autoencoder to learn what normal modulation patterns look like—then flags signals that deviate from this learned baseline.

🚀 Overview

Modern RF environments (Wi-Fi, telemetry, drone control links, Bluetooth, broadcast, etc.) are noisy and dynamic. Spotting unusual or unknown signals inside this spectrum is increasingly important for:

Counter-UAS systems

Electronic warfare

Spectrum monitoring

Interference analysis

Security and device detection

Autoencoders offer a simple but powerful approach:

If a model learns to accurately reconstruct only “normal” RF signals, it will produce higher error for unseen or abnormal signals.
This reconstruction error becomes the anomaly score.

📡 How It Works
1. Data Source

This project uses the open-source RML2016.10a dataset, which contains labeled I/Q radio signals across many modulation types and SNRs.

2. Spectrogram Conversion

Each I/Q sample is transformed into a log-power spectrogram, providing a compact and visually interpretable RF snapshot.

3. Training on “Normal” Signals Only

The autoencoder is trained exclusively on standard modulation types (e.g., QPSK, BPSK) across reasonable SNR ranges.

4. Reconstruction Error for Anomaly Detection

Unfamiliar or abnormal modulations (e.g., AM-DSB, 8PSK, WBFM) produce higher reconstruction error.
A threshold defines what counts as “anomalous.”

🧠 Model Architecture (Autoencoder)

Dense autoencoder

Latent dimension: 64

Loss: MSE

Optimizer: Adam

The model is intentionally lightweight so the project remains simple, reproducible, and easy to extend.

The script will:

✔ Load dataset
✔ Build spectrograms
✔ Normalize + flatten
✔ Train autoencoder
✔ Print training metrics

📊 Example Output

Once integrated with your own notebook visualizations, you can generate:

Reconstruction error histograms

Spectrogram comparisons

Confusion matrices for anomaly performance

Reconstruction samples

I'm keeping my visualisation code a secret but it's not hard to make your own 😎
