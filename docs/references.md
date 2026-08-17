\# Scientific References



\## Heart Rate and Remote Photoplethysmography



\### Camera-based physiological measurement



D. McDuff, “Camera Measurement of Physiological Vital Signs,” \*ACM Computing Surveys\*, vol. 55, no. 9, Art. no. 176, 2023.



This review provides the theoretical basis for camera-based physiological sensing, including remote photoplethysmography, cardiac measurements, blood oxygen saturation, motion artifacts, and illumination limitations.



\---



\### Infant rPPG feasibility



M. E. Wieler, T. G. Murphy, M. Blecherman, H. Mehta, and G. J. Bender, “Infant heart-rate measurement and oxygen desaturation detection with a digital video camera using imaging photoplethysmography,” \*Journal of Perinatology\*, 2021.



This study evaluated imaging photoplethysmography in newborn infants using facial video, particularly a forehead region of interest, for heart-rate measurement and detection of oxygen desaturation events.



\---



\## Neonatal Dataset and Heart Rate



B. Huang \*et al.\*, “A neonatal dataset and benchmark for non-contact neonatal heart rate monitoring based on spatio-temporal neural networks,” \*Engineering Applications of Artificial Intelligence\*, vol. 106, Art. no. 104447, 2021.



DOI: `10.1016/j.engappai.2021.104447`



This work introduces the NBHR neonatal dataset and provides a benchmark for non-contact neonatal heart-rate estimation.



\---



\## Neonatal Heart Rate and SpO₂



D. Dewagiri, K. Anuradha, P. Liyanage, H. Kulatunga, P. Somarathne, U. S. K. P. M. Thanthrige, N. Lucas, A. Withana, and J. P. Kulasingham, “VideoPulse: Neonatal heart rate and peripheral capillary oxygen saturation (SpO₂) estimation from contact free video,” \*arXiv preprint arXiv:2602.23771\*, 2026.



VideoPulse applies a PhysNet-based 3D-CNN pipeline to neonatal facial videos for HR and SpO₂ estimation. The model processes short RGB video clips and learns spatiotemporal representations associated with physiological reference measurements.



\---



\## Respiratory Rate



\### AIR-400



L. Song, H. Bishnoi, S. K. R. Manne, S. Ostadabbas, B. J. Taylor, and M. Wan, “Overcoming Small Data Limitations in Video-Based Infant Respiration Estimation,” \*Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision (WACV)\*, 2026.



This work introduces AIR-400 and evaluates video-based infant respiratory-rate estimation using computer-vision and spatiotemporal approaches, including optical-flow information.



Original repository:



`https://github.com/michaelwwan/air-400`



\---



\## Additional Respiratory-Rate Reference



S. Ahani, N. Niknafs, P. M. Lavoie, L. Holsti, and G. A. Dumont, “Video-Based Respiratory Rate Estimation for Infants in the NICU,” \*IEEE Journal of Translational Engineering in Health and Medicine\*, vol. 12, pp. 684–696, 2024.



DOI: `10.1109/JTEHM.2024.3488523`



This study demonstrates an alternative video-based approach for neonatal respiratory-rate estimation using Eulerian Video Magnification and respiratory motion analysis. It is included as scientific background but is not the respiratory algorithm implemented in this prototype.



\---



\# Software and Repository References



\## AIR-400



Repository:



`https://github.com/michaelwwan/air-400`



Role in this project:



Respiratory-rate estimation.



The original implementation is used as the basis for the respiratory module. No substantial modifications to the core algorithm are claimed.



\---



\## NeoCare / rPPG implementation



Role in this project:



Heart-rate and SpO₂ estimation using video-based rPPG and machine-learning methods.



The implementation is used as an upstream research prototype. No substantial modifications to the core algorithm are claimed in this project.



At the time this documentation was prepared, no explicit software license had been identified in the upstream NeoCare repository. Users should verify the current upstream licensing terms before redistributing its source code.

