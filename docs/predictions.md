# Prediction Files

[← Back to README](../README.md)

Per-frame predictions are organized by method, dataset and test sequence:

```text
predictions/
└── <Method>/
    ├── Oxford/
    │   ├── 15-13-06-37/
    │   ├── 17-13-26-39/
    │   ├── 17-14-03-00/
    │   └── 18-14-14-42/
    ├── QEOxford/
    │   └── (same four sequences)
    └── NCLT/
        ├── 2012-02-12/
        ├── 2012-02-19/
        ├── 2012-03-31/
        └── 2012-05-26/
```

Each sequence folder contains plain-text files with one row per test frame, space-separated, in the same frame order across files:

| File | Columns | Description |
| --- | --- | --- |
| `gt_t.txt` | `x y z` | Ground-truth position (m) |
| `pred_t.txt` | `x y z` | Predicted position (m) |
| `gt_q.txt` | `qw qx qy qz` | Ground-truth orientation (unit quaternion) |
| `pred_q.txt` | `qw qx qy qz` | Predicted orientation (unit quaternion) |
| `error_t.txt` | `e` | Position error (m) |
| `error_q.txt` | `e` | Orientation error (°) |

Orientation files provided by each method (all methods provide `gt_t`, `pred_t`, `error_t` and `error_q` for every sequence):

| Method | `gt_q` | `pred_q` |
| --- | :-: | :-: |
| PointLoc | | QEOxford, NCLT |
| PosePN | | |
| PosePN++ | | QEOxford, NCLT |
| PoseMinkLoc | | QEOxford, NCLT |
| PoseSOE | | QEOxford, NCLT |
| HypLiLoc | ✓ | ✓ |
| FlashMix | | ✓ |
| DiffLoc | | |
| SGLoc | | |
| LiSA | | ✓ |
| RALoc | | ✓ |
| LightLoc | ✓ | ✓ |
| GTR-Loc | ✓ | ✓ |
