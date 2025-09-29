This project predicts the **next values of motor health/operation signals** from time-series sensor data using a Long Short-Term Memory (LSTM) network.

## What’s in this repo
- **Data/** – Excel files used in analysis (health + operational parameters).
- **Notebooks/** – Jupyter/Colab notebook(s) to clean data, build the model, and make predictions.
- **Report/** – Full internship report (PDF) documenting data, model, and results.
- **Visualizations_png/** – Plots exported from the notebook.
- **README.md** – This file.

## Data (source & signals)
- Data comes from an **ABB Smart Sensor** attached to an electric motor (fan). The platform provides ~90 days of measurements.  
- Signals include **health** (overall vibration, bearing condition, skin temperature) and **operational** (vibration axial/tangential/radial, motor supply frequency, output power, peak-to-peak for three axes, etc.).  
- The workflow downloads two Excel files (health + operational), then **merges** them into one dataset for modeling.

## Method (high level)
1. **Cleaning & smoothing**: remove irrelevant entries, handle missing data, and filter outliers; visualize each signal.
2. **Correlation & dimensionality reduction**: keep variables with **Pearson correlation > 60%** to overall vibration.
3. **Model**: **LSTM RNN** (bidirectional, many-to-many) with **ReLU** activations and **Adam** optimizer; trained with **2 LSTM layers** and **~400 epochs**.
4. **Sequence setup**: use a **10-step input window** to predict subsequent values.
5. **Train/test split**: data is split into training and testing sets and evaluated with plots.

## Results (summary)
- The notebook shows **target vs. predicted** overlays for key signals (e.g., overall vibration and peak-to-peak axes).  
- An accuracy check (after rounding continuous values) is included; results are noted as **limited by small data size**.

## How to use
1. Open the notebook in **Notebooks/** (Colab or Jupyter).  
2. Place the Excel files in **Data/** and run cells to reproduce cleaning, modeling, and predictions.  
3. See **Report/** for full details, figures, and rationale.
