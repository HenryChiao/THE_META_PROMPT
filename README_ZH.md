# THE META PROMPT 元提示词库

[English](./README.md) | 中文文档

生产级元提示词精选集,用于构建高性能 AI 智能体和跨领域结构化推理系统。

## 项目概述

THE META PROMPT 是一个专业化的提示词仓库,提供经过实战验证的结构化元提示词模板,旨在将通用大语言模型转化为具有增强可靠性和精确度的领域专用推理智能体。与传统提示词库不同,本项目专注于元级别的指令框架,支持系统化任务分解、基于角色的推理以及自我改进的智能体架构。

### 核心价值主张

- **零样本专业化**: 无需微调或大量示例即可将基础 LLM 转化为专用智能体
- **系统化推理**: 通过分层指令框架实现结构化思维过程
- **生产就绪**: 经过验证的模板可直接部署至专业工作流
- **领域覆盖**: 全面覆盖通用智能体、学术研究、文学分析等场景
- **模型无关**: 兼容 GPT-4、Claude、Gemini、Llama 等主流指令遵循模型

### 目标用户

- 构建复杂 AI 工作流的提示词工程师
- 开发智能体框架的 AI 研究人员
- 实现基于 LLM 自动化系统的开发者
- 需要结构化推理工具的学术专业人士
- 将 AI 能力集成到生产环境的产品团队

## 核心特性

### 架构设计
- 模块化提示词结构,具备清晰的角色定义和能力边界
- 显式推理步骤要求,确保决策过程透明可追溯
- 使用 XML/JSON 标签的结构化输出格式,便于下游解析
- 错误处理和边缘场景恢复机制
- 多轮对话状态管理协议

### 模板质量保证
- 经多个 LLM 提供商的生产环境验证
- 通过系统化测试确保性能一致性
- 每个模板内置全面的行内文档
- 采用语义化版本控制进行版本追踪

### 可扩展性框架
- 清晰的定制化修改指南
- 支持多语言本地化且保持结构完整性
- 领域专用变体生成方法论
- 具备质量标准的社区贡献流程

## 环境要求

### 系统前置条件
- 文本编辑器或 Markdown 查看器
- 支持系统消息的 LLM 接口(API 或聊天界面)

### 兼容 LLM 平台
- OpenAI API (GPT-3.5、GPT-4、GPT-4 Turbo)
- Anthropic Claude (Claude 3 Opus/Sonnet/Haiku)
- Google Gemini (Pro、Ultra)
- 开源模型 (Llama 2/3、Mistral、通义千问)
- 任何支持结构化系统提示词的 LLM

### 技术依赖
无。本仓库包含独立的 Markdown 文件,无运行时依赖。

## 安装部署

### 快速开始

```bash
# 克隆仓库
git clone https://github.com/HenryChiao/THE_META_PROMPT.git
cd THE_META_PROMPT

# 查看可用模板
ls -la *.md
```

### 基础使用模式

```python
# 示例: OpenAI API 集成
import openai

# 加载元提示词模板
with open('THE_META_AGENT_PROMPT.md', 'r', encoding='utf-8') as f:
    system_prompt = f.read()

# 初始化智能体
response = openai.ChatCompletion.create(
    model="gpt-4",
    messages=[
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": "您的任务特定查询"}
    ]
)
```

```python
# 示例: Anthropic Claude 集成
import anthropic

with open('THE_ACADEMIC.md', 'r', encoding='utf-8') as f:
    system_prompt = f.read()

client = anthropic.Anthropic(api_key="your-api-key")
message = client.messages.create(
    model="claude-3-opus-20240229",
    max_tokens=4096,
    system=system_prompt,
    messages=[
        {"role": "user", "content": "分析 [研究论文] 的研究方法"}
    ]
)
```

## 项目架构

### 模板目录

#### 1. 通用元智能体 (`THE_META_AGENT_PROMPT.md`)

**用途**: 通用推理框架,用于构建通用型智能体

**核心能力**:
- 多步骤任务分解与显式推理链
- 工具使用编排和结果集成
- 错误检测与恢复策略
- 上下文感知的响应生成
- 自洽性验证机制

**应用场景**:
- 复杂工作流自动化
- 多工具协调系统
- 具备推理透明度的对话式 AI
- 决策支持应用

**结构组成**:
```
├── 角色定义 (智能体身份与边界)
├── 能力矩阵 (支持的操作与限制)
├── 推理协议 (分步思考流程结构)
├── 工具集成层 (外部系统交互模式)
├── 输出规范 (响应格式要求)
└── 错误处理 (失败模式与恢复程序)
```

---

#### 2. 学术研究智能体 (`THE_ACADEMIC.md`)

**用途**: 学术分析和研究工作流的专用框架

**核心能力**:
- 引用处理和来源评估
- 研究方法论合规性
- 假设生成与测试框架
- 文献综述合成
- 学术写作标准执行

**应用场景**:
- 系统性文献综述
- 研究提案开发
- 方法论批判与改进
- 学术论文分析
- 循证论证

**结构组成**:
```
├── 研究角色定义 (学术智能体身份)
├── 来源评估协议 (引用质量评估)
├── 方法论框架 (研究流程结构)
├── 证据综合 (跨来源整合)
├── 学术输出标准 (学术写作要求)
└── 伦理指南 (研究诚信约束)
```

---

#### 3. 本地化智能体 - 中文 (`THE_META_AGENT_PROMPT_CN.md`)

**用途**: 中文语言优化与文化语境适配

**核心能力**:
- 母语级中文推理模式
- 文化语境感知
- 特定语言习语处理
- 区域监管合规
- 跨文化交流协议

**应用场景**:
- 中国市场应用
- 多语言工作流系统
- 文化适配需求
- 区域合规自动化

**结构组成**:
```
├── 角色定义 (中文角色定义)
├── 能力边界 (能力范围界定)
├── 推理流程 (推理工作流)
├── 文化适配 (文化适配层)
├── 输出规范 (输出格式规范)
└── 异常处理 (错误处理机制)
```

---

#### 4. 文学分析智能体 (`Literature_meta_prompt.md`)

**用途**: 文学文本分析与批评的专用框架

**核心能力**:
- 叙事结构分析
- 主题要素提取
- 风格特征识别
- 人物发展追踪
- 文学手法辨识

**应用场景**:
- 文学批评自动化
- 文本分析工作流
- 创意写作反馈
- 比较文学研究

---

#### 5. 通用模板 (`General_meta_prompt.md`)

**用途**: 自定义智能体开发的基础模板

**核心能力**:
- 基线推理结构
- 通用任务处理模式
- 可扩展框架基础
- 最小约束基准

**应用场景**:
- 自定义智能体原型开发
- 领域特定适配基础
- 提示词工程教育参考

## 使用示例

### 示例 1: 学术文献综述

```python
import anthropic

# 加载学术智能体模板
with open('THE_ACADEMIC.md', 'r', encoding='utf-8') as f:
    academic_prompt = f.read()

client = anthropic.Anthropic()

# 任务: AI 安全论文系统性综述
response = client.messages.create(
    model="claude-3-opus-20240229",
    max_tokens=8192,
    system=academic_prompt,
    messages=[{
        "role": "user",
        "content": """
        对 2023-2024 年发表的 AI 对齐研究进行系统性综述,重点关注:
        1. 关键方法论途径
        2. 实证验证策略
        3. 开放研究问题
        4. 引用网络分析
        """
    }]
)
```

### 示例 2: 多工具智能体工作流

```python
import openai

with open('THE_META_AGENT_PROMPT.md', 'r', encoding='utf-8') as f:
    agent_prompt = f.read()

# 配备计算器和网络搜索工具的智能体
response = openai.ChatCompletion.create(
    model="gpt-4-turbo",
    messages=[
        {"role": "system", "content": agent_prompt},
        {"role": "user", "content": "计算 2024 年第四季度 ROI 并与行业基准对比"}
    ],
    tools=[
        {"type": "function", "function": {"name": "calculator"}},
        {"type": "function", "function": {"name": "web_search"}}
    ]
)
```

### 示例 3: 自定义领域适配

```python
# 扩展通用模板用于法律文件分析
with open('General_meta_prompt.md', 'r', encoding='utf-8') as f:
    base_prompt = f.read()

# 添加领域特定约束
legal_prompt = base_prompt + """

## 法律文件分析扩展

### 领域约束
- 应用严格的引用验证
- 维护司法管辖区特定合规性
- 标记潜在法律歧义
- 保留原始文件语言

### 输出要求
- 结构化法律分析格式
- 参考案例法引用
- 风险评估框架
- 合规性检查清单
"""

# 部署定制化智能体
```

## 配置指南

### 模板定制最佳实践

#### 修改角色定义
```markdown
# 原始定义
您是一个通用推理智能体...

# 定制为金融分析
您是一位专门从事风险评估和投资组合优化的量化金融分析师...
```

#### 扩展能力矩阵
```markdown
# 添加领域特定能力
## 金融分析能力
- 时间序列预测
- 风险指标计算 (VaR, CVaR)
- 相关性分析
- 监管合规检查
```

#### 调整输出格式
```xml
<!-- 原始结构化输出 -->
<response>
  <analysis>...</analysis>
  <conclusion>...</conclusion>
</response>

<!-- 扩展为金融报告 -->
<financial_report>
  <executive_summary>...</executive_summary>
  <quantitative_analysis>...</quantitative_analysis>
  <risk_assessment>...</risk_assessment>
  <recommendations>...</recommendations>
  <compliance_notes>...</compliance_notes>
</financial_report>
```

### 多提供商测试

始终在多个 LLM 提供商上验证定制化:

```python
providers = [
    ("openai", "gpt-4"),
    ("anthropic", "claude-3-opus-20240229"),
    ("google", "gemini-pro")
]

for provider, model in providers:
    response = test_prompt(custom_prompt, provider, model)
    validate_output_format(response)
    measure_consistency(response)
```

## 模板结构参考

### 标准章节层次

所有模板遵循此组织模式:

```
1. 角色定义
   ├── 主要身份
   ├── 能力范围
   └── 操作边界

2. 推理框架
   ├── 任务分析协议
   ├── 分解策略
   ├── 分步执行
   └── 验证程序

3. 工具集成 (如适用)
   ├── 可用工具目录
   ├── 工具选择标准
   ├── 结果解释
   └── 错误处理

4. 输出规范
   ├── 格式要求
   ├── 结构化数据模式
   ├── 质量标准
   └── 边缘情况处理

5. 元指令
   ├── 自我改进触发器
   ├── 澄清协议
   ├── 升级程序
   └── 性能监控
```

### 行内文档格式

模板包含嵌入式使用说明:

```markdown
<!-- 使用说明: 本节定义核心推理协议 -->
## 推理框架
[... 模板内容 ...]

<!-- 示例: 对于金融分析任务,强调定量验证 -->
```

## 版本历史

### 当前发布版本: v1.0.0 (生产稳定版)

**发布日期**: 2024-02

**核心模板**:
- THE_META_AGENT_PROMPT.md (通用智能体框架)
- THE_ACADEMIC.md (学术研究框架)
- THE_META_AGENT_PROMPT_CN.md (中文本地化)
- Literature_meta_prompt.md (文学分析框架)
- General_meta_prompt.md (基础模板)

**验证状态**:
- 已在 GPT-4、Claude 3、Gemini Pro 上测试
- 生产部署已验证
- 已整合社区反馈

**已知限制**:
- 对于上下文窗口较小的模型,模板文件大小可能需要分块
- 部分模板假设具备工具使用能力,但并非所有 LLM API 都支持
- 中文模板优化专注于简体中文

## 贡献指南

### 提交要求

**接受的贡献类型**:
- 提示词清晰度改进
- 领域特定模板变体
- 额外语言本地化
- Bug 修复和边缘情况处理
- 性能优化
- 文档增强

**贡献流程**:

```bash
# Fork 仓库
git clone https://github.com/YOUR_USERNAME/THE_META_PROMPT.git
cd THE_META_PROMPT

# 创建功能分支
git checkout -b feature/domain-legal-agent

# 添加您的模板或修改
# 遵循现有结构和命名约定

# 跨多个 LLM 提供商测试
python test_suite.py --template your_template.md

# 提交带验证结果的 Pull Request
```

**Pull Request 模板**:
```markdown
## 模板名称
[例如: 法律文件分析智能体]

## 用途
[简要描述使用场景]

## 验证结果
- [ ] 已在 GPT-4 上测试
- [ ] 已在 Claude 3 上测试
- [ ] 已在 Gemini Pro 上测试
- [ ] 输出格式验证通过
- [ ] 边缘情况处理已验证

## 示例输出
[附上代表性输出示例]

## 附加说明
[任何特定考虑事项或限制]
```

### 质量标准

所有贡献必须保持:
- 清晰的层次结构,与现有模板匹配
- 显式推理步骤要求
- 结构化输出格式定义
- 全面的行内文档
- 无外部依赖
- 跨提供商兼容性

### 行为准则

- 保持专业、尊重的沟通
- 对提交内容提供建设性反馈
- 适当注明原始提示词工程研究出处
- 尊重知识产权和许可条款

## 许可证

MIT License

Copyright (c) 2024 THE META PROMPT Contributors

特此免费授予任何获得本软件及相关文档文件("软件")副本的人不受限制地处置该软件的权利,包括但不限于使用、复制、修改、合并、发布、分发、再许可和/或出售该软件副本的权利,并允许向其提供本软件的人员这样做,但须符合以下条件:

上述版权声明和本许可声明应包含在本软件的所有副本或主要部分中。

本软件按"原样"提供,不提供任何形式的明示或暗示担保,包括但不限于对适销性、特定用途适用性和非侵权性的担保。在任何情况下,作者或版权持有人均不对因软件或软件的使用或其他处置而产生的或与之相关的任何索赔、损害或其他责任承担责任,无论是在合同诉讼、侵权诉讼还是其他诉讼中。

## 联系方式

**项目维护者**: HenryChiao

**仓库地址**: [https://github.com/HenryChiao/THE_META_PROMPT](https://github.com/HenryChiao/THE_META_PROMPT)

**问题追踪**: [https://github.com/HenryChiao/THE_META_PROMPT/issues](https://github.com/HenryChiao/THE_META_PROMPT/issues)

**贡献讨论**: [https://github.com/HenryChiao/THE_META_PROMPT/discussions](https://github.com/HenryChiao/THE_META_PROMPT/discussions)

如有问题、反馈或合作咨询,请在 GitHub 上开启 issue 或参与社区讨论。

---

## 致谢

本项目建立在 AI 研究社区关于元提示词框架和提示词工程方法论的研究基础之上。特别感谢结构化提示词技术和智能体架构模式的贡献者,这些工作为本模板提供了灵感。

## 相关资源

### 研究论文
- Meta-Prompting: Enhancing Language Models with Task-Agnostic Scaffolding
- Prompt Engineering for Large Language Models: A Survey
- Constitutional AI: Harmlessness from AI Feedback

### 社区资源
- [Anthropic Prompt Library](https://docs.anthropic.com/claude/prompt-library)
- [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
- [LangChain Prompt Templates](https://python.langchain.com/docs/modules/model_io/prompts/)

### 配套工具
- [DSPy](https://github.com/stanfordnlp/dspy): LM 管道编程框架
- [Guidance](https://github.com/guidance-ai/guidance): 结构化生成库
- [LangChain](https://github.com/langchain-ai/langchain): 智能体开发框架
