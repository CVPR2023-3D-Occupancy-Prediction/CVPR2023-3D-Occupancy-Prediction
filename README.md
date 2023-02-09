<div id="top" align="center">

# CVPR 2023 Occupancy Prediction Challenge
**The world's First 3D Occupancy Benchmark for Scene Perception in Autonomous Driving.**


<a href="#devkit">
  <img alt="devkit: v0.1.0" src="https://img.shields.io/badge/devkit-v0.1.0-blueviolet"/>
</a>
<a href="#license">
  <img alt="License: Apache2.0" src="https://img.shields.io/badge/license-Apache%202.0-blue.svg"/>
</a>

**[English](./README.md) | [中文](./README-zh-hans.md)**


<img src="./figs/occupanc_1.gif" width="696px">

</div>

## Table of Contents
- [CVPR 2023 Occupancy Prediction Challenge](#cvpr-2023-occupancy-prediction-challenge)
  - [Table of Contents](#table-of-contents)
  - [Highlight](#highlight)
  - [Task](#task)
  - [Metrics](#metrics)
  - [Timeline](#eimeline)
  - [Data](#data)
  - [Devkit](#devkit)
  - [Leaderboard](#leaderboard)
  - [License](#license)

## Highlight


Understanding the 3D surroundings including the background and foreground objects is important for autonomous driving, which can be applied for perception and planning. In the traditional 3D object detection task, the foreground object is represented by the 3D bounding box. However, the geometrical shape of the object is complex, which can not be represented by a simple 3D box, and the perception of the background is absent. The goal of this task is to predict the 3D occupancy of the complete scene. In this task, we provide a large-scale occupancy benchmark based on the nuScenes dataset. The benchmark is a voxelized representation of the 3D space, and the occupancy state and semantics of the voxel in 3D space are jointly estimated in this task. The complexity of this task lies in the dense prediction of 3D space given the input of the image.


<p align="right">(<a href="#top">back to top</a>)</p>

## Task
Given images from multiple cameras, one has to predict the current occupancy state and semantics of each voxel grid in the scene. The voxel state (free or occupied) is needed to be predicted first. If a voxel is occupied, its semantics need to be predicted. Besides, we also provide a known/unknown mask for each scene. The unknown voxel is defined as an invisible grid in the camera, which is ignored in the evaluation.


## Metrics
Leaderboard ranking for this challenge is by the intersection-over-union (mIoU) over all classes. 
### mIoU

Let $C$ be he number of classes. 

$$
    mIoU=\frac{1}{C}\displaystyle \sum_{c=1}^{C}\frac{TP_c}{TP_c+FP_c+FN_c},
$$

where $TP_c$ , $FP_c$ , and $FN_c$ correspond to the number of true positive, false positive, and false negative predictions for class $c_i$.

### F1 Score
We also measure the F-score as the harmonic mean of the completeness $P_c$ and the accuracy $P_a$.

$$
    F-score=\left( \frac{P_a^{-1}+P_c^{-1}}{2} \right) ^{-1} ,
$$
where $P_a$ is the percentage of predicted voxels that are within a distance threshold to the ground truth voxels, and $P_c$ is the percentage of ground truth voxels that are within a distance threshold to the predicted voxels.

<p align="right">(<a href="#top">back to top</a>)</p>

## Timeline
- Feb 15, 2023 - Dataset and Devkit Release.
- Mar 16, 2023 - Challenge Period Open.
- May 27, 2023 - Challenge Period End.
- May 29, 2023 - Finalist Notification.
- Jun 10, 2023 - Technical Report Deadline.
- Jun 12, 2023 - Winner Announcement.
<p align="right">(<a href="#top">back to top</a>)</p>

## Data

To be released.

<p align="right">(<a href="#top">back to top</a>)</p>

## Devkit

To be released.

<p align="right">(<a href="#top">back to top</a>)</p>


## Leaderboard 
To be released.

<p align="right">(<a href="#top">back to top</a>)</p>

## License
Before using the dataset, you should register on the website and agree to the terms of use of the [nuScenes](https://www.nuscenes.org/nuscenes).
All code within this repository is under [Apache License 2.0](./LICENSE).

<p align="right">(<a href="#top">back to top</a>)</p>
