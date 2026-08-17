\# System Architecture



\## Overview



This project integrates existing video-based physiological monitoring methods into a unified prototype for infant vital-sign estimation.



The prototype estimates:



\* Heart Rate (HR)

\* Peripheral Oxygen Saturation (SpO₂)

\* Respiratory Rate (RR)



The project focuses on the configuration, execution, testing, and integration of existing research implementations rather than the development of the core estimation algorithms.



\## General Pipeline



```text

&#x20;                    RGB VIDEO

&#x20;                        │

&#x20;                        ▼

&#x20;               Video Quality Check

&#x20;                        │

&#x20;             ┌──────────┴──────────┐

&#x20;             │                           │

&#x20;             ▼                           ▼

&#x20;      rPPG / PhysNet            	AIR-400

&#x20;       HR + SpO₂                         RR

&#x20;             │                		      │

&#x20;             └──────────┬──────────┘

&#x20;                        ▼

&#x20;                 Vital-sign output

```



\## Heart Rate and SpO₂



Heart rate and peripheral oxygen saturation are processed using the rPPG-based implementation contained in the `rppg-test-main` module.



Remote photoplethysmography (rPPG) detects subtle temporal variations in the RGB intensity of exposed skin caused by pulsatile changes in peripheral blood volume.



For heart-rate estimation, the temporal pulse-related information contained in facial video is processed to recover cardiac activity.



For SpO₂ estimation, the implementation uses a video-based machine-learning approach based on PhysNet and three-dimensional convolutional neural networks (3D-CNNs). These networks analyze spatial and temporal information from consecutive facial video frames.



The model is based on supervised learning, where video recordings are associated with synchronized reference physiological measurements during training. After training, the model estimates physiological parameters from new video sequences.



\## Respiratory Rate



Respiratory-rate estimation is performed using the `AIR-400-main` module.



Unlike HR and SpO₂ estimation, respiratory-rate estimation is primarily based on motion analysis rather than photoplethysmography.



Respiration produces periodic movements in regions such as the thorax and abdomen. AIR-400 uses computer-vision techniques, including optical-flow information, to characterize motion between consecutive video frames and estimate respiratory activity.



Conceptually:



```text

Infant RGB video

&#x20;     │

&#x20;     ▼

Region-of-interest processing

&#x20;     │

&#x20;     ▼

Optical-flow / motion representation

&#x20;     │

&#x20;     ▼

Spatiotemporal respiratory analysis

&#x20;     │

&#x20;     ▼

Respiratory Rate

```



\## Module Distribution



```text

project-root/

│

├── rppg-test-main/

│   └── Heart Rate + SpO₂

│

├── AIR-400-main/

│   └── Respiratory Rate

│

└── docs/

&#x20;   └── Technical documentation

```



\## Integration Scope



The prototype integrates the outputs of both processing pipelines into a common vital-sign monitoring workflow.



The core algorithms originate from external research repositories. No substantial modifications to the original core algorithms are claimed in this project.



The main contribution of this implementation is the reproduction and integration of the different video-processing approaches into a unified prototype for infant vital-sign monitoring.



\## Important Limitation



The system is an academic and experimental prototype.



It must not be considered a replacement for certified clinical monitoring equipment or used independently for medical diagnosis or treatment decisions.



