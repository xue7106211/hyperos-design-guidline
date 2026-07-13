# HyperOS 设计规范文档结构参考

Use this as a menu, not a mandatory checklist. Select sections according to the user's artifact and scenario.

## 概述

Explain what the component, pattern, or rule is; what user problem it solves; and where it appears in HyperOS.

Template:

```markdown
## 概述

本规范定义「对象名称」在「场景」中的使用方式，覆盖结构、状态、交互、视觉与实现约束，帮助设计、研发与 QA 在 HyperOS 场景下保持一致。
```

## 适用范围

Define where the spec applies and where it does not. Include platform, device, app module, component family, or screen mode when known.

```markdown
| 范围 | 说明 |
| --- | --- |
| 适用 |  |
| 不适用 |  |
| 依赖 |  |
```

## 设计原则

List 3-5 principles. Each principle should explain a decision rule, not a slogan.

```markdown
| 原则 | 说明 |
| --- | --- |
| 稳定优先 | 保持关键操作位置和反馈一致，降低跨场景迁移成本。 |
```

## 结构与组成

Describe anatomy: container, icon, label, value, affordance, helper text, status indicator, action area, etc. Use this section to map old OS3 naming to new HyperOS naming if needed.

```markdown
| 元素 | 必需 | 说明 |
| --- | --- | --- |
| 容器 | 是 | 承载主体内容和交互热区。 |
```

## 布局规则

Document hierarchy, alignment, spacing, density, truncation, and responsive behavior. Use token placeholders if exact values are unknown.

```markdown
| 项目 | 规则 |
| --- | --- |
| 对齐 | 主文本与图标视觉中心对齐。 |
| 间距 | 使用 `{space.*}` token；具体值待接入设计系统。 |
```

## 状态与变体

Use a matrix for default, pressed, focused, selected, disabled, loading, error, success, expanded, collapsed, etc. Include only relevant states.

```markdown
| 状态 | 触发条件 | 视觉变化 | 行为规则 |
| --- | --- | --- | --- |
| 默认 | 初始可用 | 使用默认容器与文字层级 | 可点击或可聚焦 |
```

## 交互行为

Describe input methods, gestures, tap/click area, keyboard/focus, feedback, transitions, and conflict resolution.

```markdown
| 行为 | 规则 |
| --- | --- |
| 点击 | 命中热区后触发主操作，并给出即时反馈。 |
| 长按 | 仅在场景需要二级操作时启用。 |
```

## 内容与文案

Clarify label length, terminology, empty/error messages, localization, units, and dynamic content.

## 视觉规范

Cover color roles, typography roles, elevation, shape, icons, opacity, and contrast. Do not invent final token names if missing.

```markdown
| 属性 | Token / 规则 | 备注 |
| --- | --- | --- |
| 主文本 | `{color.text.primary}` | 待与 HyperOS token 对齐 |
```

## 动效规范

Define when motion exists, what changes, duration/easing if known, and when to reduce motion.

## 无障碍与可用性

Include focus order, semantic role, screen reader label, contrast, touch target, keyboard operation, and reduced-motion behavior.

## 适配与响应式

Use for phone/tablet/foldable/desktop, portrait/landscape, compact/regular density, and dark mode.

## 边界场景

Document empty, loading, offline, permission denied, long text, extreme values, nested usage, and conflicting states.

## 实现说明

Give engineering-facing constraints without over-specifying framework details unless provided.

```markdown
| 项目 | 说明 |
| --- | --- |
| 状态来源 | 由业务状态控制；组件不应自行推断 selected 与 disabled 的冲突。 |
```

## QA 检查清单

Write verifiable checks.

```markdown
- [ ] 默认、按下、禁用、选中等状态与规范一致。
- [ ] 长文本、空数据、异常数据不会破坏布局。
- [ ] 深色模式和浅色模式均满足可读性要求。
```

## 从 OS3 迁移

Use when updating legacy specs.

```markdown
| OS3 规则 | HyperOS 处理 | 原因 |
| --- | --- | --- |
|  | 保留 / 调整 / 新增 / 废弃 |  |
```

## 待确认

Collect unresolved inputs that should be confirmed by design system, product, engineering, or QA owners.
