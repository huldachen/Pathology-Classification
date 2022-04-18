# Pathology-Classification
Whole-slide CNN Training Pipeline. This is a practice project from published papers: "An annotation-free whole-slide training approach to pathological classification of lung cancer types by deep learning", including model training, inference, visualization, and statistics calculation, etc.

# License
Copyright (C) 2021 aetherAI Co., Ltd. All rights reserved. Licensed under the CC BY-NC-SA 4.0 license (https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode).

# Packages
The codes are tested on the environment with Ubuntu 18.04 / CentOS 7.5, Python 3.7.3, cuda 10.0, cudnn 7.6 and Open MPI 4.0.1. Some Python packages should be installed before running the scripts, including

Tensorflow v1.x (tensorflow-gpu==1.15.3)

Horovod (horovod==0.19.0)

MPI for Python (mpi4py==3.0.3)

OpenSlide 3.4.1 (https://github.com/openslide/openslide/releases/tag/v3.4.1)

OpenSlide Python (openslide-python=1.1.1)

Tensorflow Huge Model Support (our package)

(optional) R 4.0.2 (https://www.r-project.org/)

Refer to requirements.txt for the full list. The installation of these packages should take few minutes.


# Steps
1. Define Datasets
2. Set Up Training Configurations
3. Train a Model
4. (Optional) Post-train Patch Aggregation Model for MIL
5. Evaluate the Model
To evaluate the model or optionally generate prediction heatmap, call
```
[mpirun ...] python -m whole_slide_cnn.test --config YOUR_TRAIN_CONFIG.YAML
```

This command generate a JSON file in the result directory named `test_result.json` by default. The file contains the model predictions for each testing slide.





Data Availability
The slide data from TMUH, WFH and SHH are not publicly available due to patient privacy constraints, but are available uponon reasonable request from the corresponding author Chao-Yuan Yeh or Cheng-Yu Chen. The slide data supporting the cross-site generalization capability in this study are obtained from TCGA via the Genomic Data Commons Data Portal (https://gdc.cancer.gov).

A dataset consists of several slides from TCGA-LUAD and TCGA-LUSC is suitable for testing our pipeline in small scale, with some proper modifications of configuration files described above.