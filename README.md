# Vibe Coding Framework

一套面向人类开发者、主 agent 和 subagent 的 AI 协作开发框架。

它的目标是在保持 vibe coding 速度的同时，让项目仍然拥有清晰的业务真源、架构边界、任务范围、测试入口和冲突处理机制。适合用于从想法、原型到可维护系统的开发过程，尤其适合多人和多 agent 协作的项目。

## What It Solves

在 AI 辅助开发中，常见问题不是“代码写不出来”，而是：

- 业务语义在多轮实现中漂移。
- agent 为了局部通过测试，把逻辑塞进错误的模块。
- subagent 读取过多上下文，反而产生冲突或重复实现。
- 最初和用户聊清楚的需求只留在聊天上下文里，写文档时容易丢失或被压缩。
- 文档、测试、任务卡和代码边界不同步。
- 用户新要求和已有 contract 冲突时被静默覆盖。

这个框架用一组轻量但严格的文档和工作流解决这些问题：先由 AI 扮演产品经理和用户聊天，持续澄清需求；把已确认需求落盘成需求真源；再拆业务域、定 contract、写实现。每个任务只加载精准上下文；实现阶段按 module 队列一次只做一个业务域或一个明确业务切片。当前 module 验收测试通过后，才允许进入下一个 module。

Skill 创建的项目文档默认使用中文，方便人类团队阅读、维护和评审；文件路径、命令、API 名、schema 字段和代码标识符保持原样。

## Repository Contents

```text
.
├── vibe-coding-framework.md
└── vibe-coding-framework-skill/
    ├── SKILL.md
    └── references/
        ├── conflict-resolution.md
        ├── context-pack-template.md
        ├── discovery-log-template.md
        ├── discovery-questions.md
        ├── framework-files.md
        ├── implementation-loop.md
        ├── module-design-template.md
        ├── product-requirements-template.md
        ├── review-checklist.md
        └── task-card-template.md
```

- `vibe-coding-framework.md`: 完整的中文框架说明文档。
- `vibe-coding-framework-skill/`: Codex skill 版本，方便在 Codex 中直接复用这套协作流程。
- `references/`: 具体模板和执行参考，包括需求发现、产品需求、模块设计、任务卡、context pack、冲突处理和实现循环。

## Recommended Project Structure

框架推荐在项目中维护以下文件体系：

```text
AGENTS.md
docs/
  requirements/
    DISCOVERY_LOG.md
    PRODUCT_REQUIREMENTS.md
  design/
    PROJECT_DESIGN.md
    modules/
      <domain>.md
  ARCHITECTURE.md
  TASKS.md
  QUALITY.md
  DECISIONS.md
  context-packs/
    <task-or-domain>.md
```

这些文件分别承担 AI 执行纪律、需求访谈记录、产品需求真源、项目总设计、业务域设计、架构映射、任务拆分、质量规则、决策记录和精准上下文入口。

## Core Principles

- 需求发现先行：一开始不直接写设计文档，先让 AI 扮演产品经理，通过聊天澄清用户、目标、场景、边界、业务规则和验收标准。
- 本地落盘：已确认需求必须写入 `docs/requirements/PRODUCT_REQUIREMENTS.md`，重要访谈过程写入 `docs/requirements/DISCOVERY_LOG.md`，避免上下文压缩后丢失。
- 真源优先：重要业务语义先写进需求真源，再转写到设计文档，而不是只存在于聊天记录里。
- 按业务域拆分：模块设计按业务职责拆，不按技术层拆。
- 精准上下文：任务只读取必要文档，避免上下文爆炸。
- Contract 先行：跨域依赖先明确契约，再实现。
- 门禁顺序：缺少已确认需求、设计、架构、任务、质量或 context pack 时，不改产品代码。
- 顺序实现：实现顺序来自 `docs/TASKS.md` 中的 module 队列。
- 单域实现：一次只实现一个业务域或一个明确业务切片。
- 测试守门：当前 module 未跑通验收测试，不进入下一个 module。
- 冲突暂停：用户新要求和已有文档或 contract 冲突时，先暴露冲突并让用户选择。
- 中文文档：skill 生成的设计文档、任务卡、context pack、质量规则和交付说明默认写中文。

## Using The Codex Skill

将 `vibe-coding-framework-skill` 复制到 Codex skills 目录后，即可在 Codex 中通过 `vibe-coding-framework` skill 触发这套工作流。

示例用途：

- 为新项目生成 AGENTS、设计文档、架构文档和任务卡。
- 先以产品经理访谈模式澄清需求，并把确认过的需求保存到本地需求文档。
- 审查现有项目的 AI 协作边界。
- 为某个业务域补模块设计文档。
- 为 subagent 生成任务卡和 context pack。
- 在进入实现前检查文档、contract 和测试入口是否足够。

## When To Use

适合：

- 使用 Codex、Claude Code、Cursor 或其他 agent 编程工具的项目。
- 需要主 agent 和 subagent 协作的大型任务。
- 原型正在进入可维护工程阶段的项目。
- 业务规则复杂、容易被实现细节带偏的系统。

不适合：

- 一次性脚本。
- 没有长期维护预期的小实验。
- 不需要文档、测试或协作边界的极小项目。

## Language

框架主文档目前以中文编写。Skill 文件使用英文说明，以便 Codex 更稳定地识别触发条件和执行规则。
