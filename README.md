This project predicts the **next values of motor health/operation signals** from time-series sensor data using a Long Short-Term Memory (LSTM) network.

## Data (source & signals)
- Data comes from an **ABB Smart Sensor** attached to an electric motor (fan). The platform provides ~90 days of measurements.  
- Signals include **health** (overall vibration, bearing condition, skin temperature) and **operational** (vibration axial/tangential/radial, motor supply frequency, output power, peak-to-peak for three axes, etc.).  
- The workflow downloads two Excel files (health + operational), then **merges** them into one dataset for modeling.

## Method
1. **Cleaning & smoothing**: remove irrelevant entries, handle missing data, and filter outliers; visualize each signal.
2. **Correlation & dimensionality reduction**: keep variables with **Pearson correlation > 60%** to overall vibration.
3. **Model**: **LSTM RNN** (bidirectional, many-to-many) with **ReLU** activations and **Adam** optimizer; trained with **2 LSTM layers** and **~400 epochs**.
4. **Sequence setup**: use a **10-step input window** to predict subsequent values.
5. **Train/test split**: data is split into training and testing sets and evaluated with plots.

## Results (summary)
- The notebook shows **target vs. predicted** overlays for key signals (e.g., overall vibration and peak-to-peak axes).  
- An accuracy check (after rounding continuous values) is included; results are noted as **limited by small data size**.

## See **Report/** for full details, figures, and rationale.
