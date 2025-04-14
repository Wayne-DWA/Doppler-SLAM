<div align="center">
    <h1>Doppler-SLAM</h1>
</div>

**Doppler-SLAM** is a unified SLAM approach that combines a tightly-coupled front-end with a graph optimization back-end, seamlessly integrating IMU, 4D radar or FMCW LiDAR, and Doppler velocity measurements.

*Note: Our paper is currently under review. The source code and dataset will be made available upon publication.*

<div align="center">
    <img src="./resource/pics/intro_doppler_slam.png" alt="Doppler-SLAM" width="100%"/>
</div>

## Demo

<div align="center">
  <table>
    <tr>
      <td>
        <img src="resource/gif/sprot_aeva_speed.gif" alt="doppler_slam_aeva" width="100%">
        <p><em>Doppler SLAM with FMCW LiDAR on Sequence "Sports Complex" from HeRCULES dataset.</em></p>
      </td>
    </tr>
    <tr>
      <td>
        <img src="resource/gif/woehrdersee_full.gif" alt="doppler_slam_radar" width="100%">
        <p><em>Doppler SLAM with 4D Radar on Sequence ""WoehrSee" from our IMADAR dataset.</em></p>
      </td>
    </tr>
        <tr>
          <td>
            <img src="resource/pics/data_1.png" alt="doppler_slam_radar_full" width="100%" style="background-color: white">
            <p><em>Results of Doppler SLAM with 4D Radar on Sequence ""WoehrSee" from our IMADAR dataset.</em></p>
          </td>
        </tr>
        <tr>
      <td>
        <img src="resource/gif/N4_speed.gif" alt="doppler_slam_radar_high_speed" width="100%">
        <p><em>Doppler SLAM with 4D Radar on Sequence ""N4" from our IMADAR dataset (vehicle speeds up to 110 km/h).</em></p>
      </td>
    </tr>
  </table>
</div>

## Overview

Pipeline of Doppler-SLAM consists of four main modules: velocity filter, motion compensation, state estimation, and loop closure with graph optimization. The graph on the right illustrates the workflow of online extrinsic calibration between the IMU and either radar or LiDAR using graph optimization. In this approach, we combine the IMU pre-integration factor, odometry factor, and ego velocity factor to construct a factor graph. Once a loop closure factor is detected, additional optimization refines the extrinsic transformation.

<div align="center">
    <img src="./resource/pics/Doppler-SLAM-D-SLAM.png" alt="Doppler-SLAM-overview" width="100%"/>
</div>

## Usage

todo

## Dataset

todo
### Hardware Setup

<div align="center"> 
    <img src="./resource/pics/car.jpeg" alt="setup_car" width="100%"/>
</div>

<div align="center">
    <img src="./resource/pics/cad_setup.png" alt="setup_sensors" width="100%"/>
</div>

### Sensor Specification

| Sensor | Model | Specifications |
|--------|-------|----------------|
| 4D Radar | Altos V2 | Range: 0.2-200m, Azimuth Resolution: 1.38°, Range Resolution: 0.35m, Speed Resolution: 0.2m/s, Up to 6000 points per frame @ 15fps |
| LiDAR | 2 × Livox Mid-70 | Range: 0.1-130m, Range Resolution: 0.02m, Point Density: Up to 100,000 points/s |
| IMU | Spatial Phidget | Gyroscope Bias Stability: 0.7°/s, Accelerometer Bias Stability: 5mg |
| GNSS/RTK | U-Blox F9 | Position Accuracy: 1cm + 1ppm (RTK), Velocity Accuracy: 0.03m/s |
| Camera | OAK-D Pro | Resolution: 12MP RGB, 1280×800 Stereo, FOV: 75° HFOV, Depth: Up to 19.5m, Onboard AI Processing |

