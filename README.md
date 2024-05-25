# Deepfake Detection

**Project by: Emirhan Bilgiç**

**Date: May 2024**

---

## Table of Contents
- [Project Overview](#project-overview)
- [Problem Definition](#problem-definition)
- [Datasets](#datasets)
- [Methods](#methods)
- [Results](#results)
- [Future Work](#future-work)
- [References](#references)
- [Acknowledgements](#acknowledgements)
- [How to Run](#how-to-run)

---

## Project Overview

This repository contains the final project for the CMPE593 course, focused on deepfake detection using various machine learning and deep learning techniques. The goal is to compare different methods for detecting deepfakes and evaluate their effectiveness across different datasets.

## Problem Definition

Deepfake pictures are hyper-realistic digital manipulations of audiovisual content that can convincingly mimic real people saying or doing things they never did. This poses significant challenges in the realms of misinformation, privacy, and security.

## Datasets

The datasets used in this project for the creation, detection, training, and testing phases of deepfakes include:

| Dataset           | Release Date | Real/Fake  | Source   |
|-------------------|--------------|------------|----------|
| FaceForensics++   | 2019.0       | 1000/4000  | YouTube  |
| DFDC              | 2019.10      | 23654/104500 | Actors  |
| Celeb-DF          | 2019.11      | 890/5639   | YouTube  |
| DeeperForensics   | 2020.1       | 10000/50000 | Actors  |

## Methods

1. **MesoNet**
   - A CNN architecture designed for deepfake facial manipulation detection by capturing "mesoscopic" features within images.

2. **MesoInception**
   - Enhances the Meso-4 architecture by integrating inception modules, enabling the network to capture multi-scale features through parallel convolutions with various kernel sizes.

3. **Xception**
   - Built exclusively on depthwise separable convolution layers with residual connections, adaptable for various applications including deepfake detection.

4. **Face X-Ray (CVPR 2020)**
   - Detects face forgeries by assuming the existence of a blending step, effective against a wide range of manipulation techniques.

5. **On Improving Cross-dataset Generalization of Deepfake Detectors (CVPR 2022)**
   - Uses a hybrid approach combining supervised learning and reinforcement learning to enhance cross-dataset generalization.

6. **Implicit Identity Leakage (CVPR 2023)**
   - Addresses the reliance on global identity features in deepfake detection, proposing new methods to avoid identity leakage.

7. **Emirhan’s Method: BLIP**
   - A VLP (Vision-Language Pre-training) framework tested for deepfake detection by asking questions about image manipulation.

## Results

The performance of different methods was evaluated based on their classification scores (AUC) on the FF++ and Celeb-DF datasets:

| Network              | FF++ Classification Score (AUC) | Celeb-DF Classification Score (AUC) |
|----------------------|---------------------------------|------------------------------------|
| MesoNet (4)          | 0.847                           | 0.548                              |
| MesoInception (4)    | 0.830                           | 0.536                              |
| Xception             | 0.955                           | 0.655                              |
| Face X-Ray (HRNet)   | 0.9915                          | 0.8058                             |
| RL-guided-network    | 0.994                           | 0.669                              |
| ID-Unaware Network   | 0.9979                          | 0.9388                             |
| Emirhan’s Method: BLIP | 0.60 (Accuracy)                 | N/A                                |

## Future Work

The robustness of deepfake detectors against adversarial attacks should be investigated. For example, methods like StatAttack that minimize statistical differences between real and fake images can effectively evade many existing detection systems.

## References

1. Afchar, D., Nozick, V., Yamagishi, J., & Echizen, I. (2018, December). Mesonet: a compact facial video forgery detection network. In 2018 IEEE international workshop on information forensics and security (WIFS) (pp. 1-7). IEEE.
2. Pan, Z., Ren, Y., & Zhang, X. (2021). Low-complexity fake face detection based on forensic similarity. Multimedia Systems, 27, 1-9.
3. Yu, P., Xia, Z., Fei, J., & Lu, Y. (2021). A survey on deepfake video detection. Iet Biometrics, 10(6), 607-624.
4. Li, L., Bao, J., Zhang, T., Yang, H., Chen, D., Wen, F., & Guo, B. (2020). Face x-ray for more general face forgery detection. In Proceedings of the IEEE/CVF conference on computer vision and pattern recognition (pp. 5001-5010).
5. Nadimpalli, A. V., & Rattani, A. (2022). On improving cross-dataset generalization of deepfake detectors. In Proceedings of the IEEE/CVF conference on computer vision and pattern recognition (pp. 91-99).
6. Dong, S., Wang, J., Ji, R., Liang, J., Fan, H., & Ge, Z. (2023). Implicit identity leakage: The stumbling block to improving deepfake detection generalization. In Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (pp. 3994-4004).
7. Hou, Y., Guo, Q., Huang, Y., Xie, X., Ma, L., & Zhao, J. (2023). Evading deepfake detectors via adversarial statistical consistency. In Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (pp. 12271-12280).
8. Li, J., Li, D., Xiong, C., & Hoi, S. (2022, June). Blip: Bootstrapping language-image pre-training for unified vision-language understanding and generation. In International conference on machine learning (pp. 12888-12900). PMLR.


