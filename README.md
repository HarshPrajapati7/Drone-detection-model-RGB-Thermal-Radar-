# Trinetra Detection Engine (RGB + Thermal + Radar)

<div align="center">
  <h3><strong>Made by Team Star Busters</strong></h3>
  <p><em>Multimodal Perception Pipeline for SIH26247</em></p>
</div>

---

## 📌 Overview
This repository contains the core Machine Learning and inference notebooks powering the **Trinetra** threat simulation platform. Instead of relying on simulated or mock AI, Trinetra uses live models trained on real UAV datasets to provide trainees with authentic detection telemetry.

## 🧠 Model Architecture

Our pipeline utilizes **NVIDIA TAO Toolkit** with an **RT-DETR** architecture, backed by a **C-RADIOv3-L** backbone. 
This approach was chosen specifically for its ability to handle high-velocity small-target tracking in cluttered environments while maintaining real-time inference speeds suitable for a live simulation dashboard.

### Sensor Fusion
The pipeline is designed to fuse data across the spectrum:
1.  **RGB (Daylight)**: High resolution visual tracking.
2.  **Thermal / LWIR**: Crucial for nighttime detection or haze/fog scenarios where visual fidelity drops.
3.  **Radar (FMCW)**: Used to filter out false positives and confirm velocity vectors in extreme weather.

## 📂 Repository Contents

*   `SIH26247_STEP1_LOCAL_NVIDIA_RTDETR_CRADIOv3L_v15.ipynb`: The primary local training and evaluation pipeline for the RT-DETR model.
*   `SIH26247_Inference_Test.ipynb`: Contains the logic for running inference on live frames and generating the bounding-box telemetry sent to the UI.
*   `part_2_colab_has2,3,4.ipynb` & `SIH26247_STEP1_part2_v2.ipynb`: Extended training workflows utilizing cloud compute for larger batch processing and hyperparameter tuning.

## 🏃‍♂️ Execution

The notebooks are designed to be run in a Jupyter environment with a compatible NVIDIA GPU (TensorRT optimization recommended for deployment).

```bash
pip install -r requirements.txt
jupyter notebook
```

---
*Developed with ❤️ by Team Star Busters for Smart India Hackathon.*
