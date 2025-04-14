<div align="center">
    <h1>Doppler-SLAM</h1>
</div>

**Doppler-SLAM** is a unified SLAM approach that combines a tightly-coupled front-end with a graph optimization back-end, seamlessly integrating IMU, 4D radar or FMCW LiDAR, and Doppler velocity measurements.

*Note: Our research paper is currently under review. The source code and dataset will be made available upon publication.*

<div align="center">
    <img src="./resource/pics/intro_doppler_slam.png" alt="Doppler-SLAM" width="100%"/>
</div>

## Demo

## Overview
Pipeline of Doppler-SLAM consists of four main modules: velocity filter, motion compensation, state estimation, and loop closure with graph optimization. The graph on the right illustrates the workflow of online extrinsic calibration between the IMU and either radar or LiDAR using graph optimization. In this approach, we combine the IMU pre-integration factor, odometry factor, and ego velocity factor to construct a factor graph. Once a loop closure factor is detected, additional optimization refines the extrinsic transformation.

<div align="center">
    <img src="./resource/pics/Doppler-SLAM-D-SLAM.png" alt="Doppler-SLAM-overview" width="100%"/>
</div>

## Usage

## Dataset


