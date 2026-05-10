# 第 3 章 · 让机器人找到位置：状态估计、定位与 SLAM

> 没有"我在哪"，就没有"我去哪"。本章从概率推断的视角统一状态估计、定位、建图三件事。

## 3.1 概率与估计基础
- 贝叶斯滤波框架
- 高斯假设下的卡尔曼滤波（KF / EKF / UKF / IEKF）
- 粒子滤波（MCL）
- 因子图与非线性优化（GTSAM、Ceres、g2o）
- MAP vs MLE、最大似然 vs 最大后验

## 3.2 里程计
- 轮式里程计：差速 / 阿克曼模型
- IMU 预积分（Forster et al.）
- 视觉里程计 VO：直接法 vs 特征法
- VIO：MSCKF、VINS-Mono、OpenVINS、ORB-SLAM3 的 VIO 模式
- LiDAR 里程计：LOAM、FAST-LIO2、Point-LIO

## 3.3 SLAM
- **视觉 SLAM**：ORB-SLAM3、DSO、SVO
- **LiDAR SLAM**：LOAM 家族、LIO-SAM、FAST-LIO、SLICT
- **多传感器融合**：LVI-SAM、R3LIVE、FAST-LIVO2
- **稠密 / 神经 SLAM**：BundleFusion、NICE-SLAM、SplaTAM、MonoGS
- 闭环检测、全局优化、地图保存与重定位

## 3.4 定位（在已知地图中）
- AMCL（粒子滤波 + 占据栅格地图）
- NDT 配准、ICP 家族
- 语义定位、GPS/RTK 融合
- 室内/室外切换

## 3.5 与下游的接口
- 给规划：稳定 / 低延迟的位姿
- 给感知：把检测投到全局坐标
- 给控制：高频里程计 vs 低频全局位姿融合策略

## 3.6 实践路径
1. 在 ROS2 跑通 Cartographer 或 FAST-LIO2 建一张办公室地图
2. 用 AMCL 在地图中做导航定位
3. 写一个最简 EKF 融合 IMU + 轮速
4. 阅读 ORB-SLAM3 框架

## 代码分析待办
- [ ] ORB-SLAM3 主循环与回环
- [ ] FAST-LIO2 IEKF 实现
- [ ] GTSAM 因子图构建
- [ ] SplaTAM / MonoGS 神经地图
