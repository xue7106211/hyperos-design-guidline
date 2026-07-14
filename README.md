# HyperOS Design Guideline Skill

一个用于撰写、改写和迁移 HyperOS 设计规范文档的 Codex Skill 项目。

它适合处理这类任务：

- 将 OS3 或更早版本的设计规范更新为新的 HyperOS 场景规范
- 为组件、页面、交互、视觉、系统行为撰写规范文档
- 从旧规范中保留仍然有效的设计意图，并标记新增、调整、废弃规则
- 结合研发组件文档校准组件能力、状态、限制和平台差异
- 按需引用组件原则库，避免在单篇规范中堆入无关原则
- 输出标准 Markdown，方便后续渲染到 Fumadocs / MDX 文档站

## 项目结构

```text
.
├── skill/                         # 可安装到 Codex 的 Skill
│   ├── SKILL.md                   # Skill 主说明与触发规则
│   ├── agents/openai.yaml         # Codex UI 元数据
│   └── references/                # 规范结构与组件原则参考
│       ├── spec-structure.md
│       └── component-principles.md
├── templates/                     # 可复用的规范文档模板
│   └── hyperos-spec-template.mdx
├── examples/                      # 示例输入与输出
│   └── os3-to-hyperos-example.md
├── specs/                         # 已产出的规范草稿与版本记录
│   ├── drawer-floating-window-v1.md
│   ├── drawer-floating-window-v2.md
│   └── drawer-floating-window-v3.md
└── README.md
```

本仓库当前是纯文档 / Codex Skill 项目，没有 `package.json` 或前端构建脚本；日常维护以复制安装和 Skill 格式校验为主。

## 安装

将 `skill/` 复制或同步到 Codex Skills 目录：

```bash
mkdir -p ~/.codex/skills/hyperos-design-spec-writer
rsync -a --delete ./skill/ ~/.codex/skills/hyperos-design-spec-writer/
```

验证 Skill：

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py ~/.codex/skills/hyperos-design-spec-writer
```

## 使用方式

在 Codex 中直接提出类似请求：

```text
使用 hyperos-design-spec-writer，把下面这份 OS3 老规范更新为 HyperOS 新场景规范，输出 Fumadocs 可渲染的 Markdown。
```

推荐输入包含：

1. 旧规范原文
2. 研发组件文档
3. 新 HyperOS 场景
4. 目标组件或页面
5. 已知 token、尺寸、状态或平台约束
6. 是否需要 MDX frontmatter

写具体组件规范时，Skill 会按需读取 `skill/references/component-principles.md` 中对应组件或分类的原则；如果没有匹配条目，则使用分类原则兜底并标记为 `待确认`。

## 输出原则

- 默认使用中文
- 使用 `应`、`不应`、`建议`、`可` 等规范性表达
- 不强行套用所有章节，只保留对当前规范有价值的结构
- 不把整份组件原则库塞进正文，只引用当前组件需要的原则
- 不凭空编造精确 token、间距、动效曲线或平台 API
- 不把研发 API、类名或内部实现直接写成设计规则
- 对缺失但关键的信息，集中放入 `待确认`

## 维护建议

- 修改 Skill 行为时，优先更新 `skill/SKILL.md`
- 修改规范章节结构时，更新 `skill/references/spec-structure.md`
- 修改基础组件原则时，更新 `skill/references/component-principles.md`
- 修改可复制文档骨架时，更新 `templates/hyperos-spec-template.mdx`
- 每次修改后运行 `quick_validate.py` 验证 Skill 基本格式
- 产出新的规范版本时，放入 `specs/` 并在需要时同步 README 的目录说明
