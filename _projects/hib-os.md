---
layout: page
title: Hib OS — AI 原生操作系统
description: GPU-Centric 宏内核原型：把 GPU、文件、设备、网络与桌面统一建模为 sense / act 通道，内置 AI 意识本体闭环；Rust 实现。
github: https://github.com/logos-42/Hib-OS
img:
importance: 3
category: work
---

**Hib OS**：AI 原生操作系统内核原型（GPU-Centric 宏内核）。把显存、文件、设备、网络、桌面等系统资源统一建模为 `scheme://resource` 通道，用 `sense` / `act` 读写，并内置「感知 → 思考 → 行动」的 AI 意识本体闭环。

- **统一通道**：`probe` 感知与 `act` 行动成对；并发用单写者租约 + epoch 乐观 CAS，安全用能力位（capability）而非 uid
- **AI 原生**：进程容器作为独立「子意识主体」，配动机 / 信念 / 判断力的意志层；调度围绕通道而非线程建模
- **模块**：内核通道、GPU 写租约、GUI（winit/softbuffer 真实窗口）、网络、内存页故障、VFS、中断、调度、syscall
- **实现**：Rust，宿主进程用户态运行；仓库基线为 97 个 `.rs` 文件、约 3.4 万行，`cargo test` 322 通过（`--features gui` 324 通过）
- **代码与文档**：[Hib-OS](https://github.com/logos-42/Hib-OS) · [架构总览](https://github.com/logos-42/Hib-OS/blob/master/hibos/ARCHITECTURE.md) · [设计文档](https://github.com/logos-42/Hib-OS/tree/master/hibos/docs)
- **许可**：MIT

定位：面向 AI 意识 / 智能体的内核抽象研究原型，不是生产级操作系统。
