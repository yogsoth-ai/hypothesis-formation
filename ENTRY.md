---
name: hypothesis-formation
description: "Goal-Driven Hypothesis & Research Question Formation Engine — gap prioritization, hypothesis formulation, and research question formation"
version: 1.0.0
category: hypothesis-formation
type: entry
dependencies:
  skills:
    - web-browsing
    - literature-engine
    - context-management
    - subagent-spawning
  mcp:
    - brave-search
    - apify
    - alphaxiv
    - semantic-scholar
---

# Hypothesis Formation

Goal-Driven Hypothesis & Research Question Formation Engine — 将上游的 gaps 和 insights 转化为可测试的假设和精确的研究问题。

## Positioning

**前置条件**:
- north-star-crystallization 已完成（研究意图明确）
- 至少一个上游 repo 产出了 gaps/insights（knowledge-acquisition、deep-insight、或用户手动提供）

**执行边界**:
- 止步于"形成可测试的假设和研究问题" — 不做 ideation（方案生成）、不做实验设计
- 不做 gap 发现（那是上游的事），只做 gap 排序和转化
- 产出是结构化的假设和研究问题文档，不是解决方案

## Campaigns

| Campaign | 核心问题 | 输入 | 产出 |
|----------|---------|------|------|
| gap-prioritization | "哪些 gap 最值得攻击？" | 上游 gaps | 排序后的 gap 优先级列表 + 攻击建议 |
| hypothesis-formulation | "如何将 insight 转化为可测试假设？" | gaps + insights + tensions | 结构化假设 + falsifiability criteria |
| research-question | "如何将假设细化为精确研究问题？" | 假设 + 领域约束 | 框架化的研究问题 + scope + success criteria |

## Campaign Routing

| Signal | Campaign |
|--------|----------|
| gap 排序、优先级、哪个值得做、PiCMe、多维评分、portfolio | → gap-prioritization |
| 假设生成、理论推导、可证伪、If-then、变量、机制、competing hypothesis | → hypothesis-formulation |
| 研究问题、PICO、SPIDER、FINER、scope、子问题分解、success criteria | → research-question |

## Multi-Campaign Orchestration

三个 campaign 完全灵活组合，CC 自主决定用几个、什么顺序：
- 典型串行: gap-prioritization → hypothesis-formulation → research-question
- 跳过: hypothesis-formulation → research-question（已有明确假设）
- 单独: gap-prioritization only（只需排序）
- 反向: research-question → hypothesis-formulation（先有问题框架，再填充假设）
- 并行: hypothesis-formulation ∥ research-question（假设和问题同步迭代）

## Context Management

- **Campaign start**: 调用 context-init（加载/创建 campaign context file）
- **每个 strategy 完成后**: 调用 context-checkpoint（硬性约束，不可跳过）
- **一个 context file per campaign**: 所有 strategy 产出累积在单个 campaign-scoped file

## Design Philosophy

兵法书模式 — CC 读完后内化原则，面对具体研究任务自行构建打法。

**硬约束仅四种**:
1. Budget Gate — 量化地板，不达标不能退出
2. Minimum Yield — 每次执行的最低产出要求
3. HARD-GATE — 前置条件检查，不满足不能开始
4. context-checkpoint — strategy 完成后必须触发

**CC 有权自主决策**:
- 简化 tactic 为只使用一批 SOP
- 决定迭代次数
- 决定 campaign 组合顺序
- 跳过不适用的 strategy
