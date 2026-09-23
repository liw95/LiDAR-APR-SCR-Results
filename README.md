# LiDAR APR & SCR: Reproduced Results and Predictions

Reproduced results and per-frame predictions of 13 regression-based LiDAR localization methods, covering **absolute pose regression (APR)** and **scene coordinate regression (SCR)**, on **Oxford Radar RobotCar**, **QEOxford** and **NCLT**.

> ⚠️ This is an unofficial reproduction. All credit for the methods goes to their authors; please cite the original papers.

## Methods

### Absolute Pose Regression (APR)

- [2025 IROS] BEVDiffLoc: End-to-End LiDAR Global Localization in BEV View Based on Diffusion Model [[paper]](https://ieeexplore.ieee.org/abstract/document/11246131) [[code]](https://github.com/nubot-nudt/BEVDiffLoc)
- [2025 WACV] FlashMix: Fast Map-Free LiDAR Localization via Feature Mixing and Contrastive-Constrained Accelerated Training [[paper]](https://openaccess.thecvf.com/content/WACV2025/html/Goswami_FlashMix_Fast_Map-Free_LiDAR_Localization_via_Feature_Mixing_and_Contrastive-Constrained_WACV_2025_paper.html) [[code]](https://github.com/raktimgg/FlashMix)
- [2024 CVPR] DiffLoc: Diffusion Model for Outdoor LiDAR Localization [[paper]](https://openaccess.thecvf.com/content/CVPR2024/html/Li_DiffLoc_Diffusion_Model_for_Outdoor_LiDAR_Localization_CVPR_2024_paper.html) [[code]](https://github.com/liw95/DiffLoc)
- [2024 IEEE TITS] NIDALoc: Neurobiologically Inspired Deep LiDAR Localization [[paper]](https://ieeexplore.ieee.org/abstract/document/10296854) [[code]](https://github.com/PSYZ1234/NIDALoc)
- [2023 CVPR] HypLiLoc: Towards Effective LiDAR Pose Regression with Hyperbolic Fusion [[paper]](https://openaccess.thecvf.com/content/CVPR2023/html/Wang_HypLiLoc_Towards_Effective_LiDAR_Pose_Regression_With_Hyperbolic_Fusion_CVPR_2023_paper.html) [[code]](https://github.com/sijieaaa/HypLiLoc)
- [2023 IEEE TITS] STCLoc: Deep LiDAR Localization with Spatio-Temporal Constraints [[paper]](https://ieeexplore.ieee.org/abstract/document/9928031) [[code]](https://github.com/PSYZ1234/STCLoc)
- [2022 PR] LiDAR-based Localization Using Universal Encoding and Memory-Aware Regression (PosePN, PosePN++, PoseMinkLoc, PoseSOE) [[paper]](https://www.sciencedirect.com/science/article/pii/S0031320322001662) [[code]](https://github.com/PSYZ1234/PosePN)
- [2022 IEEE Sensors J.] PointLoc: Deep Pose Regressor for LiDAR Point Cloud Localization [[paper]](https://ieeexplore.ieee.org/abstract/document/9617633)

### Scene Coordinate Regression (SCR)

- [2025 NeurIPS] GTR-Loc: Geospatial Text Regularization Assisted Outdoor LiDAR Localization [[paper]](https://proceedings.neurips.cc/paper_files/paper/2025/hash/c745bfa5b50544882938ff4f89ff26ac-Abstract-Conference.html) [[code]](https://github.com/PSYZ1234/GTR-Loc)
- [2025 ICCV] RALoc: Enhancing Outdoor LiDAR Localization via Rotation Awareness [[paper]](https://openaccess.thecvf.com/content/ICCV2025/html/Yang_RALoc_Enhancing_Outdoor_LiDAR_Localization_via_Rotation_Awareness_ICCV_2025_paper.html) [[code]](https://etheryangyy.github.io/raloc.github.io/)
- [2025 CVPR] LightLoc: Learning Outdoor LiDAR Localization at Light Speed [[paper]](https://openaccess.thecvf.com/content/CVPR2025/html/Li_LightLoc_Learning_Outdoor_LiDAR_Localization_at_Light_Speed_CVPR_2025_paper.html) [[code]](https://github.com/liw95/LightLoc)
- [2024 CVPR] LiSA: LiDAR Localization with Semantic Awareness [[paper]](https://openaccess.thecvf.com/content/CVPR2024/html/Yang_LiSA_LiDAR_Localization_with_Semantic_Awareness_CVPR_2024_paper.html) [[code]](https://github.com/Ybchun/LiSA)
- [2023 CVPR] SGLoc: Scene Geometry Encoding for Outdoor LiDAR Localization [[paper]](https://openaccess.thecvf.com/content/CVPR2023/html/Li_SGLoc_Scene_Geometry_Encoding_for_Outdoor_LiDAR_Localization_CVPR_2023_paper.html) [[code]](https://github.com/liw95/SGLoc)

## Results

Average `mean position error (m) / mean orientation error (°)` over the four test sequences of each dataset.

- **Paper**: numbers reported in [LightLoc (CVPR 2025)](https://openaccess.thecvf.com/content/CVPR2025/html/Li_LightLoc_Learning_Outdoor_LiDAR_Localization_at_Light_Speed_CVPR_2025_paper.html) and [GTRLoc (NeurIPS 2025)](https://proceedings.neurips.cc/paper_files/paper/2025/hash/c745bfa5b50544882938ff4f89ff26ac-Abstract-Conference.html), Tables 1–3, which evaluates all prior methods under the same protocol. "–" means not reported there.
- **Ours**: computed from the released prediction files in [`predictions/`](predictions/). All training and testing are run on a single NVIDIA RTX 4090 GPU.

| Method | Oxford (paper) | Oxford (ours) | QEOxford (paper) | QEOxford (ours) | NCLT† (paper) | NCLT† (ours) |
| --- | --- | --- | --- | --- | --- | --- |
| PointLoc | 12.45 / 2.17 | 15.04 / 2.17 | 10.79 / 2.14 | 10.62 / 2.14 | 7.45 / 4.58 | 7.45 / 4.58 |
| PosePN | 13.48 / 2.48 | 13.46 / 2.49 | 9.34 / 2.25 | 9.34 / 2.25 | 8.43 / 6.31 | 8.43 / 6.30 |
| PosePN++ | 9.43 / 1.77 | 8.14 / 1.79 | 5.13 / 1.69 | 5.13 / 1.69 | 5.36 / 3.52 | 5.36 / 3.52 |
| PoseMinkLoc | 11.96 / 2.41 | 12.16 / 2.37 | 7.56 / 1.86 | 7.56 / 1.85 | 6.17 / 4.78 | 6.17 / 4.78 |
| PoseSOE | 8.62 / 2.00 | 8.56 / 1.98 | 4.98 / 1.79 | 4.98 / 1.79 | 9.44 / 6.24 | 9.00 / 6.24 |
| HypLiLoc | 5.74 / 1.05 | 6.00 / 1.13 | 3.89 / 1.27 | 4.29 / 1.31 | 1.80 / 3.12 | 1.74 / 2.97 |
| FlashMix | 3.80 / 1.96¹ | 3.83 / 2.02 | – | 2.30 / 2.03 | – | 3.00 / 4.47 |
| DiffLoc | 3.53 / 0.72 | 3.59 / 0.70 | 1.86 / 0.87 | 1.90 / 0.87 | 1.06 / 2.32 | 1.07 / 2.38 |
| SGLoc | 3.14 / 1.88 | 3.15 / 1.90 | 1.53 / 1.60 | 1.56 / 1.61 | 1.75 / 3.46 | 1.75 / 3.47 |
| LiSA | 2.74 / 1.32 | 2.73 / 1.41 | 0.95 / 1.14 | 0.99 / 1.16 | 1.47 / 2.31 | 1.48 / 2.32 |
| RALoc | – | 3.23 / 3.99 | – | 1.51 / 1.25 | – | 2.80 / 5.14 |
| LightLoc | 2.67 / 1.25 | 2.63 / 1.23 | 0.83 / 1.12 | 0.79 / 1.11 | 1.46 / 2.80 | 1.44 / 2.88 |
| GTR-Loc | 2.59 / 1.19 | 2.59 / 1.19 | 0.75 / 1.03 | 0.75 / 1.03 | 1.40 / 2.62 | 1.19 / 2.50 |

¹ Not included in LightLoc; taken from the FlashMix paper (Oxford only, CL Reg. variant).
† On NCLT 2012-05-26, frames 4300–4500 (a region unseen in training) are excluded, following LightLoc.

## More

- [Evaluation protocol, per-sequence results, recall and efficiency](docs/results.md)
- [Prediction file format](docs/predictions.md)

## Acknowledgements

We thank the authors of all the methods above for releasing their code.