# EAEPNet: Multi-Level Representation Enhancement and Weighted Box Fusion Network for Multi-Modal 3D Object Detection

This repository is the official PyTorch implementation of our paper "EAEPNet: Multi-Level Representation Enhancement and Weighted Box Fusion Network for Multi-Modal 3D Object Detection".

---


##  Installation

### 1. Environment Setup
The environment has been tested under the following settings:
* **OS**: Linux (tested on Ubuntu 16.04)
* **Python**: 3.6+
* **PyTorch**: 1.0+

### 2. Install Dependencies

You can install the required packages via `requirements.txt`:

```bash
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
```

##  Data Preparation

Please download the datasets and organize them as follows:

```bash
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
```
##  Train

```bash
CUDA_VISIBLE_DEVICES=0 python train_rcnn.py --cfg_file cfgs/LI_Fusion_with_attention_use_ce_loss.yaml --batch_size 2 --train_mode rcnn_online --epochs 50 --ckpt_save_interval 1 --output_dir ./log/Car/full_epnet_without_iou_branch/   --set LI_FUSION.ENABLED True LI_FUSION.ADD_Image_Attention True RCNN.POOL_EXTRA_WIDTH 0.2 RPN.SCORE_THRESH 0.2 RCNN.SCORE_THRESH 0.2  USE_IOU_BRANCH False TRAIN.CE_WEIGHT 5.0
```

##  Train

```bash
CUDA_VISIBLE_DEVICES=2 python eval_rcnn.py --cfg_file cfgs/LI_Fusion_with_attention_use_ce_loss.yaml --eval_mode rcnn_online  --eval_all  --output_dir ./log/Car/full_epnet_without_iou_branch/eval_results/  --ckpt_dir ./log/Car/full_epnet_without_iou_branch/ckpt --set  LI_FUSION.ENABLED True LI_FUSION.ADD_Image_Attention True RCNN.POOL_EXTRA_WIDTH 0.2  RPN.SCORE_THRESH 0.2 RCNN.SCORE_THRESH 0.2  USE_IOU_BRANCH False
```
