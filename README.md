# Audio Autoencoder on Mel Spectrograms

A self-supervised deep learning project exploring compact audio representations using a convolutional autoencoder trained on log-mel spectrograms.

The notebook implements the complete pipeline:
- audio preprocessing,
- waveform → log-mel spectrogram conversion,
- convolutional autoencoder training,
- spectrogram reconstruction,
- approximate waveform reconstruction from spectrograms.

Everything is contained inside a single Jupyter notebook.

---

## Overview

The goal of this project is to learn compact latent representations of audio signals without labels by training an autoencoder to reconstruct mel spectrograms.

Instead of working directly on raw waveforms, the model operates on log-mel spectrograms, which provide a structured and convolution-friendly representation of audio signals.

The notebook also includes:
- spectrogram visualization,
- reconstruction comparison,
- absolute reconstruction error maps,
- approximate waveform reconstruction using `InverseMelScale` and `GriffinLim`.

---

## Model

The model is a 2D convolutional autoencoder composed of:
- convolution + pooling encoder blocks,
- a compact latent bottleneck,
- transposed convolution decoder blocks.

Training uses a reconstruction loss combining:
- MSE loss,
- L1 loss.

---

## Dataset

The project uses the TinySOL dataset:
- monophonic isolated instrument recordings,
- resampled to 16 kHz,
- normalized and converted into fixed-length samples.

---


## Running the notebook

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

### 2. Open the notebook

Launch Jupyter Notebook or Jupyter Lab and open:

```text
autoencoder_specto.ipynb
```

### 3. Run the notebook cells

The notebook contains:
- dependency installation cells,
- dataset preparation,
- preprocessing,
- training,
- inference and visualization.

Simply execute the cells sequentially from top to bottom.

---

## Notes

- The notebook is fully self-contained.
- No additional Python scripts are required.
- Some cells generate figures and reconstructed audio samples used in the portfolio article.
- Audio reconstruction quality is limited by the absence of phase information in mel spectrograms.

---
