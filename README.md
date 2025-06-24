# 3D Transformer for Earthquake Prediction 
*ETH Zurich – AI Center Projects in Machine Learning Research.*

---

## 📘 Overview
This repository contains the final poster and associated documentation (to be added) for the project "3D Transformer for Earthquake Prediction", developed as part of the AI Center Projects in Machine Learning Research at ETH Zurich.

---

## Outline
Accurate forecasting of seismic wave propagation is essential for hazard mitigation and early warning systems. This project explores the adaptation of transformer-based architectures—specifically SwinUNETR—to model 3D seismic wavefields using synthetic data from the HEMEW-3D dataset.

We trained a 3D SwinUNETR model to predict future displacement fields from past wavefield snapshots and geological inputs. Our goal was to evaluate the model's capability to learn long-range spatio-temporal patterns and benchmark its performance against existing approaches.

---

## Objectives
- Implement the SwinUNETR architecture for seismic forecasting.
- Train and validate the model on a downsampled subset (10Hz) of the HEMEW-3D dataset.
- Evaluate performance using MAE, RMSE, and R² metrics.
- Visualize qualitative outputs through heatmaps and line plots.
- Lay the foundation for future large-scale and high-resolution training (50Hz).

---

## Dataset
HEMEW-3D: A high-fidelity synthetic dataset of 30,000 3D simulations of seismic wave propagation in heterogeneous geological media.

For this project, a 10Hz version with 10,000 samples was used.

Each sample includes:
- 3-component velocity wavefields (uE, uN, uZ)
- Geological velocity model (VS)
- 32×32×32 voxel resolution with 2000 time steps (only a subset used)

---

## Methods
- Input tensor: 4 channels (3 past displacements + 1 velocity model)
- Output: Future displacements in three directions
- Architecture: SwinUNETR (shifted-window transformer with U-Net-like decoder)
- Loss Function: Custom L1 loss with small denominator regularization
- Evaluation Metrics: MAE, RMSE, R²

---

## Results
The model showed promising qualitative performance, particularly in capturing structural wave patterns. However, peak amplitudes in high-gradient zones were often underestimated. Visualizations and metric plots are included in the final poster.

---

## 🖼 Poster
You can find the final poster here.
It includes detailed sections on:

- Introduction & Objectives
- Related Work
- Dataset Description
- Methodology
- Visual & Quantitative Results
- Conclusions & Future Work

---

## Authors
Aydin Javadov: Model architecture & training, experimentation, visualizations

Anna Kravchenko: Initial prototyping, theoretical structuring, poster layout & writing

## References
1. F. Lehmann, F. Gatti, M. Bertin, D. Clouteau. Synthetic ground motions in heterogeneous geolo- gies: the HEMEW-3D dataset for scientific machine learning. Earth System Science Data, 2024. https: //doi.org/10.5194/essd-16-3949-2024
2. A. Hatamizadeh, V. Nath, Y. Tang, D. Yang, H. R. Roth, D. Xu. Swin UNETR: Swin Transformers for Se- mantic Segmentation of Brain Tumors in MRI Images. arXiv preprint arXiv:2201.01266, 2022. https: //arxiv.org/abs/2201.01266
F. Lehmann, F. Gatti, D. Clouteau. Multiple-Input Fourier Neural Operator (MIFNO) for source-dependent 3D elastodynamics. Journal of Computational Physics, 2025. https://doi.org/10.1016/j.jcp.2025. 113813

