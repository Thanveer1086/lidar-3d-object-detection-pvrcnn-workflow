# LiDAR 3D Object Detection using OpenPCDet

This repository contains a complete workflow for LiDAR-based **3D Object Detection** using **OpenPCDet**.  
It includes environment setup, dataset preparation, training, inference, and testing steps using the KITTI dataset.

---

## 🚀 1. Prerequisites

All models are tested in the below environment:

- Linux (Ubuntu 14.04 / 16.04 / 18.04 / 20.04 / 21.04)
- Python 3.6+
- PyTorch 1.1 or higher (tested on 1.1, 1.3, 1.5–1.10)
- CUDA 9.0+ (PyTorch 1.3+ requires CUDA 9.2+)
- spconv v1.0 / v1.2 / v2.x

> Note: LiDAR models work best on Python 3.8.  
> CUDA + PyTorch versions must match to avoid compatibility errors.

---

## 📂 2. KITTI Dataset Preparation

Download KITTI 3D Object Detection dataset and arrange it as:

data/kitti/
├── ImageSets/
│ ├── train.txt
│ ├── val.txt
│ ├── test.txt
├── training/
│ ├── velodyne/
│ ├── label_2/
│ ├── calib/
├── testing/
├── velodyne/
├── calib/



- `ImageSets` folder is used for dataset splitting.
- Add only the required sample IDs inside train/val/test text files.

---

## 🏋️‍♂️ 3. Training Pipeline

Example: Train **PV-RCNN** on KITTI:

```bash
python train.py --cfg_file cfgs/kitti_models/pv_rcnn.yaml
