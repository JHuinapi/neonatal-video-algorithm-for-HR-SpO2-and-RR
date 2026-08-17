# Datasets and Data Sources

This project uses public or locally available data only where access was obtained and permitted.

Several neonatal datasets were also identified as scientifically relevant for future validation. Where access was not available, the authors were contacted and the datasets were not incorporated into the current prototype.

\## AIR-400



\*\*Application:\*\* Infant respiratory-rate estimation.



AIR-400 is a video dataset developed for video-based infant respiration estimation.



It extends previous infant respiration datasets and contains 400 annotated infant video recordings.



The AIR-400 repository provides the implementation used in this project for respiratory-rate inference.



\### Use in this project



AIR-400 is associated with the `AIR-400-main` module and is used as the research basis for respiratory-rate estimation.



The respiratory pipeline analyzes movement information, including optical-flow representations, to identify respiratory activity from infant videos.



\### Local data



Dataset files and infant videos are intentionally excluded from this GitHub repository.



\---



\## NBHR



\*\*Purpose in this project:\*\* Reference neonatal dataset considered for future validation.



NBHR is a neonatal rPPG dataset developed for non-contact physiological monitoring and includes synchronized facial video and physiological reference signals such as PPG, heart rate, and SpO₂.



The dataset was identified as highly relevant for validating neonatal heart-rate and SpO₂ estimation under more realistic conditions.



Access to the dataset was not available during the development of the current prototype. The authors were contacted to request access for research and validation purposes.



Therefore, NBHR data were \*\*not used to train, test, or validate the current prototype\*\*.



The dataset is referenced only as a scientific and methodological resource.





\## VideoPulse



\## VideoPulse



\*\*Purpose in this project:\*\* Scientific reference and potential future validation dataset.



VideoPulse is a neonatal dataset and research system for contact-free heart-rate and SpO₂ estimation from facial RGB video.



The work was used as a scientific reference for understanding neonatal rPPG, PhysNet-based processing, and video-based SpO₂ estimation.



The authors were contacted with the objective of obtaining access to the dataset for future testing and validation of the prototype.



VideoPulse data were \*\*not incorporated into the current implementation\*\*, and no training or validation of the prototype was performed using this dataset.



Its inclusion in this documentation is therefore limited to scientific background and future validation planning.

\---



\## UBFC-rPPG



\*\*Application:\*\* Adult rPPG testing and experimentation.



UBFC-rPPG is an adult facial-video dataset frequently used for remote photoplethysmography research.



The second UBFC-rPPG dataset contains 42 shared recordings and includes synchronized pulse-related reference measurements.



It may be used for preliminary testing of rPPG pipelines before neonatal-specific evaluation.



\---



\## Dataset Policy



The following are intentionally excluded from this repository:



```text

data/

datasets/

videos/

\\\*.mp4

\\\*.avi

\\\*.mov

```



This prevents:



\* redistribution of third-party datasets;

\* accidental publication of participant videos;

\* unnecessary repository size;

\* potential privacy issues involving biomedical video data.



Users wishing to reproduce the original experiments should obtain each dataset from its official source and comply with the corresponding access conditions, licenses, and ethical requirements.

