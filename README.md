# RF-Autoencoder
RF Anomaly Detection Using Autoencoders

A minimalist implementation for detecting anomalous RF signals using reconstruction error.

Overview

This project explores how autoencoders can identify abnormal RF activity by learning the baseline characteristics of “normal” signals. Using the RML2016.10a dataset, the model is trained exclusively on standard modulation types (QPSK, BPSK) and then evaluated on signals outside this baseline.

Autoencoders reconstruct familiar patterns accurately—but struggle with unfamiliar ones.
This reconstruction error becomes a powerful anomaly signal.

The goal of this repo is to provide a clean, minimal, reproducible pipeline suitable for both learning and demonstrating the core idea behind RF anomaly detection.
