# Cardioalerta Vital Signs

Prototype for contactless infant vital-sign estimation from RGB video.

The project integrates two existing research implementations:

* **rPPG / PhysNet-based processing** for Heart Rate (HR) and peripheral oxygen saturation (SpO₂) estimation.
* **AIR-400** for Respiratory Rate (RR) estimation using video-based motion analysis and optical flow.

The objective of this repository is to reproduce, configure, test, and integrate these methods into a unified prototype for infant physiological monitoring.

> **Academic prototype:** This system is not intended to replace certified clinical monitoring equipment or professional medical assessment.

---

## Estimated Parameters

* Heart Rate — HR / FC
* Peripheral Oxygen Saturation — SpO₂
* Respiratory Rate — RR / FR

---

## System Architecture

```text
                     RGB VIDEO
                         │
                         ▼
                Video Quality Check
                         │
              ┌──────────┴──────────┐
              │                     │
              ▼                     ▼
       rPPG / PhysNet            AIR-400
        HR + SpO₂                   RR
              │                     │
              └──────────┬──────────┘
                         ▼
                 Vital-sign outputs
```

---

## Repository Structure

```text
cardioalerta-vital-signs/
│
├── rppg-test-main/
│   └── Heart Rate + SpO₂
│
├── AIR-400-main/
│   └── Respiratory Rate
│
├── docs/
│   ├── architecture.md
│   ├── datasets.md
│   └── references.md
│
├── README.md
├── .gitignore
└── THIRD_PARTY.md
```

---

# Software Environment

The prototype uses **two separate Conda environments** because AIR-400 and the rPPG/PhysNet implementation require different Python and dependency versions.

The tested platform is:

* Ubuntu running under WSL2
* Miniconda / Conda

Do not install all dependencies in a single environment.

---

## Respiratory Rate — AIR-400

### Environment

* Conda environment: `respenv`
* Python: `3.9.18`
* Platform: Ubuntu / WSL2

Activate the environment:

```bash
conda activate respenv
```

Navigate to the AIR-400 module:

```bash
cd AIR-400-main
```

Run the respiratory-rate inference:

```bash
bash run_infer.sh
```

AIR-400 contains the module-specific configuration, model requirements, ROI processing, and optical-flow-based respiratory analysis.

For additional information, see:

```text
AIR-400-main/README.md
```

---

## Heart Rate and SpO₂ — rPPG / PhysNet

### Environment

* Conda environment: `rppg-toolbox`
* Python: `3.8.20`
* Platform: Ubuntu / WSL2

Activate the environment:

```bash
conda activate rppg-toolbox
```

Navigate to the rPPG module:

```bash
cd rppg-test-main
```

Then execute the corresponding inference or testing script included in the module.

For module-specific dependencies and execution details, refer to the documentation contained in:

```text
rppg-test-main/
```

---

## Environment Separation

The two modules must be executed independently:

```text
respenv
└── AIR-400
    └── Respiratory Rate

rppg-toolbox
└── rPPG / PhysNet
    ├── Heart Rate
    └── SpO₂
```

The Conda `base` environment is not intended for running the prototype.

---

# Input Requirements

The prototype processes RGB video files.

Recommended format:

```text
.mp4
```

The acquisition should provide:

* visible infant face for HR and SpO₂ estimation;
* visible thoracic or abdominal regions for RR estimation;
* adequate and relatively stable illumination;
* limited motion;
* sufficient video duration;
* stable camera position.

---

# Video Quality Considerations

Video-based physiological estimation is sensitive to acquisition conditions.

Potential causes of unreliable estimation include:

* strong infant movement;
* crying;
* coughing;
* face occlusion;
* thoracoabdominal occlusion;
* insufficient illumination;
* unstable illumination;
* camera exposure changes;
* motion blur;
* strong video compression.

Technical-quality checks may be used to identify unsuitable video segments before physiological estimation.

When acquisition conditions are inadequate, the video should be repeated or replaced before interpreting the estimated vital signs.

---

# Datasets

## Used or available during prototype development

* **AIR-400** — respiratory-rate estimation.
* **UBFC-rPPG** — adult rPPG testing where applicable.

## Identified for future neonatal validation

* **NBHR**
* **VideoPulse**

NBHR and VideoPulse were identified as highly relevant neonatal datasets for future validation of HR and SpO₂ estimation.

Their authors were contacted to request research access. However, these datasets were **not used to train, test, or validate the current prototype**.

See:

```text
docs/datasets.md
```

for additional information.

---

# Scientific Basis

## Heart Rate

Heart-rate estimation is based on **remote photoplethysmography (rPPG)**.

rPPG analyzes subtle temporal variations in reflected RGB light produced by pulsatile changes in peripheral blood volume.

The periodic component of these optical variations can be used to estimate cardiac pulse rate.

---

## SpO₂

SpO₂ estimation uses a video-based machine-learning approach associated with **PhysNet and three-dimensional convolutional neural networks (3D-CNNs)**.

These models analyze spatial and temporal information contained in consecutive facial RGB video frames.

During supervised model development, video information is associated with reference physiological measurements, allowing the neural network to learn patterns related to oxygen saturation.

---

## Respiratory Rate

Respiratory-rate estimation is based primarily on **video motion analysis** rather than photoplethysmography.

AIR-400 processes motion information from infant video, including **optical-flow representations**, to characterize periodic respiratory movements and estimate respiratory rate in breaths per minute.

---

# Third-Party Software

This repository integrates research implementations developed by third parties.

The original core algorithms are **not claimed as developments of this project**.

The work performed in this prototype focuses on:

* software environment configuration;
* execution and reproduction of existing implementations;
* testing;
* integration of HR, SpO₂, and RR processing pipelines;
* evaluation of their applicability within a unified infant-monitoring prototype.

See:

```text
THIRD_PARTY.md
```

for attribution and upstream repository information.

---

# Clinical Disclaimer

This software is an academic and experimental prototype.

It has not been clinically validated or certified as a medical device.

It must not be used as a replacement for:

* pulse oximetry;
* ECG monitoring;
* respiratory monitoring;
* clinical examination;
* professional medical decision-making.

Results generated by the prototype should be interpreted only within the context of research, technical testing, and prototype evaluation.

---

# Documentation

Additional technical documentation is available in:

```text
docs/architecture.md
docs/datasets.md
docs/references.md
```
=======
# neonatal-video-algorithm-for-HR-SpO2-and-RR
Video-based vital sign estimation using rPPG and machine learning for heart rate and SpO₂, integrating the NeoCare repository with AIR-400 optical-flow analysis for respiratory rate estimation.
