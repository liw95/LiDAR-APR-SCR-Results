<div align="center">

# LiDAR APR & SCR: Reproduced Results and Predictions

Reproduced results and per-frame predictions of **13 regression-based LiDAR localization methods**<br>
covering **absolute pose regression (APR)** and **scene coordinate regression (SCR)**<br>
on **Oxford Radar RobotCar**, **QEOxford** and **NCLT**

<p>
<img src="https://img.shields.io/badge/Methods-13-blue" alt="Methods">
<img src="https://img.shields.io/badge/Datasets-Oxford%20%7C%20QEOxford%20%7C%20NCLT-orange" alt="Datasets">
<img src="https://img.shields.io/badge/GPU-RTX%204090-76B900?logo=nvidia&logoColor=white" alt="GPU">
<img src="https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0%20%7C%20ODbL%201.0-lightgrey" alt="License">
</p>

[**Methods**](#-methods) · [**Results**](#-results) · [**Detailed Results**](docs/results.md) · [**Prediction Files**](docs/predictions.md) · [**License**](#-license)


</div>

## 📚 Methods

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
- [2025 ICCV] RALoc: Enhancing Outdoor LiDAR Localization via Rotation Awareness [[paper]](https://openaccess.thecvf.com/content/ICCV2025/html/Yang_RALoc_Enhancing_Outdoor_LiDAR_Localization_via_Rotation_Awareness_ICCV_2025_paper.html) [[project]](https://etheryangyy.github.io/raloc.github.io/)
- [2025 CVPR] LightLoc: Learning Outdoor LiDAR Localization at Light Speed [[paper]](https://openaccess.thecvf.com/content/CVPR2025/html/Li_LightLoc_Learning_Outdoor_LiDAR_Localization_at_Light_Speed_CVPR_2025_paper.html) [[code]](https://github.com/liw95/LightLoc)
- [2024 CVPR] LiSA: LiDAR Localization with Semantic Awareness [[paper]](https://openaccess.thecvf.com/content/CVPR2024/html/Yang_LiSA_LiDAR_Localization_with_Semantic_Awareness_CVPR_2024_paper.html) [[code]](https://github.com/Ybchun/LiSA)
- [2023 CVPR] SGLoc: Scene Geometry Encoding for Outdoor LiDAR Localization [[paper]](https://openaccess.thecvf.com/content/CVPR2023/html/Li_SGLoc_Scene_Geometry_Encoding_for_Outdoor_LiDAR_Localization_CVPR_2023_paper.html) [[code]](https://github.com/liw95/SGLoc)

## 📊 Results

Average `mean position error (m) / mean orientation error (°)` over the four test sequences of each dataset.

- **Paper**: numbers reported in [LightLoc (CVPR 2025)](https://openaccess.thecvf.com/content/CVPR2025/html/Li_LightLoc_Learning_Outdoor_LiDAR_Localization_at_Light_Speed_CVPR_2025_paper.html) and [GTRLoc (NeurIPS 2025)](https://proceedings.neurips.cc/paper_files/paper/2025/hash/c745bfa5b50544882938ff4f89ff26ac-Abstract-Conference.html), which evaluate prior methods under the same protocol. "–" means not reported there.
- **Ours**: computed from the released prediction files in [`predictions/`](predictions/). All training and testing are run on a single NVIDIA RTX 4090 GPU.

| Method | Oxford (paper) | Oxford (ours) | QEOxford (paper) | QEOxford (ours) | NCLT† (paper) | NCLT† (ours) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| PointLoc | 12.45&nbsp;/&nbsp;2.17 | 15.04&nbsp;/&nbsp;2.17 | 10.79&nbsp;/&nbsp;2.14 | 10.62&nbsp;/&nbsp;2.14 | 7.45&nbsp;/&nbsp;4.58 | 7.45&nbsp;/&nbsp;4.58 |
| PosePN | 13.48&nbsp;/&nbsp;2.48 | 13.46&nbsp;/&nbsp;2.49 | 9.34&nbsp;/&nbsp;2.25 | 9.34&nbsp;/&nbsp;2.25 | 8.43&nbsp;/&nbsp;6.31 | 8.43&nbsp;/&nbsp;6.30 |
| PosePN++ | 9.43&nbsp;/&nbsp;1.77 | 8.14&nbsp;/&nbsp;1.79 | 5.13&nbsp;/&nbsp;1.69 | 5.13&nbsp;/&nbsp;1.69 | 5.36&nbsp;/&nbsp;3.52 | 5.36&nbsp;/&nbsp;3.52 |
| PoseMinkLoc | 11.96&nbsp;/&nbsp;2.41 | 12.16&nbsp;/&nbsp;2.37 | 7.56&nbsp;/&nbsp;1.86 | 7.56&nbsp;/&nbsp;1.85 | 6.17&nbsp;/&nbsp;4.78 | 6.17&nbsp;/&nbsp;4.78 |
| PoseSOE | 8.62&nbsp;/&nbsp;2.00 | 8.56&nbsp;/&nbsp;1.98 | 4.98&nbsp;/&nbsp;1.79 | 4.98&nbsp;/&nbsp;1.79 | 9.44&nbsp;/&nbsp;6.24 | 9.00&nbsp;/&nbsp;6.24 |
| HypLiLoc | 5.74&nbsp;/&nbsp;1.05 | 6.00&nbsp;/&nbsp;1.13 | 3.89&nbsp;/&nbsp;1.27 | 4.29&nbsp;/&nbsp;1.31 | 1.80&nbsp;/&nbsp;3.12 | 1.74&nbsp;/&nbsp;2.97 |
| FlashMix | 3.80&nbsp;/&nbsp;1.96¹ | 3.83&nbsp;/&nbsp;2.02 | – | 2.30&nbsp;/&nbsp;2.03 | – | 3.00&nbsp;/&nbsp;4.47 |
| DiffLoc | 3.53&nbsp;/&nbsp;0.72 | 3.59&nbsp;/&nbsp;0.70 | 1.86&nbsp;/&nbsp;0.87 | 1.90&nbsp;/&nbsp;0.87 | 1.06&nbsp;/&nbsp;2.32 | 1.07&nbsp;/&nbsp;2.38 |
| SGLoc | 3.14&nbsp;/&nbsp;1.88 | 3.15&nbsp;/&nbsp;1.90 | 1.53&nbsp;/&nbsp;1.60 | 1.56&nbsp;/&nbsp;1.61 | 1.75&nbsp;/&nbsp;3.46 | 1.75&nbsp;/&nbsp;3.47 |
| LiSA | 2.74&nbsp;/&nbsp;1.32 | 2.73&nbsp;/&nbsp;1.41 | 0.95&nbsp;/&nbsp;1.14 | 0.99&nbsp;/&nbsp;1.16 | 1.47&nbsp;/&nbsp;2.31 | 1.48&nbsp;/&nbsp;2.32 |
| RALoc | – | 3.23&nbsp;/&nbsp;3.99 | – | 1.51&nbsp;/&nbsp;1.25 | – | 2.80&nbsp;/&nbsp;5.14 |
| LightLoc | 2.67&nbsp;/&nbsp;1.25 | 2.63&nbsp;/&nbsp;1.23 | 0.83&nbsp;/&nbsp;1.12 | 0.79&nbsp;/&nbsp;1.11 | 1.46&nbsp;/&nbsp;2.80 | 1.44&nbsp;/&nbsp;2.88 |
| GTR-Loc | 2.59&nbsp;/&nbsp;1.19 | 2.59&nbsp;/&nbsp;1.19 | 0.75&nbsp;/&nbsp;1.03 | 0.75&nbsp;/&nbsp;1.03 | 1.40&nbsp;/&nbsp;2.62 | 1.19&nbsp;/&nbsp;2.50 |

¹ Not reported in LightLoc or GTR-Loc; taken from the FlashMix paper (Oxford only, CL Reg. variant).

† On NCLT 2012-05-26, frames 4300–4500 (a region unseen in training) are excluded, following LightLoc.

## 📁 More

- [Evaluation protocol, per-sequence results, recall and efficiency](docs/results.md)
- [Prediction file format](docs/predictions.md)

## 🙏 Acknowledgements

We thank the authors of all the methods above for releasing their code. If you use any results in this repository, please cite the original paper of the corresponding method.

## 📄 License

The released files are derived from datasets with different licenses, so each part follows the license of its source dataset:

| Files | License |
| --- | --- |
| `predictions/*/Oxford/`, `predictions/*/QEOxford/` | [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/), following Oxford Radar RobotCar |
| `predictions/*/NCLT/` | [ODbL 1.0](http://opendatacommons.org/licenses/odbl/1.0/) (contents under [DbCL 1.0](http://opendatacommons.org/licenses/dbcl/1.0/)), following NCLT |
| README, `docs/`, `experiments_summary.csv` | [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) |

When using these files, please also cite the dataset papers. See [LICENSE](LICENSE) for details.
