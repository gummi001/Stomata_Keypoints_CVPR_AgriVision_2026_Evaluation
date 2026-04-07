# Stomata Keypoint Benchmark for Cross-Domain Evaluation

This repository contains the evaluation notebooks for the CVPR 2026 AgriVision Workshop paper:

**Towards Morphology Aware Stomata Keypoint Detection: Benchmarking Foundation Models Under Distribution Shift**

The benchmark evaluates stomata keypoint detection under controlled distribution shift across location, environment, taxonomy, species, and microscope system.

## Released Assets

| Asset | Link | DOI |
|---|---|---|
| Dataset | [Hugging Face](https://huggingface.co/datasets/Sainath001/stomata-keypoint-benchmark-cvpr-agrivision-2026-Dataset) | [10.57967/hf/8280](https://doi.org/10.57967/hf/8280) |
| Model weights | [Hugging Face](https://huggingface.co/Sainath001/stomata-keypoint-benchmark-cvpr-agrivision-2026-models) | [10.57967/hf/8279](https://doi.org/10.57967/hf/8279) |
| Paper | Coming soon | — |

## What This Repository Contains

- evaluation notebooks for the four benchmarked pipelines
- minimal code needed to run inference and evaluation
- notes for using the released dataset and model weights

This repository does not host the dataset or model weights directly.

## Benchmark Summary

The benchmark includes **1 training split** (`KP-Train`) and **9 held-out test splits**.

| Shift type | Test splits |
|---|---|
| Location | `T-MZA` |
| Plant-level | `T-MZLP` |
| Environment | `T-SBGH`, `T-HR5MZ`, `T-TCMZ` |
| Taxonomy | `T-SBGH`, `T-MSAA`, `T-TCAB` |
| Species | `T-HR5WH`, `T-NKBY`, `T-MSAA` |
| Sensor/system | `T-HR5MZ`, `T-HR5WH`, `T-TCMZ`, `T-TCAB`, `T-NKBY` |

Each stomata instance is annotated in **COCO keypoint format** with four keypoints:
- `p0, p1`: polar tips along the stomatal length axis
- `p2, p3`: lateral endpoints along the stomatal width axis
- Some public benchmark splits provide annotations only. For those splits, original images must be obtained separately from the source links listed in the Hugging Face dataset card.

## Evaluated Pipelines

| Pipeline | Type | Detector | Keypoint head |
|---|---|---|---|
| `KP-RCNN-X101` | End-to-end | ResNeXt-101 + FPN | Built-in |
| `YOLO26X-Pose` | End-to-end | YOLO26X | Built-in |
| `GDINO-SB → ViTPose++` | Two-stage | Grounding DINO (Swin-B) | ViTPose++ Huge |
| `SAM 3 → ViTPose++` | Two-stage | SAM 3 | ViTPose++ Huge |

## Citation

If you use this benchmark, please cite:

```bibtex
@inproceedings{gummi2026stomata,
  author    = {Gummi, S. R. and Pack, C. and Zhang, H. K. and Solanki, S. and Chang, Y.},
  title     = {Towards Morphology Aware Stomata Keypoint Detection: Benchmarking Foundation Models Under Distribution Shift},
  booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops},
  year      = {2026},
  note      = {Accepted}
}
```

## Contact

**Sainath Reddy Gummi**
South Dakota State University
Email: [gummisainath@gmail.com](mailto:gummisainath@gmail.com)
