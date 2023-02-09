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
    - [Definition](#definition)
    - [Input](#input)
    - [Output](#output)
    - [Metrics](#metrics)
  - [News](#news)
  - [Data](#data)
  - [Devkit](#devkit)
  - [Get Started](#get-started)
  - [Benchmark and Leaderboard (To be released)](#benchmark-and-leaderboard-to-be-released)
  - [Citation](#citation)
  - [License](#license)

## Highlight


Understanding the 3D surroundings including the background and foreground object is important for autonomous driving, which can be applied for perception and planning. In the traditional 3D object detection task, the foreground object is represented by the 3D bounding box. However, the geometrical shape of the object is complex, which can not be represented by a simple 3D box, and the perception of background is absent. The goal of this task is to predict the 3D occupancy of the complete scene. In this task, we provide a large-scale occupancy benchmark based on the nuScenes dataset. The benchmark is a voxelized representation of the 3D space, and the occupancy state and semantics of voxel in 3D space are jointly estimated in this task. The complexity of this task lies in the dense prediction of 3D space given the input of image.


<p align="right">(<a href="#top">back to top</a>)</p>

## Task

### Definition

### Input

### Output

### Metrics



<p align="right">(<a href="#top">back to top</a>)</p>

## News
- [2023/02/15]
  * Dataset `v0.1`: Initial Training and validation dataset sample will be released.
  * Devkit `v0.1.0`: Initial devkit will be released.

<p align="right">(<a href="#top">back to top</a>)</p>

## Data


<p align="right">(<a href="#top">back to top</a>)</p>

## Devkit

<p align="right">(<a href="#top">back to top</a>)</p>

## Get Started

<p align="right">(<a href="#top">back to top</a>)</p>

## Benchmark and Leaderboard (To be released)
We will provide an initial benchmark on the dataset, and you are welcome to add your work here!
Please stay tuned for the release of the benchmark.



<p align="right">(<a href="#top">back to top</a>)</p>

## Citation
Our dataset is built on top of the [nuScenes](https://www.nuscenes.org/nuscenes) datasets. Please cite:

```bibtex
@article{ nuscenes2019,
  author = {Holger Caesar and Varun Bankiti and Alex H. Lang and Sourabh Vora and Venice Erin Liong and Qiang Xu and Anush Krishnan and Yu Pan and Giancarlo Baldan and Oscar Beijbom},
  title = {nuScenes: A multimodal dataset for autonomous driving},
  journal = {arXiv preprint arXiv:1903.11027},
  year = {2019}
}

```

<p align="right">(<a href="#top">back to top</a>)</p>

## License
Before using the dataset, you should register on the website and agree to the terms of use of the [nuScenes](https://www.nuscenes.org/nuscenes).
All code within this repository is under [Apache License 2.0](./LICENSE).

<p align="right">(<a href="#top">back to top</a>)</p>
