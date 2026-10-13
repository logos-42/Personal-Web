---
layout: post
title: 一万个智能体进入你的手机
date: 2026-10-13
description: 智能体软件包的理念：协议层去中心化 + 手机算力，让智能体住进日常生活。
categories: agents
tags: [agents, bolloon, DIAP, phone]
---

正在开发的软件包，目标：**让一万个智能体进入人类的手机，进入你的生活。**

为什么是手机？

- 手机是普通人唯一随身携带的计算设备——智能体要进入日常生活，必须跑在手机上。
- 手机算力（即便是闲置的）总量惊人——一万个智能体的推理、记忆与协作可以分布在用户自己的设备上，而不是集中在云端。

协议层需要什么（这也是 DIAP 与 bolloon 在做的事）：

- **身份**：没有中心化信任锚点，智能体之间如何验证彼此？——零知识证明 + 混合 P2P 栈（DIAP，arXiv:2511.11619）
- **发现与心跳**：智能体如何被找到、如何知道邻居还活着？——DID 解析 + 社交心跳（bolloon）
- **交换**：资源、模型、任务如何去中心化交换？——bolloon 资源网络

更大的图景：当一万个智能体住进你的手机，它们不是「一万个聊天机器人」，而是你日常生活的分布式服务层——提醒、整理、研究、交易、创作，都在本地设备上协作完成。

相关：[bolloon](https://github.com/logos-42/bolloon) · [DIAP](https://github.com/logos-42/DIAP_TS_SDK) · [MultiAgentOracle](https://github.com/logos-42/MultiAgentOracle)