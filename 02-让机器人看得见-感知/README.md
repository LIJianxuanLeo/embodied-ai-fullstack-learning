# 第 2 章 · 让机器人看得见：感知

> 机器人的"眼睛"和"皮肤"。本章覆盖从原始传感器到语义/几何表征的全链路，强调**机器人场景下的感知**（实时、闭环、可控）与一般 CV 的差异。

## 2.1 传感器与标定
- 相机：针孔模型、畸变、内参/外参
- 深度相机：结构光（RealSense D435）、ToF（Azure Kinect）、双目
- LiDAR：机械/固态、稠密点云
- 触觉：GelSight、DIGIT、力/扭矩传感器
- IMU：加速度计 + 陀螺 + 磁力，预积分
- **多传感器标定**：Camera-IMU（Kalibr）、Camera-LiDAR、Hand-Eye

## 2.2 2D 视觉
- 检测：YOLO 系列、DETR、Grounding-DINO
- 分割：SAM / SAM2、Mask2Former、可促进的开放词汇分割
- 跟踪：ByteTrack、SAM2 tracking
- 关键点 / 姿态：FoundationPose、MegaPose

## 2.3 3D 视觉
- 点云基础：PCL、Open3D
- 点云网络：PointNet/++、PointTransformer、Sparse Conv
- 深度估计：Depth Anything、ZoeDepth、Metric3D
- **新表征**：NeRF、3D Gaussian Splatting，及其在机器人中的角色（Real2Sim、场景理解）
- 重建：TSDF、Voxel hash、SplaTAM

## 2.4 多模态与基础模型
- 视觉基础模型：DINOv2 / DINOv3、SAM、CLIP
- 通用表征 + 机器人下游适配：R3M、VC-1、Voltron
- 视频预训练：V-JEPA、Open-Sora
- 触觉 + 视觉融合
- 语言驱动感知：CLIP-Fields、OK-Robot

## 2.5 机器人感知的特殊性
- **实时性**：30Hz / 100Hz 闭环
- **主动感知**：next-best-view、注视控制
- **可控视角**：手眼相机 vs 头部相机
- **跨域泛化**：仿真→真实、白天→夜间
- **不确定性**：感知失败时的兜底（控制层降级）

## 2.6 实践路径
1. 用 RealSense + Open3D 做一个抓取点检测 demo
2. 在 Isaac Sim 里训练一个目标检测，sim2real 部署
3. 复现 SAM2 在视频中的跟踪 → 输出 mask 给操作模块

## 代码分析待办
- [ ] SAM / SAM2 推理路径
- [ ] FoundationPose 6D 姿态估计流程
- [ ] DINOv2 特征用于 manipulation 的范式
- [ ] 3DGS-SLAM 实现细节
