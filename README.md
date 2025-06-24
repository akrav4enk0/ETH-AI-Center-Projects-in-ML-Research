3D Seismic Wavefield Prediction using SwinUNETR
This repository contains the final poster and associated documentation for our project "3D Seismic Wavefield Prediction using SwinUNETR", developed as part of the AI Center Projects in Machine Learning Research (FS2025) at ETH Zurich.

Overview
Accurate forecasting of seismic wave propagation is essential for hazard mitigation and early warning systems. This project explores the adaptation of transformer-based architectures—specifically SwinUNETR—to model 3D seismic wavefields using synthetic data from the HEMEW-3D dataset.

We trained a 3D SwinUNETR model to predict future displacement fields from past wavefield snapshots and geological inputs. Our goal was to evaluate the model's capability to learn long-range spatio-temporal patterns and benchmark its performance against existing approaches.

Objectives
Implement the SwinUNETR architecture for seismic forecasting.

Train and validate the model on a downsampled subset (10Hz) of the HEMEW-3D dataset.

Evaluate performance using MAE, RMSE, and R² metrics.

Visualize qualitative outputs through heatmaps and line plots.

Lay the foundation for future large-scale and high-resolution training (50Hz).

Dataset
HEMEW-3D: A high-fidelity synthetic dataset of 30,000 3D simulations of seismic wave propagation in heterogeneous geological media.

For this project, a 10Hz version with 10,000 samples was used.

Each sample includes:

3-component velocity wavefields (uE, uN, uZ)

Geological velocity model (VS)

32×32×32 voxel resolution with 2000 time steps (only a subset used)

Methods
Input tensor: 4 channels (3 past displacements + 1 velocity model)

Output: Future displacements in three directions

Architecture: SwinUNETR (shifted-window transformer with U-Net-like decoder)

Loss Function: Custom L1 loss with small denominator regularization

Evaluation Metrics: MAE, RMSE, R²

Results
The model showed promising qualitative performance, particularly in capturing structural wave patterns. However, peak amplitudes in high-gradient zones were often underestimated. Visualizations and metric plots are included in the final poster.

Poster
🖼 You can find the final poster here.
It includes detailed sections on:

Introduction & Objectives

Related Work

Dataset Description

Methodology

Visual & Quantitative Results

Conclusions & Future Work

Authors
Aydin Javadov: Model architecture & training, experimentation, visualizations

Anna Kravchenko: Initial prototyping, theoretical structuring, poster layout & writing

References
HEMEW-3D Dataset (ESSD 2024)

Swin UNETR (arXiv:2201.01266)

Multiple-Input FNO (JCP 2025)

