# Discovery Log Template

Use this during product-manager discovery. Write generated project documents in Chinese by default, while keeping file paths, commands, code identifiers, and contract names unchanged.

Append one entry per meaningful discovery round. Keep it concise; this file preserves why requirements were understood a certain way, not a full chat transcript.

```markdown
# 需求发现日志

## <YYYY-MM-DD> / 第 <N> 轮

### 用户原始意图摘要

- <用户想解决的问题或表达的偏好>

### Agent 理解复述

- <agent 当前理解>

### 本轮已确认

- <confirmed requirement>

### 本轮未确认

- <open question>

### 冲突或取舍

- <conflict or tradeoff>

### 下一轮优先问题

- <1-3 high-impact questions>
```

Move stable confirmed requirements into `docs/requirements/PRODUCT_REQUIREMENTS.md` instead of leaving them only in this log.
