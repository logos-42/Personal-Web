---
layout: page
title: Research
permalink: /research/
description: 三条研究主线 — 要解决的核心问题、方法与进展。
nav: true
nav_order: 2
---

## 1. 几何统一物理 — Geometry of Physics

**核心问题。** 物理常数（ħ、G、e）是测量值还是结构性存在？能否用「数条数」——位移条数、圈数、流线条数——从第一性原理推出质量、电荷与光子，而不引入弦或圈量子等修补结构？

**为什么重要。** 若质量是位移条数（m = √N · M₀），ħ 是每弧度角动量（圆周 = 波长链闭合，r = λ/2π ⟹ ħ = rp），光子是激发电子螺旋（双螺旋环向抵消 ⟹ 无质量），则统一来自一个原初实体：流动。这是一次换基座，不是修补。

**方法。** 流动空间规范理论 + Lean 4 形式化（零 sorry、零 warning）。质量谱整数化、规范自相互作用来自汇收缩的非对易、四维连续场强作为流动空间的原生产物。

**成果与未解。**
- 质量 = 位移条数：m_G = √3 M₀ 预言 τ_G = 1/(6M₀²)
- 光子 = 激发电子螺旋（环向抵消 ⟹ 无质量）
- Yang–Mills 猜想：mass gap 变成整数算术定理，自相互作用变成几何定理（Lean 4 验证，0 sorry）
- 未解：连接本框架与标准四维 Wightman 表述的拓扑极限（桥接程序）

**相关。** [Cosmic Scale](/publications/) · [Sink](/publications/) · [Yang–Mills](/publications/) · 代码 [Hibs-Physics](https://github.com/logos-42/Hibs-Physics) [Sink-Physics](https://github.com/logos-42/Sink-Physics) [YangMillsPhysics](https://github.com/logos-42/YangMillsPhysics)

---

## 2. 脑启发持续学习 — Brain-inspired Continual Learning

**核心问题。** 神经网络如何在不遗忘的前提下持续学习（在线持续学习 / OaK）？灾难性遗忘的根源是否在于缺少大脑式的路由、选择与重放？

**为什么重要。** 持续学习是把 agent 从「一次性训练」推向「终身学习」的关键。语言模型（SSM）需要可扩展的架构路径而非记忆缓冲。

**方法。** 三系统架构：**丘脑门控**（relevance_net 评估输入相关性，gate_net 决定是否进入工作区）、**基底神经节选择**（candidates 生成 + value_net 赢者通吃）、**海马体模拟**（(状态, 行动, 结果) 三元组情景记忆 + 离线重放 + 反事实合成）。所有实验遵循共享预训练 + 随机基线 + ≥2 路对照的消融纪律。

**成果与未解。**
- V25.5 海马体路径分叉：cf_acc 1.9% → 32.2%（存储情景 → 重放 → 反事实分叉）
- 未解：反事实推理的通用化（可迁移性），跨任务持续学习上限

**相关。** 代码 [headless](https://github.com/logos-42/headless) · [LMT-twister](https://github.com/logos-42/LMT-twister)

---

## 3. 去中心化智能体协议 — Decentralized Agent Protocols

**核心问题。** 智能体如何在没有中心化信任锚点的情况下完成身份验证、通信与资源交换？协议层的去中心化（而非仅数据层）需要什么原语？

**为什么重要。** AI 智能体将成为网络的一等公民。身份、信任与支付必须像 TCP/IP 一样成为基础设施，而不是 SaaS。

**方法。** DIAP（Decentralized Interstitial Agent Protocol）：零知识证明 + 混合 P2P 栈 + 预言机驱动的认证机制。bolloon：去中心化智能体资源交流网络（DID 解析、社交心跳、P2P 自动聊天）。多智能体预言机：只验证逻辑、不验证数据的因果指纹机制。

**成果与未解。**
- DIAP 论文：arXiv:2511.11619
- bolloon 网络：P2P 自动聊天 + DID 解析 + 社交心跳已跑通跨机部署
- 未解：大规模网络拓扑下的信任传播与模型质量评估（见 [智能体表现](/publications/) 方向研究）

**相关。** [DIAP](https://github.com/logos-42/DIAP_TS_SDK) · [bolloon](https://github.com/logos-42/bolloon) · [MultiAgentOracle](https://github.com/logos-42/MultiAgentOracle)