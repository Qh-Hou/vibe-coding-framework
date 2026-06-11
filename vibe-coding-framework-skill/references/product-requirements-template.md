# Product Requirements Template

Use this after or during product-manager discovery. This file is the confirmed requirements source of truth that later design docs, module docs, task cards, tests, and context packs should reference.

Project documents generated from this template should be written in Chinese by default, while keeping file paths, commands, code identifiers, and contract names unchanged.

```markdown
# 产品需求说明

## 需求状态

- 状态：<草稿/已确认/部分确认>
- 最近更新：<YYYY-MM-DD>
- 来源：`docs/requirements/DISCOVERY_LOG.md` <relevant rounds>

## 产品目标

- <goal>

## 非目标

- <non-goal>

## 用户、角色和调用方

| 角色 | 目标 | 权限或限制 |
|---|---|---|
| <role> | <goal> | <constraint> |

## 核心场景

### <Scenario Name>

- 触发条件：
- 用户意图：
- 主要流程：
- 成功结果：
- 失败或异常：

## 功能需求

| ID | 需求 | 优先级 | 验收标准 |
|---|---|---|---|
| FR-001 | <requirement> | <P0/P1/P2> | <acceptance criteria> |

## 非功能需求

| ID | 需求 | 验收标准 |
|---|---|---|
| NFR-001 | <requirement> | <acceptance criteria> |

## 业务规则

| ID | 规则 | 影响范围 |
|---|---|---|
| BR-001 | <rule> | <domain or scenario> |

## 边界和约束

- <constraint>

## 开放问题

- <question and why it matters>

## 假设

- <assumption and revisit condition>

## 需求变更记录

| 日期 | 变更 | 原因 | 影响 |
|---|---|---|---|
| <YYYY-MM-DD> | <change> | <reason> | <impact> |
```

Do not start full project design until this file contains enough confirmed requirements, or explicit assumptions, to support the design.
