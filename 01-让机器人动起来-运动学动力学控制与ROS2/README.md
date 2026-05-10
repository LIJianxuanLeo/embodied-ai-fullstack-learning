# 第 1 章 · 让机器人动起来：运动学、动力学、控制与 ROS2

> 这是机器人学的"地基"。任何上层算法最终都要通过关节/轮子转起来。本章目标：能把一台机械臂从仿真到真机驱动起来，并理解每个数学环节。

## 1.1 运动学（Kinematics）
- 刚体变换：旋转矩阵 / 欧拉角 / 四元数 / 轴角 / 李群 SO(3)、SE(3)
- DH 参数与 URDF
- **正运动学（FK）**：关节角 → 末端位姿
- **逆运动学（IK）**：末端位姿 → 关节角
  - 解析 IK、数值 IK（Newton / Damped Least Squares）
  - 冗余机械臂、零空间
- 雅可比矩阵：速度映射、奇异性
- 速度运动学、加速度运动学

## 1.2 动力学（Dynamics）
- 牛顿-欧拉法 vs 拉格朗日法
- 惯量参数、质心、惯量张量
- 关节空间动力学方程：`M(q)q̈ + C(q,q̇)q̇ + G(q) = τ`
- 操作空间动力学
- 接触动力学、摩擦模型（Coulomb / LuGre）
- 参数辨识

## 1.3 控制（Control）
- **位置控制层级**：PID、前馈、计算力矩
- **力 / 阻抗 / 导纳控制**：与环境交互的关键
- **轨迹生成**：多项式、最小 jerk、DMP
- **MPC**：线性 MPC、非线性 MPC、whole-body MPC（人形机器人核心）
- **WBC（Whole-Body Control）**：任务优先级、QP 求解
- **腿足机器人特有**：ZMP / CoM、MIT Cheetah convex MPC、Raibert 控制器

## 1.4 ROS2 工程化
- 核心概念：Node / Topic / Service / Action / Parameter / TF2 / DDS QoS
- 工具链：colcon、ros2 cli、rviz2、rqt、ros2_control
- 仿真集成：Gazebo / Ignition、Isaac Sim ROS2 Bridge
- 实时性：RT kernel、PREEMPT_RT、cyclic 性能调优
- 部署：launch / lifecycle node、容器化（Docker / docker-compose）

## 1.5 实践路径
1. URDF → RViz 可视化 → MoveIt2 规划
2. 写一个最简单的 PID 关节控制器
3. 在 Gazebo / Isaac 里复现一个机械臂的 pick-and-place
4. 真机驱动（如 UR / Franka / 国产臂）

## 推荐资源
- 《Modern Robotics》Lynch & Park（含 Coursera 课程 + Python 库）
- 《Robotics: Modelling, Planning and Control》Siciliano
- 《Underactuated Robotics》Russ Tedrake（MIT 6.832）
- Drake、Pinocchio、RBDL 这三个动力学库源码

## 代码分析待办
- [ ] MoveIt2 规划求解流程
- [ ] ros2_control 控制器加载机制
- [ ] Pinocchio 算法实现
- [ ] MIT Cheetah / Unitree 开源代码
