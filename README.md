# Patch-Based Landscape Change Classification using UNet

This project uses a custom UNet convolutional neural network with **three output branches** to classify landscape changes derived from binary vegetation maps at two time points (`t1` and `t2`). The model distinguishes between stability, vegetation loss, and vegetation gain, and refines these into **10 distinct classes**.

## 🔍 Objective

To identify and classify spatial patterns of vegetation change using only two input rasters:
- `t1`: binary map at time 1 (1 = vegetated, 0 = non-vegetated)
- `t2`: binary map at time 2

The model predicts a map where each pixel belongs to one of the 10 refined classes, including:
- Stable vegetation (0)
- Stable non-vegetated (1)
- Four types of vegetation loss (22–25)
- Four types of vegetation gain (36–39)

## 🧠 Model Architecture

The network is based on a standard **U-Net** encoder–decoder structure, with **three separate output heads**:
- **Stable**: classifies between 0 and 1
- **Loss**: classifies between 22 to 25
- **Gain**: classifies between 36 to 39

Each head is trained using a filtered version of the input according to transition type derived from `t1` and `t2`.

## 📂 Repository Structure

