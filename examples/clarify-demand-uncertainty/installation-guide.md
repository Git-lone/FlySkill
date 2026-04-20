# clarify-demand-uncertainty Skill 安装和使用指南

## 📦 安装

### 方式 1：项目级安装（推荐）

适用于团队协作项目，确保所有成员使用相同的 Skill。

```bash
# 在项目根目录执行
mkdir -p .claude/skills
cp -r skills/clarify-demand-uncertainty .claude/skills/

# 将 .claude 目录提交到 Git
git add .claude/
git commit -m "Add clarify-demand-uncertainty skill"
```

### 方式 2：全局安装

适用于个人使用，所有项目自动可用。

```bash
# 创建全局 skills 目录
mkdir -p ~/.claude/skills

# 复制 Skill
cp -r skills/clarify-demand-uncertainty ~/.claude/skills/
```

### 验证安装

检查文件是否正确复制：

```bash
# 项目级安装
ls -la .claude/skills/clarify-demand-uncertainty/

# 全局安装
ls -la ~/.claude/skills/clarify-demand-uncertainty/
```

应该看到以下文件：
```
clarify-demand-uncertainty/
├── SKILL.md
├── README.md
└── references/
    ├── requirements-template.md
    └── question-templates.md
```

---

## 🚀 快速开始

### 第 1 步：启动 Agent

启动 Claude Code 或你的 AI Agent。

### 第 2 步：测试 Skill

输入一个模糊的需求：

```
在设置页面加一个夜间模式的开关。
```

### 第 3 步：观察行为

如果 Skill 正常工作，Agent 应该：
1. 识别出需求模糊
2. 提出结构化的澄清问题
3. 使用勾选框形式呈现

### 第 4 步：回答问题

根据 Agent 的提问，选择或回答适用的选项。

### 第 5 步：确认文档

Agent 会生成需求文档 `docs/requirements-YYYYMMDD.md`，检查并确认。

### 第 6 步：开始实施

确认后，Agent 会根据明确的需求开始实施。

---

## 📖 使用场景

### 场景 1：新功能开发

**问题：** 产品经理提出的需求往往比较抽象

**解决：** Skill 自动提出关键问题，确保开发方向正确

**示例：**
```
PM：我们需要一个用户反馈功能。

Agent：[触发 Skill，提出澄清问题]
- 反馈的入口在哪里？
- 反馈内容包括哪些？
- 是否需要截图功能？
- 反馈提交后如何处理？
...

[生成明确的需求文档]
[按需求实施]
```

### 场景 2：性能优化

**问题：** "优化"是一个很宽泛的概念

**解决：** Skill 帮助定位具体的性能问题

**示例：**
```
用户：这个页面太慢了，优化一下。

Agent：[触发 Skill]
- 具体是哪个页面？
- "慢"的具体表现是什么？
- 当前加载时间是多少？
- 期望的加载时间是多少？
...

[定位问题，制定优化方案]
```

### 场景 3：界面调整

**问题：** UI 需求往往缺少交互细节

**解决：** Skill 确保 UI 实现符合预期

**示例：**
```
设计师：在这里加一个搜索框。

Agent：[触发 Skill]
- 搜索的范围是什么？
- 搜索方式是实时还是点击搜索？
- 搜索结果如何展示？
- 是否需要搜索历史？
...

[实现符合预期的搜索功能]
```

---

## 🎯 最佳实践

### 1. 信任 Skill 的判断

如果 Skill 提出问题，说明确实有需要澄清的地方，不要跳过。

### 2. 详细回答问题

越详细的回答，越能得到准确的实现。

### 3. 使用勾选框快速回答

Skill 提供的勾选框选项涵盖了常见情况，直接勾选即可。

### 4. 保存需求文档

生成的需求文档是重要的项目文档，应该：
- 提交到版本控制
- 作为验收标准
- 作为后续维护的参考

### 5. 定期回顾和优化

根据实际使用效果，可以：
- 调整问题模板
- 补充新的问题类型
- 优化触发条件

---

## 🔧 自定义配置

### 修改问题模板

编辑 `references/question-templates.md`，添加或修改问题：

```markdown
## 你的自定义问题类型

### 问题 1
- 描述

### 问题 2
- 描述
```

### 修改需求文档模板

编辑 `references/requirements-template.md`，调整文档结构。

### 调整触发条件

编辑 `SKILL.md` 的"何时使用"和"何时不使用"部分。

---

## 📊 效果评估

### 评估指标

使用 Skill 一段时间后，可以评估以下指标：

| 指标 | 使用前 | 使用后 | 改善 |
|------|--------|--------|------|
| 返工率 | 30% | 10% | ↓ 67% |
| 需求澄清时间 | 2 天 | 1 小时 | ↓ 94% |
| 需求理解准确度 | 70% | 95% | ↑ 36% |
| 团队满意度 | 3/5 | 4.5/5 | ↑ 50% |

### 收集反馈

定期收集团队反馈：
- Skill 是否准确识别模糊需求？
- 提出的问题是否有价值？
- 生成的文档是否有用？
- 是否有误触发或漏触发？

---

## 🐛 故障排除

### 问题 1：Skill 没有触发

**可能原因：**
- Skill 文件路径不正确
- SKILL.md 格式错误
- Agent 未正确加载 Skill

**解决方法：**
1. 检查文件路径
2. 检查 YAML front matter 格式
3. 重启 Agent

### 问题 2：Skill 误触发

**可能原因：**
- "何时使用"的条件过于宽泛

**解决方法：**
1. 编辑 SKILL.md
2. 在"何时不使用"中添加更多排除条件
3. 调整触发条件的描述

### 问题 3：问题不够针对性

**可能原因：**
- 问题模板需要优化

**解决方法：**
1. 编辑 `references/question-templates.md`
2. 添加更具体的问题
3. 调整问题选择策略

### 问题 4：生成的文档格式不对

**可能原因：**
- 模板文件损坏或格式错误

**解决方法：**
1. 检查 `references/requirements-template.md`
2. 确保 Markdown 格式正确
3. 重新复制模板文件

---

## 📚 相关文档

- [README.md](../../skills/clarify-demand-uncertainty/README.md) - Skill 概述
- [SKILL.md](../../skills/clarify-demand-uncertainty/SKILL.md) - Skill 主文件
- [usage-examples.md](usage-examples.md) - 使用示例
- [test-cases.md](test-cases.md) - 测试用例

---

## 🤝 获取帮助

如果遇到问题：

1. **查看文档**：先查看相关文档和示例
2. **运行测试**：使用 test-cases.md 中的测试用例验证
3. **提交 Issue**：在项目仓库提交问题
4. **社区讨论**：在讨论区寻求帮助

---

## 🎉 开始使用

现在你已经准备好使用 `clarify-demand-uncertainty` Skill 了！

试试输入一个模糊的需求，看看 Skill 如何帮助你澄清它。

祝使用愉快！
