# Predictive Maintenance with LSTM

Forecast the **next values of key health signals** for an industrial electric motor using a Long Short-Term Memory (LSTM) recurrent neural network—so maintenance can be scheduled before failures cause downtime.

> This project uses real data from an ABB motor smart sensor deployed on a factory fan. Time-series signals include overall vibration and peak-to-peak vibrations along multiple axes, among others. :contentReference[oaicite:0]{index=0}

---

## Table of Contents
- [Project Overview](#project-overview)
- [Repository Structure](#repository-structure)
- [Data](#data)
- [Method](#method)
- [Results](#results)
- [Quickstart](#quickstart)
- [Reproduce the Notebook](#reproduce-the-notebook)
- [Roadmap](#roadmap)
- [Citations & Acknowledgements](#citations--acknowledgements)
- [License](#license)

---

## Project Overview

Industrial motors fail in patterns that are visible in **sequential sensor data**. LSTM networks are well-suited to time series because they preserve temporal context.

**Goal:** given recent windows of sensor readings, predict the **next step** (and short horizon) values for the most informative signals, enabling early warnings for abnormal vibration growth that precedes failure. Feature selection relies on correlation analysis to reduce noise and dimensionality. :contentReference[oaicite:1]{index=1}

---

## Repository Structure

