# YOLOP - Autonomous Driving Perception (Thesis)

Multi-task model for object detection, drivable area segmentation, and lane detection.

## Results
| Task | Metric | Score |
|------|--------|-------|
| Object Detection | mAP@0.5 | 0.75 |
| Drivable Area | mIOU | 0.89 |
| Lane Detection | mIOU | 0.70 |

## Training Curves
![Training Curves](yolop_training_curves.png)

## Model Weights
Download: [Google Drive - updating]

## Training
- Dataset: BDD45K (subset of BDD100K)
- GPU: Kaggle T4
- Epochs: 118
- Optimizer: Adam, LR=0.001

## Reference
[YOLOP paper](https://arxiv.org/abs/2108.11250)
