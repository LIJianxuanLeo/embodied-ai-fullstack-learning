# 第 5 章 · 让机器人自主学习：强化学习、模仿学习、VLA 与 World Model

> 当前研究最热的章节。核心问题：**怎么让机器人从经验/示教/视频里学到泛化的策略**。

## 5.1 强化学习（RL）
- **基础**：MDP、Bellman、Value/Policy iteration
- **On-policy**：REINFORCE、A2C、PPO（依然是主力）
- **Off-policy**：DQN、DDPG、SAC、TD3
- **Offline RL**：CQL、IQL、Decision Transformer
- **Sim-to-Real RL**：域随机化、Privileged learning（teacher-student）
- **HIL-SERL**：人在环 + 真机 RL，当前最实用范式之一
- **Residual RL**：在经典控制器上学习残差

## 5.2 模仿学习（IL）
- BC（Behavior Cloning）及其失败模式（compounding error）
- DAgger、HG-DAgger
- 逆强化学习（IRL）、AIRL、GAIL
- **Action Chunking Transformer（ACT）**：ALOHA 框架
- **Diffusion Policy**：visuomotor 控制新范式
- **Flow Matching Policy**：π0 系列采用
- Implicit BC、Energy-based Policy

## 5.3 VLA（Vision-Language-Action）
- 起点：RT-1、RT-2、RT-X 数据集
- **OpenVLA**：开源里程碑
- **π0 / π0.5**：flow matching + 大规模数据
- **GR-2 / RDT-1B / Octo / CogACT**
- 训练范式：预训练 + 微调、co-training、多任务
- 关键设计：动作 tokenization、动作分块、推理速度

## 5.4 World Model
- **Dreamer 家族**：DreamerV2/V3、在 RL 中规划
- **视频生成作为世界模型**：Sora、Genie 2、UniSim
- **机器人专用 WM**：DayDreamer、TWM、1X World Model
- 用途：（a）数据增广 （b）模型预测控制 （c）评测 policy

## 5.5 数据
- 真机示教：teleoperation（VR / 主从 / ALOHA / GELLO）
- 仿真生成：RoboCasa、RoboGen
- 人类视频：Ego4D、HOI 数据
- 大规模数据集：Open-X Embodiment、DROID、RH20T
- 数据飞轮：自动评估 → 失败案例标注 → 再训练

## 5.6 关键开放问题
- 泛化（新物体 / 新场景 / 新任务）
- 长程任务
- 推理速度（高频控制 vs 大模型）
- 安全与可靠性
- 评测标准（在真实世界上）

## 5.7 实践路径
1. PPO 在 Isaac Lab / IsaacGym 训一个 locomotion 或抓取
2. 复现 Diffusion Policy（LeRobot 实现）
3. 在自己的小数据上微调 OpenVLA 或 π0
4. 用 Dreamer 在简单环境训一个世界模型

## 代码分析待办
- [ ] LeRobot 仓库整体架构
- [ ] OpenVLA 训练 / 推理流程
- [ ] Diffusion Policy 代码细节
- [ ] HIL-SERL 真机 RL 工程实现
- [ ] DreamerV3 实现
