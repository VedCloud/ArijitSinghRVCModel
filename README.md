# Arijit Singh RVC v2 Model (M4 Optimized)

A high-fidelity, production-grade Retrieval-based Voice Conversion (RVC) model trained on an optimized dataset of **Arijit Singh**. This repository contains the standalone weights, intermediate training checkpoints, complete feature index maps, and TensorBoard logs compiled directly on Apple Silicon architecture.

## 📊 Model Specifications & Training Metrics

* **RVC Architecture Version:** v2
* **Target Sample Rate:** 48 kHz
* **Total Training Epochs:** 250
* **Total Optimization Steps:** 18,750 steps
* **Pitch Extraction Native Settings:** RMVPE (Robust Minimum Velocity Pitch Estimation)
* **Dataset Density:** 31 minutes and 16 seconds of pristine, modern studio-isolated vocal stems.
* **Optimal Dataset Cleanup:** Preprocessed via a custom Python script for uniform splitting and absolute acoustic consistency.
* **Lowest Achieved Generator Loss:** `28.603` (Stabilized at Epoch 216, Step 16163)

---

## 🗂️ Repository Structure

```text
├── Arijit_Singh_v2_M4_250e_18750s.pth   # Master Production Weights (Crown Jewel)
├── Arijit_Singh_v2_M4.index             # Full 18,750-step Feature Lookup Index Map
├── config.json                           # Hyperparameter configurations
├── model_info.json                      # Model metadata properties
├── filelist.txt                         # Dataset structural manifest
├── [Arijit_Singh_v2_M4_*0e_*.pth]       # Intermediate milestone checkpoints (20e - 240e)
├── [G_*.pth / D_*.pth]                  # Generator and Discriminator snapshots for resume compatibility
├── eval/                                # TensorBoard training visualization logs
└── extracted/                           # F0 and feature extraction artifacts
