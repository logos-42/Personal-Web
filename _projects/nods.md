---
layout: page
title: NODS — New Object Discovery System
description: Lean 4 + Mathlib 形式化「通过最小一致扩张发现新数学对象」——开方 ≠ 幂的证明。
github: https://github.com/logos-42/NODS
img:
importance: 4
category: work
---

**NODS**（New Object Discovery System）：把「发现新对象」本身变成可形式化的方法论——新对象 = 对现有系统的最小一致扩张（minimal consistent extension）。

- **核心证明**：开方与幂不可混淆——`Radical.lean` 零 sorry 接入主链（Lean 4 + Mathlib）
- **论文**：*The radical as a forced structure: how to split powers from radicals*（[aiXiv:260907.000001](https://aixiv.science/papers/aixiv.260907.000001)）——「被逼出的真实结构」中英双版
- **代码**：[NODS](https://github.com/logos-42/NODS)

可迁移方法论：任何「发现新东西」的场合 = 现有系统 + 一条被逼出的最小扩张。