# HUMS DEXR Dataset

Dataset release for WACV submission.
Link for original HUMS dataset: https://github.com/ElifErarslan1/HUMS-X-ray-Dataset

## Folder Structure

```
HUMS_DEXR_DATASET/
├── Fused_HUMSDEXR_dataset/
│   ├── heavy_occ/
│   ├── medium_occ/
│   └── light_occ/
└── Source_HUMS_data/
    ├── bags_source/
    ├── knife_source/
    └── non_threat_source/
```

## Description

- **Fused_HUMSDEXR_dataset/** — Fused dual-energy X-ray images, organized by occlusion severity:
  - `heavy_occ/` — Heavily occluded scans
  - `medium_occ/` — Moderately occluded scans
  - `light_occ/` — Lightly occluded scans

- **Source_HUMS_data/** — Raw dual-energy source X-ray  scans prior to fusion, obtained from HUMS dataset, organized by object category:
  - `bags_source/` — Bag scans
  - `knife_source/` — Knife threat scans
  - `non_threat_source/` — Non-threat item scans

## File Format

- Source files are stored as `.npz`, containing single-channel dual-energy X-ray data as 2D arrays.
- Fused images are stored as 16 bit `.tif` format, containing single-channel dual-energy X-ray data.

## Reading the .npz files

```python
import numpy as np

data = np.load("FILE_NAME.npz")
print(data.files)          # list arrays stored in the archive
arr = data[data.files[0]]  # load the array
print(arr.shape, arr.dtype)
```

## Notes

- This dataset is being used purely to provide a common academic public benchmark for de-occlusion in dual energy X-ray images and we have not used it for any commercial purpose.
