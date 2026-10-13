---
layout: post
title: Fusion 项目 — 可控核聚变的工程闭环
date: 2026-10-13
description: HUSHFUSION Forge：电磁线圈设计的自动搜索 / 评分 / 记录 / 学习闭环；fusion-sim 仿真工作台。
categories: fusion
tags: [fusion, forge, simulation]
---

可控核聚变 Fusion 项目进行中。两条腿走路：

**1. HUSHFUSION Forge — 电磁线圈设计闭环**

聚变装置的核心工程瓶颈之一是电磁线圈设计。传统做法依赖专家经验手工迭代——周期长、不可复用。Forge 把它变成一个可学习的闭环：

- **自动搜索**：线圈拓扑与位形参数空间
- **评分**：物理与工程约束下的目标函数
- **记录**：每次尝试进数据库，经验可复用
- **学习**：从历史评分中迭代改进搜索策略

技术栈：Go 主栈 + 独立 Python 复核层（双实现互验，防止单栈偏差）。

**2. fusion-sim — 聚变数字仿真工作台**

- TORAX / Gym-TORAX 跑通（成熟的聚变仿真框架接入）
- gym-μ-FRC：μ 动力学 × FRC（场反位形）窗口 × Gymnasium 环境——把 FRC 物理做成可强化学习的仿真环境，含门禁验证

**当前状态。** Forge 闭环已跑通并开源；μ-FRC 环境已就绪。下一步：线圈-等离子体联合优化的收敛性验证。

相关仓库：[hushfusion-forge](https://github.com/logos-42/hushfusion-forge) · [fusion-sim](https://github.com/logos-42/fusion-sim) · [HushFusion](https://github.com/logos-42/HushFusion)