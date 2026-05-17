# EAEPNet: Multi-Level Representation Enhancement and Weighted Box Fusion Network for Multi-Modal 3D Object Detection

This repository is the official PyTorch implementation of our paper "EAEPNet: Multi-Level Representation Enhancement and Weighted Box Fusion Network for Multi-Modal 3D Object Detection".

---

##  Installation

### 1. Environment Setup

```bash
The Environment：
Linux (tested on Ubuntu 16.04)
Python 3.6+
PyTorch 1.0+
Install the dependent python：
opencv-python
shapely
Cython
scipy
pandas
pyyaml
json_tricks
scikit-image
yacs>=0.1.5
tensorboardX>=1.6
tqdm
ninja
fire
numba
easydict
##  Data Preparation
Please download the datasets and organize them as follows:
EPNet
├── data
│   ├── KITTI
│   │   ├── ImageSets
│   │   ├── object
│   │   │   ├──training
│   │   │      ├──calib & velodyne & label_2 & image_2 & (optional: planes)
│   │   │   ├──testing
│   │   │      ├──calib & velodyne & image_2
├── lib
├── pointnet2_lib
├── tools
