# Arijit Singh RVC v2 Production Model (M4 Silicon Architecture Optimization)

A high-fidelity, production-grade Retrieval-based Voice Conversion (RVC) model trained on an optimized dataset of **Arijit Singh**. This repository archives the complete 17 GB standalone weights, intermediate training checkpoints, complete feature index maps, and TensorBoard logs compiled directly on Apple Silicon architecture.

---

## 📊 1. Core Model Specifications & Architecture

| Attribute | Specification Configuration | Architectural Impact |
| :--- | :--- | :--- |
| **RVC Core Engine** | Version 2 (v2 Framework) | Enhanced high-frequency resonance modeling over v1 |
| **Target Sample Rate** | 48,000 Hz (48 kHz Pristine) | Broadcast-ready acoustic range with zero downsampling |
| **Feature Extraction** | ContentVec (256-Dimension) | Robust linguistic representation, fully decoupling speaker identity |
| **Pitch Tracking Algorithm** | RMVPE Native | Unmatched accuracy tracking complex vocal slides (*Meend*) |
| **Dataset Total Density** | 31 Minutes, 16 Seconds | Pure vocal source data completely cleared of background instrumentation |

---

## 🛠️ 2. Comprehensive Data Preprocessing Pipeline

To capture the emotional nuances, microtonal inflections, and breath dynamics characteristic of Arijit Singh's vocal delivery, the source data underwent a meticulous multi-stage Digital Signal Processing (DSP) pipeline before entering the model:

### Phase 1: Vocal Isolation & Demixing
* **Dewatering/De-reverb:** Advanced phase-cancellation and deep-learning separation algorithms were deployed to isolate dry vocal stems from modern Bollywood orchestral arrangement mixdowns.
* **Sibilance & Noise Attenuation:** High-pass filtering at 60 Hz eliminated sub-bass room rumble, followed by surgical dynamic equalization targeting harsh sibilance zones (4 kHz - 7 kHz) to protect the model from generating electronic lisp artifacts.

### Phase 2: Dynamic Slicing & Normalization
* **Audio Chunk Segmentation:** A custom Python script sliced long vocal tracks into uniform segments based on silent breath thresholds. 
  * *Minimum Slice Length:* 4.0 seconds
  * *Maximum Slice Length:* 12.0 seconds
  * *Silence Threshold:* -60 dB (ensuring zero mid-syllable truncation).
* **Amplitude Matching:** Every individual audio slice was peak-normalized to -1.0 dBFS to guarantee absolute gain consistency across legacy acoustic sets and modern studio masters.

---

## 📈 3. End-to-End Training & Convergence Logs

Training was executed locally using native hardware acceleration optimized for local memory layouts.

```text
Dataset Manifest Parsing ──> F0 Pitch Estimation (RMVPE) ──> HuBERT Semantic Mapping
                                                                    │
   ┌────────────────────────────────────────────────────────────────┘
   ▼
Multi-Epoch Training Loop ──> Forward/Backward Propagation ──> Target Loss Convergence
```

### Computational Parameters & Milestones
* **Total Training Epochs:** 250 Epochs
* **Total Optimization Steps:** 18,750 Steps
* **Batch Density:** Evaluated at maximum capacity relative to hardware architecture memory layouts, eliminating training noise.
* **Loss Dynamics:** Stabilized cleanly around Epoch 216. 
  * **Lowest Achieved Generator Total Loss:** `28.603` (Logged at Step 16,163)
  * **Discriminator Classification Error:** Consistently balanced, forcing the generator to adapt to real spectral qualities rather than over-smoothing the audio.

---

## 🗂️ 4. Full Repository Architecture

This backup contains the raw history tree and runtime artifacts of the model's complete training evolution.

```text
.
├── Arijit_Singh_v2_M4_250e_18750s.pth   # Master Production Weights (Crown Jewel - 48kHz)
├── Arijit_Singh_v2_M4.index             # 18,750-step Feature Lookup Index Map (232.6 MB)
├── config.json                          # Hyperparameter configuration metrics
├── model_info.json                      # Training duration metadata properties
├── filelist.txt                         # Structural parsing dataset manifest
├── f0/                                  # Extracted pitch tracks (.f0 files)
├── f0_voiced/                           # Voiced-only pitch calculation matrix arrays
├── extracted/                           # HuBERT semantic hidden layer feature vectors
├── sliced_audios/                       # Formatted dataset split audio segments
├── sliced_audios_16k/                   # 16 kHz sample down-conversions for target feature lookups
└── eval/                                # Complete TensorBoard training visualization event charts
```

---

## 🎛️ 5. Production Inference Guidelines

To reproduce a studio-grade representation that preserves complex vocal techniques, apply the following parameter stack inside your inference GUI or pipeline (e.g., Applio or custom script configurations):

```text
[Input Vocal Audio]
       │
       ▼
   [RMVPE Engine] ───> Tracks pitch transitions down to the millisecond
       │
       ▼
[Index Rate: 0.70] ───> Blends original accents with 70% target Arijit timbre
       │
       ▼
[Voiceless Protect: 0.33] ──> Safely passes natural breath textures
       │
       ▼
 [Output Master]
```

### Setting Recommendations Matrix

* **Pitch Extraction:** Always select **RMVPE**. It successfully captures smooth gliding notes without introducing robotic stepping artifacts.
* **Index Rate (`0.70`):** Provides the ideal ratio. It locks down Arijit's definitive tonal character while retaining enough of the source singer's original energy and performance inflections.
* **Protect Voiceless Consonants (`0.33`):** Protects unvoiced breath segments and hard consonants (`t`, `p`, `k`), eliminating digital whistling.

---

## 🛡️ License & Usage Note
This repository is established as a private archival backup for educational research into deep-learning neural audio synthesis and digital voice preservation. Ensure absolute legal compliance regarding synthetic voice deployment and intellectual property laws in your jurisdiction.
