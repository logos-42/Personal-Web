---
layout: page
title: Research
permalink: /research/
description: 三条研究主线 — 要解决的核心问题、方法与进展。Three lines of research — questions, methods, progress.
nav: true
nav_order: 2
---

<div data-lang="zh" markdown="1">

## 1. 可控核聚变 — Controlled Fusion

**核心问题。** 如何把聚变电磁设计从「手工迭代」变成「算法驱动的可学习闭环」？磁场位形、线圈拓扑与等离子体动力学之间如何自动搜索、评分与记录？

**为什么重要。** 受控聚变是人类能源的终局问题之一。工程侧的关键瓶颈之一是电磁线圈设计——当前依赖专家经验迭代，周期长、不可复用。

**方法。** HUSHFUSION Forge：自动搜索 → 评分 → 记录 → 学习（Go 主栈 + 独立 Python 复核层）。fusion-sim：聚变数字仿真工作台（TORAX / Gym-TORAX 跑通；gym-μ-FRC = μ 动力学 × FRC 窗口 × Gymnasium 环境，含门禁）。

**成果与未解。**
- Forge 闭环跑通：电磁线圈设计的可学习回路（开源）
- fusion-sim 工作台：TORAX / Gym-TORAX 仿真 + μ-FRC 环境
- 未解：线圈-等离子体联合优化的收敛性，FRC 窗口的实验验证

**相关。** [hushfusion-forge](https://github.com/logos-42/hushfusion-forge) · [fusion-sim](https://github.com/logos-42/fusion-sim) · [HushFusion](https://github.com/logos-42/HushFusion)

---

## 2. 智能体研究 — Agent Research

**核心问题。** 智能体如何在没有中心化信任锚点的情况下完成身份验证、通信与资源交换？当一万个智能体住进普通人的手机，协议层需要什么原语？

**为什么重要。** AI 智能体将成为网络的一等公民。身份、信任与交换必须像 TCP/IP 一样成为基础设施——并且要能跑在手机上，进入日常生活。

**方法。** DIAP（Decentralized Interstitial Agent Protocol）：零知识证明 + 混合 P2P 栈 + 预言机驱动认证。bolloon：去中心化智能体资源交流网络（DID 解析、社交心跳、P2P 自动聊天）。多智能体预言机：只验证逻辑、不验证数据的因果指纹机制。以及面向手机的智能体软件包——让一万个智能体进入你的手机。

**成果与未解。**
- DIAP 论文：arXiv:2511.11619
- bolloon：P2P 自动聊天 + DID 解析 + 社交心跳，跨机部署跑通
- 手机智能体软件包：开发中
- 未解：大规模拓扑下的信任传播与模型质量评估

**相关。** [DIAP](https://github.com/logos-42/DIAP_TS_SDK) · [bolloon](https://github.com/logos-42/bolloon) · [MultiAgentOracle](https://github.com/logos-42/MultiAgentOracle)

---

## 3. 数学推动 — Advancing Mathematics

**核心问题。** 物理常数（ħ、G、e）是测量值还是结构性存在？能否用「数条数」——位移条数、圈数、流线条数——从第一性原理推出质量、电荷与光子，并把每一条定理交给机器验证？

**为什么重要。** 若质量是位移条数（m = √N · M₀），ħ 是每弧度角动量（圆周 = 波长链闭合，r = λ/2π ⟹ ħ = rp），光子是激发电子螺旋（双螺旋环向抵消 ⟹ 无质量），统一就来自一个原初实体：流动。这是一次换基座，不是修补。而 Lean 4 形式化让「证明」不再依赖叙述，而是机器可核验的事实。

**方法。** 流动空间规范理论 + Lean 4 形式化（零 sorry、零 warning）。质量谱整数化、规范自相互作用来自汇收缩的非对易、四维连续场强作为流动空间的原生产物。NODS：新对象 = 对现有系统的最小一致扩张。

**成果与未解。**
- 质量 = 位移条数：m_G = √3 M₀ 预言 τ_G = 1/(6M₀²)
- 光子 = 激发电子螺旋（环向抵消 ⟹ 无质量）
- Yang–Mills：mass gap 成为整数算术定理，自相互作用成为几何定理（Lean 4 验证，0 sorry）
- NODS：开方 ≠ 幂，Radical.lean 零 sorry 接入主链
- 未解：连接本框架与标准四维 Wightman 表述的拓扑极限（桥接程序）

**相关。** [Cosmic Scale](/publications/) · [Sink](/publications/) · [Yang–Mills](/publications/) · 代码 [Hibs-Physics](https://github.com/logos-42/Hibs-Physics) [Sink-Physics](https://github.com/logos-42/Sink-Physics) [YangMillsPhysics](https://github.com/logos-42/YangMillsPhysics) [NODS](https://github.com/logos-42/NODS)

---

## 其他研究 — Other Research

**持力学性模型（force-sustaining models）。** 对力学性质如何在模型中保持与延续的研究。

</div>

<div data-lang="en" markdown="1">

## 1. Controlled Fusion

**The question.** How do we turn electromagnetic design for fusion from hand-iteration into an algorithm-driven learning loop? How do field configurations, coil topologies, and plasma dynamics get searched, scored, and recorded automatically?

**Why it matters.** Controlled fusion is one of the endgame questions of human energy. On the engineering side, electromagnetic coil design is a key bottleneck — currently expert-driven, slow, and not reusable.

**Method.** HUSHFUSION Forge: search → score → record → learn (Go core + independent Python re-check layer). fusion-sim: a digital fusion simulation workbench (TORAX / Gym-TORAX running; gym-μ-FRC = μ dynamics × FRC window × Gymnasium environment, with gates).

**Progress & open problems.**
- Forge loop running: a learnable loop for coil design (open source)
- fusion-sim workbench: TORAX / Gym-TORAX simulation + μ-FRC environment
- Open: convergence of coil–plasma co-optimization; experimental validation of the FRC window

**Related.** [hushfusion-forge](https://github.com/logos-42/hushfusion-forge) · [fusion-sim](https://github.com/logos-42/fusion-sim) · [HushFusion](https://github.com/logos-42/HushFusion)

---

## 2. Agent Research

**The question.** How do agents verify identity, communicate, and exchange resources without a centralized trust anchor? When ten thousand agents live in ordinary people's phones, what primitives does the protocol layer need?

**Why it matters.** AI agents will become first-class citizens of the network. Identity, trust, and exchange must be infrastructure like TCP/IP — and they must run on phones, entering daily life.

**Method.** DIAP (Decentralized Interstitial Agent Protocol): zero-knowledge proofs + hybrid P2P stack + oracle-driven authentication. bolloon: a decentralized agent resource network (DID resolution, social heartbeat, P2P auto-chat). Multi-agent oracle: causal-fingerprint verification of agent logic, not data. Plus a phone-oriented agent software package — ten thousand agents into your phone.

**Progress & open problems.**
- DIAP paper: arXiv:2511.11619
- bolloon: P2P auto-chat + DID resolution + social heartbeat, cross-machine deployment working
- Phone agent package: in development
- Open: trust propagation and model-quality evaluation at scale

**Related.** [DIAP](https://github.com/logos-42/DIAP_TS_SDK) · [bolloon](https://github.com/logos-42/bolloon) · [MultiAgentOracle](https://github.com/logos-42/MultiAgentOracle)

---

## 3. Advancing Mathematics

**The question.** Are the physical constants (ħ, G, e) measured values or structural existences? Can counting — displacement lines, turns, flow lines — derive mass, charge, and the photon from first principles, and hand every theorem to a machine to check?

**Why it matters.** If mass is displacement lines (m = √N · M₀), ħ is angular momentum per radian (the circle is a closed wavelength chain: r = λ/2π ⟹ ħ = rp), and the photon is an excited electron helix (helical cancellation ⟹ massless), then unification comes from one primitive: flow. This is a change of foundation, not a patch. And Lean 4 formalization makes "proof" a machine-verifiable fact rather than a narrative.

**Method.** Flowing-space gauge theory + Lean 4 formalization (zero sorry, zero warning). Integer mass spectra, gauge self-interaction from noncommuting sink contractions, and the 4D continuous field strength native to flowing space. NODS: a new object = a minimal consistent extension of an existing system.

**Progress & open problems.**
- Mass = displacement lines: m_G = √3 M₀ predicts τ_G = 1/(6M₀²)
- Photon = excited electron helix (helical cancellation ⟹ massless)
- Yang–Mills: the mass gap becomes a theorem of integer arithmetic, self-interaction a theorem of geometry (Lean 4, 0 sorry)
- NODS: radical ≠ power, Radical.lean zero-sorry into the main chain
- Open: the topological limit bridging this framework to the standard 4D Wightman formulation

**Related.** [Cosmic Scale](/publications/) · [Sink](/publications/) · [Yang–Mills](/publications/) · Code [Hibs-Physics](https://github.com/logos-42/Hibs-Physics) [Sink-Physics](https://github.com/logos-42/Sink-Physics) [YangMillsPhysics](https://github.com/logos-42/YangMillsPhysics) [NODS](https://github.com/logos-42/NODS)

---

## Other Research

**Force-sustaining models (持力学性模型).** On how mechanical properties are sustained and carried within models.

</div>