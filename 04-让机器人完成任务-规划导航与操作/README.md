# 第 4 章 · 让机器人完成任务：规划、导航与操作

> 把"动起来 + 看见 + 知道位置"组合成"完成一个任务"。本章分三层：任务规划 → 运动规划 → 执行。

## 4.1 任务规划（Task Planning）
- 经典：PDDL、HTN
- 行为树（Behavior Tree）：BehaviorTree.CPP、py_trees
- 状态机：SMACH / Yasmin
- **LLM Planner**：SayCan、Code-as-Policies、Inner Monologue、VoxPoser
- 长程任务分解：ReAct、Tree of Thoughts、Reflexion 在机器人中的应用

## 4.2 路径与运动规划
- 离散搜索：A*、Dijkstra、Hybrid A*（车辆）
- 采样：RRT、RRT*、BIT*、Informed RRT*
- 优化：CHOMP、TrajOpt、STOMP
- 约束规划：碰撞约束、动力学约束、可微仿真梯度
- OMPL / MoveIt2 工程实践

## 4.3 移动机器人导航
- ROS2 Nav2 全栈：BT navigator、planner server、controller server、recovery
- Costmap：layered costmap、语义层
- 局部规划：DWA、TEB、MPPI
- 社交导航、人群避让

## 4.4 操作（Manipulation）
- 抓取：解析抓取（GraspIt!）、学习抓取（GraspNet-1Billion、AnyGrasp）
- **6D 姿态 + 抓取**：FoundationPose → 抓取规划
- 装配 / 插孔：阻抗控制 + 力反馈
- 灵巧手：高自由度控制、Allegro / Shadow / Inspire
- 双臂协同：约束、协同 IK
- 移动操作（Mobile Manipulation）：HSR、Spot Arm、人形

## 4.5 任务/运动联合规划（TAMP）
- 离散动作 + 连续约束的耦合搜索
- PDDLStream、Logic-Geometric Programming
- LLM + 经典规划器混合

## 4.6 实践路径
1. ROS2 Nav2 在 Gazebo 跑通导航
2. MoveIt2 + 一个简单抓取
3. 用 LLM（本地或 API）做高层任务分解，分发到 BT 执行
4. 复现 VoxPoser / Code-as-Policies 的一个子任务

## 代码分析待办
- [ ] Nav2 BT 与 plugin 加载
- [ ] OMPL 求解器内部
- [ ] AnyGrasp / GraspNet 推理
- [ ] VoxPoser 代码结构
