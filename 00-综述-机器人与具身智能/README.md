# 第 0 章 · 综述：机器人与具身智能

> 本章建立全局视角：搞清楚"具身智能"是什么、它和传统机器人 / 传统 AI 是什么关系，以及全栈技术地图长什么样。读完应能回答：**我现在在哪、要去哪、走哪条路最短。**

## 0.1 概念辨析
- 机器人（Robot） vs 具身智能（Embodied AI / Embodied Intelligence）
- 与 LLM / 多模态大模型 / Agent 的边界
- 与传统机器人学（Robotics）的承接与扬弃
- 关键词：感知—认知—决策—执行闭环、物理交互、世界模型

## 0.2 发展脉络
- 工业机械臂 → 移动机器人 → 服务/协作机器人 → 人形机器人
- 经典三层架构（Sense-Plan-Act） → 端到端策略 → VLA → 世界模型驱动
- 关键节点：DARPA Challenge、Boston Dynamics、RT-1/2、OpenVLA、π0、人形机器人浪潮

## 0.3 技术全景图
- **硬件层**：本体（机械臂 / 移动底盘 / 人形）、传感器（相机 / LiDAR / IMU / 力触觉）、计算（Jetson / x86 / 国产芯片）
- **基础软件**：ROS2、实时系统、驱动、通信中间件
- **算法层**：运动学动力学控制、感知、SLAM、规划、学习（RL / IL / VLA）、世界模型
- **平台层**：仿真（MuJoCo / Isaac / Genesis）、数据采集、训练框架
- **产品层**：场景定义、商业模式、安全合规

## 0.4 主要学派
| 学派 | 思路 | 代表 |
| --- | --- | --- |
| 模型驱动 | 解析建模 + 控制 | 工业机器人、MPC、阻抗控制 |
| 数据驱动 | 端到端学习 | RT 系列、OpenVLA、π0 |
| 混合派 | 模型 + 学习 | HIL-SERL、Diffusion Policy + MPC、Residual RL |
| 世界模型派 | 想象+规划 | Dreamer、UniSim、Genie |

## 0.5 推荐入门资源
- 教材：《Modern Robotics》Lynch & Park；《Probabilistic Robotics》Thrun
- 综述：survey on Foundation Models for Robotics、VLA survey
- 课程：Berkeley CS287、Stanford CS223A / CS236

## 0.6 学习路线建议
1. 先把第 1 章（动起来）和第 2 章（看见）打通 —— 没有运动+感知，后面都是空中楼阁
2. 第 3 章 SLAM 与第 4 章规划可并行
3. 第 5 章（学习）是当前研究主战场，建议在 1-4 都有手感后切入
4. 第 6 章仿真贯穿全程，越早动手越好
5. 第 7 章产品视角在你选择方向时再深读

## 笔记区
- [ ] TODO：补一张技术栈全景图（assets/）
- [ ] TODO：整理 2020-2026 关键论文/产品时间线
