# 第 6 章 · 让机器人进入现实：仿真与 Sim-to-Real

> 仿真是"廉价数据"的源泉，但仿真与现实之间有 reality gap。本章讲怎么造仿真、怎么过 gap。

## 6.1 主流仿真平台对比
| 平台 | 物理引擎 | 强项 | 弱项 |
| --- | --- | --- | --- |
| **MuJoCo** | 自研 | 接触/动力学精度高、速度快 | 渲染弱 |
| **Isaac Sim / Isaac Lab** | PhysX 5 + GPU | 并行 RL、photoreal 渲染 | 学习曲线陡 |
| **Gazebo / Ignition** | ODE / Bullet | ROS 生态完善 | 性能一般 |
| **Genesis** | 多后端 + GPU | 可微、并行、速度快 | 较新 |
| **SAPIEN / ManiSkill** | PhysX | 操作任务、benchmark | 范围窄 |
| **Webots** | ODE | 教学、轻量 | 不主流 |
| **PyBullet** | Bullet | 入门、Python 友好 | 精度一般 |

## 6.2 仿真建模要点
- URDF / MJCF / USD：物理资产格式
- 物体资产：ShapeNet、Objaverse、GSO、PartNet
- 场景资产：HSSD、ProcThor、Habitat scenes
- 接触参数标定（关键且常被忽视）
- 传感器仿真：相机、深度、LiDAR、IMU 噪声模型

## 6.3 Sim-to-Real 技术
- **域随机化（DR）**：纹理、光照、动力学、传感器噪声
- **域自适应（DA）**：feature alignment、CycleGAN-like
- **Privileged Learning**：teacher 用特权信息，student 只用真机可得信息
- **System Identification**：辨识真实物理参数后回灌仿真
- **Real-to-Sim**：3DGS / NeRF 把真实场景搬进仿真
- **Digital Twin**：与真机硬件一一对应的仿真镜像

## 6.4 数据策略
- 纯仿真训练 → 真机 zero-shot（locomotion 常见）
- 仿真预训练 → 真机少样本微调（manipulation 常见）
- 真机数据为主 + 仿真增广

## 6.5 评测
- 仿真 benchmark：ManiSkill、CALVIN、RoboCasa、LIBERO、Meta-World
- 真机评测：稳定可复现的任务集、统计学严谨的成功率报告

## 6.6 实践路径
1. Isaac Lab 训一个四足 locomotion 并 sim2real
2. ManiSkill / LIBERO 上跑 baseline policy
3. 用 3DGS 把一个真实桌面场景搬进 MuJoCo / Isaac
4. 写一个最简域随机化的训练脚本

## 代码分析待办
- [ ] Isaac Lab `ManagerBasedRLEnv` 抽象
- [ ] MuJoCo MJX（JAX 版）核心
- [ ] Genesis 可微仿真实现
- [ ] ManiSkill 任务定义
