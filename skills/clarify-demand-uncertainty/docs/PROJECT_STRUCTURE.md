# clarify-demand-uncertainty 项目结构

## 📁 文件组织

```
FlySkill/
├── skills/clarify-demand-uncertainty/          # Skill 核心文件
│   ├── SKILL.md                                # Skill 定义（必需）
│   ├── README.md                               # 使用说明
│   ├── CHANGELOG.md                            # 版本更新记录
│   ├── docs/                                   # 文档目录
│   │   └── PROJECT_STRUCTURE.md               # 本文件
│   └── references/                             # 参考资料
│       ├── question-templates.md              # 问题模板库
│       └── requirements-template.md           # 需求文档模板
│
├── examples/clarify-demand-uncertainty/        # 示例和测试
│   ├── usage-examples.md                      # 使用示例（7个场景）
│   ├── test-cases.md                          # 测试用例（14个测试）
│   ├── installation-guide.md                  # 安装指南
│   └── prompts_with_skills.md                 # 提示词示例
│
└── clarify-demand-uncertainty-v2.0-summary.md  # 版本总结（根目录）
```

## 📄 文件说明

### 核心文件

#### SKILL.md
- **作用**: Skill 的核心定义文件，Claude 通过此文件理解 Skill 的触发条件和工作流程
- **内容**: 
  - 触发条件（何时使用/何时不使用）
  - 工作流程（5个阶段）
  - 问题分类（5大类）
  - 输出格式
- **重要性**: ⭐⭐⭐⭐⭐ 必需文件

#### README.md
- **作用**: 面向用户的使用说明文档
- **内容**:
  - 功能概述
  - 适用场景
  - 快速开始
  - 工作流程
  - 效果对比
- **重要性**: ⭐⭐⭐⭐⭐ 必需文件

#### CHANGELOG.md
- **作用**: 记录版本更新历史
- **内容**:
  - v2.0 更新（2024-12-16）
  - v1.0 初始版本
- **重要性**: ⭐⭐⭐⭐ 推荐文件

### 参考资料

#### references/question-templates.md
- **作用**: 详细的问题模板库
- **内容**:
  - 功能需求类问题（核心目标、用户相关、优先级）
  - 技术约束类问题（技术栈、兼容性、安全）
  - 数据相关类问题（来源、格式、量级、存储）
  - 用户体验类问题（交互、界面、设备）
  - 性能与规模类问题（响应时间、并发、扩展性）
- **重要性**: ⭐⭐⭐⭐ 推荐文件

#### references/requirements-template.md
- **作用**: 标准需求文档模板
- **内容**:
  - 8个标准章节结构
  - 可直接用于生成需求文档
- **重要性**: ⭐⭐⭐⭐ 推荐文件

### 示例文档

#### examples/usage-examples.md
- **作用**: 展示实际使用效果
- **内容**: 7个完整示例
  1. 模糊的界面需求
  2. 模糊的性能需求
  3. 业务逻辑不明确
  4. 缺少技术栈信息
  5. 数据处理不明确
  6. 集成对接不明确
  7. 用户体验不明确
- **重要性**: ⭐⭐⭐⭐ 学习参考

#### examples/test-cases.md
- **作用**: 验证 Skill 是否正常工作
- **内容**: 14个测试用例
  - 10个应该/不应该触发的测试
  - 4个特殊情况测试
  - 测试结果记录表
- **重要性**: ⭐⭐⭐⭐ 测试验证

#### examples/installation-guide.md
- **作用**: 详细的安装和配置指南
- **内容**:
  - 安装步骤
  - 快速开始
  - 使用场景
  - 常见问题
- **重要性**: ⭐⭐⭐ 新手指南

#### examples/prompts_with_skills.md
- **作用**: 提示词示例
- **重要性**: ⭐⭐⭐ 参考资料

### 根目录文件

#### clarify-demand-uncertainty-v2.0-summary.md
- **作用**: v2.0 版本的总结文档
- **内容**:
  - 版本亮点
  - 更新内容
  - 安装使用
  - 预期效果
- **重要性**: ⭐⭐⭐ 版本说明

## 🎯 文件使用指南

### 如果你是新用户
1. 先读 `README.md` 了解功能
2. 参考 `examples/installation-guide.md` 安装
3. 查看 `examples/usage-examples.md` 学习使用
4. 用 `examples/test-cases.md` 验证安装

### 如果你要开发/修改 Skill
1. 核心逻辑在 `SKILL.md`
2. 问题模板在 `references/question-templates.md`
3. 文档模板在 `references/requirements-template.md`
4. 测试用例在 `examples/test-cases.md`

### 如果你要分享 Skill
必需文件：
- `SKILL.md`
- `README.md`

推荐文件：
- `CHANGELOG.md`
- `references/` 目录
- `examples/usage-examples.md`
- `examples/test-cases.md`

## 📊 文件依赖关系

```
SKILL.md (核心)
    ↓ 引用
references/question-templates.md (问题库)
    ↓ 生成
requirements-YYYYMMDD.md (输出文档)
    ↓ 基于
references/requirements-template.md (模板)
```

## 🔄 版本历史

- **v2.0** (2024-12-16): 扩展触发场景，新增业务逻辑、数据处理、集成对接场景
- **v1.0** (2024-12-16): 初始版本，基础需求澄清功能
