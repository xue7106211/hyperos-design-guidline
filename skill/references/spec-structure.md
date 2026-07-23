# HyperOS 设计规范文档结构参考

Default component skeleton: overview → types & structure → interaction/states → visual specs (material + component metrics) → multi-device.

Do **not** put process meta in the body. **Feishu-friendly newlines (default):** no blank line between a heading and its content; no consecutive blank lines.

## 标题编号规则

一级章节使用中文数字编号，如 `## 一、概述`；二级章节使用阿拉伯数字编号，如 `### 4.1、材质`。

## 一、概述

定义、用户问题、出现场景。已确认的组件原则写在概述内（紧随定义），不要单独成「核心原则」章。

```markdown
## 一、概述
「对象名称」是一种用于「用户任务」的「组件/模式」。
- **原则词条**：规范落点。
```

## 二、类型与结构

合并类型体系、结构解剖与必要变体差异。先类型，后组成，再变体差异。

```markdown
## 二、类型与结构
| 类型 | 用途 | 典型场景 | 关键约束 |
| --- | --- | --- | --- |
|  |  |  |  |
结构组成：
| 元素 | 必需 | 说明 |
| --- | --- | --- |
| 容器 | 是 | 承载主体内容和交互热区。 |
```

## 三、交互与状态

状态矩阵、手势、热区冲突与反馈。

```markdown
## 三、交互与状态
| 状态 | 触发条件 | 视觉变化 | 行为规则 |
| --- | --- | --- | --- |
| 默认 | 初始可用 | 使用默认容器与文字层级 | 可点击或可聚焦 |
```

## 四、视觉规格

### 4.1、材质

色彩、表面、文本色阶、选中/禁用等视觉材质与 token，不堆尺寸表。

```markdown
### 4.1、材质
| 属性 | Token / 规则 | 备注 |
| --- | --- | --- |
| 主文本 | `{color.text.primary}` |  |
```

### 4.2、组件规格

尺寸、间距、圆角、热区、左右元素档位与布局度量。

```markdown
### 4.2、组件规格
| 属性 | 规则 | 备注 |
| --- | --- | --- |
| 行高 |  |  |
```

## 五、多端设计指南

手机、折叠屏、平板等终端差异。

```markdown
## 五、多端设计指南
| 终端 | 规则 |
| --- | --- |
| 手机 |  |
| 折叠屏 |  |
| 平板 |  |
```

## 默认不输出的章节

Unless the user explicitly asks to add them back, omit: 核心原则（独立成章）、变体详解（独立成章）、使用指南、内容与文案、动效规范、QA、从 OS3 迁移、参照来源、更改日志、待确认。
