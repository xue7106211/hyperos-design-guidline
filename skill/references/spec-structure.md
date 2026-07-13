# HyperOS 设计规范文档结构参考

Use this as a menu, not a mandatory checklist. Select sections according to the user's artifact and scenario. For component specs, prefer the Button-style structure: first explain definition and role, then principles, type system, interaction states, usage guidance, per-variant rules, specifications, responsive behavior, multi-device guidance, implementation/QA, and changelog.


## 标题编号规则

规范正文一级章节使用中文数字编号，如 `## 一、概述`；二级章节使用阿拉伯数字编号，如 `### 3.1、类型选择规则`。章节编号应随最终文档结构连续调整，删除章节时同步重排编号。

## 概述

Explain what the component, pattern, or rule is; what user problem it solves; and where it appears in HyperOS. For component specs, keep the overview focused on definition, user problem, and where it appears; avoid duplicating later structure/type sections.

Template:

```markdown
## 概述

「对象名称」是一种用于「用户任务」的「组件/模式」。它通过「关键能力」帮助用户在 HyperOS 中完成「目标」。

```

## 核心原则

List the component's confirmed principles. For base components, the principles are already defined by the component principle library: quote the exact principle labels instead of inventing new ones. You may add a short "规范落点" or explanation under each principle, but do not rename, merge, split, or replace confirmed principle terms.

```markdown
## 核心原则

- **原则词条 1**：引用已确认原则原文；补充本规范中的落点。
- **原则词条 2**：引用已确认原则原文；补充本规范中的落点。
- **原则词条 3**：引用已确认原则原文；补充本规范中的落点。
```

## 类型

Use this for emphasis levels, component families, variants, and decision matrices. It should answer: which type should be used in which priority and scenario?

```markdown
## 类型

| 类型 | 用途 | 典型场景 | 关键约束 |
| --- | --- | --- | --- | --- |
|  | 高 / 中 / 低 或 模态 / 非模态 |  |  |  |
```

Optional subsections:

```markdown
### 层级

### 类型

### 类型选择规则
```

## 结构与组成

Describe anatomy: container, affordance, title, content, action area, drag handle, mask, icon, label, value, helper text, status indicator, etc. Use this section to map old OS3 naming to new HyperOS naming if needed.

```markdown
## 结构与组成

| 元素 | 必需 | 说明 |
| --- | --- | --- |
| 容器 | 是 | 承载主体内容和交互热区。 |
```

## 交互与状态

Describe input methods, gestures, state transitions, tap/click area, keyboard/focus, feedback, and conflict resolution. Use state matrices for default, hovered, pressed, focused, selected, disabled, loading, error, expanded, collapsed, hidden, etc.

```markdown
## 交互与状态

| 状态 | 触发条件 | 视觉变化 | 行为规则 |
| --- | --- | --- | --- |
| 默认 | 初始可用 | 使用默认容器与文字层级 | 可点击或可聚焦 |
```

Optional subsections:

```markdown
### 状态矩阵

### 手势与输入

### 状态切换规则
```

## 使用指南

Document practical guidance with Do / Don't, common scenarios, and component selection rules. This section should help designers avoid misuse.

```markdown
## 使用指南

### 应做（Do）

- 应在「场景」中使用「类型」，因为「原因」。

### 不应做（Don't）

- 不应在「场景」中使用「类型」，因为「风险」。
```

## 变体详解

Use this when a component has multiple variants. Each variant should include purpose, common scenarios, layout, content rules, and constraints. Do not force this section for simple one-variant patterns.

```markdown
## 变体详解

### 变体名称

说明此变体解决什么问题，何时使用。

#### 常见使用场景

#### 布局

#### 内容规则

#### 约束
```

## 规格

Document color, typography, layout, size, spacing, radius, elevation, hit area, and visual tokens. Do not invent final token names if missing; use placeholders.

```markdown
## 规格

### 色彩

| 属性 | Token / 规则 | 备注 |
| --- | --- | --- |
| 主文本 | `{color.text.primary}` | 待与 HyperOS token 对齐 |

### 布局

### 尺寸

### 间距

### 圆角

### 热区
```

## 内容与文案

Clarify label length, terminology, empty/error messages, localization, units, truncation, and dynamic content. If content rules are better placed inside each variant, keep this section short or omit it.

## 动效规范

Define when motion exists, what changes, duration/easing if known, state transitions, gesture follow, and reduced-motion behavior.

## 多端设计指南

Use for width/height behavior, parent container changes, orientation, keyboard, split screen, compact/regular density, layout rearrangement, and terminal-specific guidance such as phone, foldable, tablet, wearable, desktop, car, TV, or other terminals. Focus on interaction mode, viewing distance, input device, and platform constraints.

```markdown
## 十一、多端设计指南

### 11.1、高度规则

### 11.2、宽度规则

### 11.3、位置规则

### 11.4、多项排布

### 11.5、多端规则

| 终端 | 规则 |
| --- | --- |
| 手机 |  |
| 折叠屏 |  |
| 平板 |  |
```

## QA 检查清单

Write verifiable checks for type selection, state, layout, responsive behavior, content, accessibility, and implementation constraints.

```markdown
## QA 检查清单

- [ ] 默认、按下、禁用、选中等状态与规范一致。
- [ ] 长文本、空数据、异常数据不会破坏布局。
- [ ] 深色模式和浅色模式均满足可读性要求。
```

## 从 OS3 迁移

Use when updating legacy specs.

```markdown
## 从 OS3 迁移

| OS3 规则 | HyperOS 处理 | 原因 |
| --- | --- | --- |
|  | 保留 / 调整 / 新增 / 废弃 |  |
```

## 待确认

Collect unresolved inputs that should be confirmed by design system, product, engineering, or QA owners.

## 更改日志

Use for versioned specs. Keep entries short and traceable.

```markdown
## 更改日志

| 版本 | 日期 | 变更 |
| --- | --- | --- |
| V1 | YYYY-MM-DD | 初版。 |
```
