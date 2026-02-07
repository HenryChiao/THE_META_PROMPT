# THE META PROMPT

[中文文档](./README_zh.md) | English

A curated collection of production-grade meta-prompts for building high-performance AI agents and structured reasoning systems across multiple domains.

## Overview

THE META PROMPT is a specialized repository providing battle-tested, structured meta-prompt templates designed to transform general-purpose Large Language Models into domain-specific reasoning agents with enhanced reliability and precision. Unlike traditional prompt libraries, this collection focuses on meta-level instruction frameworks that enable systematic task decomposition, role-based reasoning, and self-improving agent architectures.

### Core Value Proposition

- **Zero-Shot Specialization**: Transform base LLMs into specialized agents without fine-tuning or extensive example sets
- **Systematic Reasoning**: Implement structured thought processes through hierarchical instruction frameworks
- **Production-Ready**: Validated templates suitable for deployment in professional workflows
- **Domain Coverage**: Comprehensive coverage across general-purpose agents, academic research, and literature analysis
- **Model Agnostic**: Compatible with GPT-4, Claude, Gemini, Llama, and other instruction-following models

### Target Users

- Prompt Engineers building complex AI workflows
- AI Researchers developing agent frameworks
- Developers implementing LLM-based automation systems
- Academic professionals requiring structured reasoning tools
- Product teams integrating AI capabilities into production environments

## Key Features

### Architectural Design
- Modular prompt structure with clear role definitions and capability boundaries
- Explicit reasoning step requirements for transparent decision-making
- Structured output formats using XML/JSON tags for downstream parsing
- Error handling and edge case recovery mechanisms
- Multi-turn conversation state management protocols

### Template Quality Assurance
- Production-validated across multiple LLM providers
- Consistent performance verified through systematic testing
- Comprehensive inline documentation within each template
- Version-controlled with semantic release tracking

### Extensibility Framework
- Clear modification guidelines for customization
- Language localization support with maintained structural integrity
- Domain-specific variant generation methodology
- Community contribution pipeline with quality standards

## Environment Requirements

### System Prerequisites
- Text editor or Markdown viewer
- LLM interface with system message support (API or chat interface)

### Compatible LLM Platforms
- OpenAI API (GPT-3.5, GPT-4, GPT-4 Turbo)
- Anthropic Claude (Claude 3 Opus/Sonnet/Haiku)
- Google Gemini (Pro, Ultra)
- Open-source models (Llama 2/3, Mistral, Qwen)
- Any LLM supporting structured system prompts

### Technical Dependencies
None. Repository contains standalone Markdown files with no runtime dependencies.

## Installation

### Quick Start

```bash
# Clone repository
git clone https://github.com/HenryChiao/THE_META_PROMPT.git
cd THE_META_PROMPT

# View available templates
ls -la *.md
```

### Basic Usage Pattern

```python
# Example: OpenAI API Integration
import openai

# Load meta-prompt template
with open('THE_META_AGENT_PROMPT.md', 'r', encoding='utf-8') as f:
    system_prompt = f.read()

# Initialize agent
response = openai.ChatCompletion.create(
    model="gpt-4",
    messages=[
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": "Your task-specific query"}
    ]
)
```

```python
# Example: Anthropic Claude Integration
import anthropic

with open('THE_ACADEMIC.md', 'r', encoding='utf-8') as f:
    system_prompt = f.read()

client = anthropic.Anthropic(api_key="your-api-key")
message = client.messages.create(
    model="claude-3-opus-20240229",
    max_tokens=4096,
    system=system_prompt,
    messages=[
        {"role": "user", "content": "Analyze the methodology of [research paper]"}
    ]
)
```

## Project Architecture

### Template Catalog

#### 1. General Meta Agent (`THE_META_AGENT_PROMPT.md`)

**Purpose**: Universal reasoning framework for general-purpose agent construction

**Core Capabilities**:
- Multi-step task decomposition with explicit reasoning chains
- Tool use orchestration and result integration
- Error detection and recovery strategies
- Context-aware response generation
- Self-consistency verification mechanisms

**Use Cases**:
- Complex workflow automation
- Multi-tool coordination systems
- Conversational AI with reasoning transparency
- Decision support applications

**Structural Components**:
```
├── Role Definition (Agent identity and boundaries)
├── Capability Matrix (Supported operations and limitations)
├── Reasoning Protocol (Step-by-step thought process structure)
├── Tool Integration Layer (External system interaction patterns)
├── Output Specification (Response format requirements)
└── Error Handling (Failure modes and recovery procedures)
```

---

#### 2. Academic Research Agent (`THE_ACADEMIC.md`)

**Purpose**: Specialized framework for academic analysis and research workflows

**Core Capabilities**:
- Citation handling and source evaluation
- Research methodology compliance
- Hypothesis generation and testing frameworks
- Literature review synthesis
- Academic writing standards enforcement

**Use Cases**:
- Systematic literature reviews
- Research proposal development
- Methodology critique and improvement
- Academic paper analysis
- Evidence-based argumentation

**Structural Components**:
```
├── Research Role Definition (Academic agent identity)
├── Source Evaluation Protocols (Citation quality assessment)
├── Methodology Framework (Research process structure)
├── Evidence Synthesis (Cross-source integration)
├── Academic Output Standards (Scholarly writing requirements)
└── Ethical Guidelines (Research integrity constraints)
```

---

#### 3. Localized Agent - Chinese (`THE_META_AGENT_PROMPT_CN.md`)

**Purpose**: Chinese language optimization with cultural context adaptation

**Core Capabilities**:
- Native Chinese reasoning patterns
- Cultural context awareness
- Language-specific idiom handling
- Regional regulatory compliance
- Cross-cultural communication protocols

**Use Cases**:
- Chinese market applications
- Multilingual workflow systems
- Cultural adaptation requirements
- Regional compliance automation

**Structural Components**:
```
├── 角色定义 (Role Definition in Chinese)
├── 能力边界 (Capability Boundaries)
├── 推理流程 (Reasoning Workflow)
├── 文化适配 (Cultural Adaptation Layer)
├── 输出规范 (Output Specifications)
└── 异常处理 (Error Handling)
```

---

#### 4. Literature Analysis Agent (`Literature_meta_prompt.md`)

**Purpose**: Specialized framework for literary text analysis and critique

**Core Capabilities**:
- Narrative structure analysis
- Thematic element extraction
- Stylistic feature identification
- Character development tracking
- Literary device recognition

**Use Cases**:
- Literary criticism automation
- Text analysis workflows
- Creative writing feedback
- Comparative literature studies

---

#### 5. General Purpose Template (`General_meta_prompt.md`)

**Purpose**: Foundational template for custom agent development

**Core Capabilities**:
- Baseline reasoning structure
- Generic task handling patterns
- Extensible framework foundation
- Minimal constraint baseline

**Use Cases**:
- Custom agent prototyping
- Domain-specific adaptation base
- Educational prompt engineering reference

## Usage Examples

### Example 1: Academic Literature Review

```python
import anthropic

# Load academic agent template
with open('THE_ACADEMIC.md', 'r') as f:
    academic_prompt = f.read()

client = anthropic.Anthropic()

# Task: Systematic review of AI safety papers
response = client.messages.create(
    model="claude-3-opus-20240229",
    max_tokens=8192,
    system=academic_prompt,
    messages=[{
        "role": "user",
        "content": """
        Conduct a systematic review of AI alignment research 
        published in 2023-2024. Focus on:
        1. Key methodological approaches
        2. Empirical validation strategies
        3. Open research questions
        4. Citation network analysis
        """
    }]
)
```

### Example 2: Multi-Tool Agent Workflow

```python
import openai

with open('THE_META_AGENT_PROMPT.md', 'r') as f:
    agent_prompt = f.read()

# Agent with calculator and web search tools
response = openai.ChatCompletion.create(
    model="gpt-4-turbo",
    messages=[
        {"role": "system", "content": agent_prompt},
        {"role": "user", "content": "Calculate ROI for Q4 2024 and compare with industry benchmarks"}
    ],
    tools=[
        {"type": "function", "function": {"name": "calculator"}},
        {"type": "function", "function": {"name": "web_search"}}
    ]
)
```

### Example 3: Custom Domain Adaptation

```python
# Extend general template for legal document analysis
with open('General_meta_prompt.md', 'r') as f:
    base_prompt = f.read()

# Add domain-specific constraints
legal_prompt = base_prompt + """

## Legal Document Analysis Extensions

### Domain Constraints
- Apply strict citation verification
- Maintain jurisdiction-specific compliance
- Flag potential legal ambiguities
- Preserve original document language

### Output Requirements
- Structured legal analysis format
- Referenced case law citations
- Risk assessment framework
- Compliance checklist
"""

# Deploy customized agent
```

## Configuration Guidelines

### Template Customization Best Practices

#### Modify Role Definition
```markdown
# Original
You are a general-purpose reasoning agent...

# Customized for Financial Analysis
You are a quantitative financial analyst specializing in 
risk assessment and portfolio optimization...
```

#### Extend Capability Matrix
```markdown
# Add domain-specific capabilities
## Financial Analysis Capabilities
- Time series forecasting
- Risk metric calculation (VaR, CVaR)
- Correlation analysis
- Regulatory compliance checking
```

#### Adjust Output Format
```xml
<!-- Original structured output -->
<response>
  <analysis>...</analysis>
  <conclusion>...</conclusion>
</response>

<!-- Extended for financial reporting -->
<financial_report>
  <executive_summary>...</executive_summary>
  <quantitative_analysis>...</quantitative_analysis>
  <risk_assessment>...</risk_assessment>
  <recommendations>...</recommendations>
  <compliance_notes>...</compliance_notes>
</financial_report>
```

### Multi-Provider Testing

Always validate customizations across multiple LLM providers:

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

## Template Structure Reference

### Standard Section Hierarchy

All templates follow this organizational pattern:

```
1. Role Definition
   ├── Primary Identity
   ├── Capability Scope
   └── Operational Boundaries

2. Reasoning Framework
   ├── Task Analysis Protocol
   ├── Decomposition Strategy
   ├── Step-by-Step Execution
   └── Verification Procedures

3. Tool Integration (if applicable)
   ├── Available Tools Catalog
   ├── Tool Selection Criteria
   ├── Result Interpretation
   └── Error Handling

4. Output Specification
   ├── Format Requirements
   ├── Structured Data Schema
   ├── Quality Standards
   └── Edge Case Handling

5. Meta-Instructions
   ├── Self-Improvement Triggers
   ├── Clarification Protocols
   ├── Escalation Procedures
   └── Performance Monitoring
```

### Inline Documentation Format

Templates include embedded usage notes:

```markdown
<!-- Usage Note: This section defines core reasoning protocol -->
## Reasoning Framework
[... template content ...]

<!-- Example: For financial analysis tasks, emphasize quantitative validation -->
```

## Version History

### Current Release: v1.0.0 (Production Stable)

**Release Date**: 2024-02

**Core Templates**:
- THE_META_AGENT_PROMPT.md (General agent framework)
- THE_ACADEMIC.md (Academic research framework)
- THE_META_AGENT_PROMPT_CN.md (Chinese localization)
- Literature_meta_prompt.md (Literary analysis framework)
- General_meta_prompt.md (Foundational template)

**Validation Status**:
- Tested across GPT-4, Claude 3, Gemini Pro
- Production deployment verified
- Community feedback integrated

**Known Limitations**:
- Template file size may require chunking for models with small context windows
- Some templates assume tool use capabilities not available in all LLM APIs
- Chinese template optimization focused on Simplified Chinese

## Contribution Guidelines

### Submission Requirements

**Accepted Contributions**:
- Prompt clarity improvements
- Domain-specific template variants
- Additional language localizations
- Bug fixes and edge case handling
- Performance optimization
- Documentation enhancements

**Contribution Process**:

```bash
# Fork repository
git clone https://github.com/YOUR_USERNAME/THE_META_PROMPT.git
cd THE_META_PROMPT

# Create feature branch
git checkout -b feature/domain-legal-agent

# Add your template or modifications
# Follow existing structure and naming conventions

# Test across multiple LLM providers
python test_suite.py --template your_template.md

# Submit pull request with validation results
```

**Pull Request Template**:
```markdown
## Template Name
[e.g., Legal Document Analysis Agent]

## Purpose
[Brief description of use case]

## Validation Results
- [ ] Tested with GPT-4
- [ ] Tested with Claude 3
- [ ] Tested with Gemini Pro
- [ ] Output format validation passed
- [ ] Edge case handling verified

## Sample Output
[Attach representative output examples]

## Additional Notes
[Any specific considerations or limitations]
```

### Quality Standards

All contributions must maintain:
- Clear hierarchical structure matching existing templates
- Explicit reasoning step requirements
- Structured output format definitions
- Comprehensive inline documentation
- No external dependencies
- Cross-provider compatibility

### Code of Conduct

- Maintain professional, respectful communication
- Provide constructive feedback on submissions
- Credit original prompt engineering research appropriately
- Respect intellectual property and licensing terms

## License

MIT License

Copyright (c) 2024 THE META PROMPT Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Contact

**Project Maintainer**: HenryChiao

**Repository**: [https://github.com/HenryChiao/THE_META_PROMPT](https://github.com/HenryChiao/THE_META_PROMPT)

**Issue Tracker**: [https://github.com/HenryChiao/THE_META_PROMPT/issues](https://github.com/HenryChiao/THE_META_PROMPT/issues)

**Contribution Discussions**: [https://github.com/HenryChiao/THE_META_PROMPT/discussions](https://github.com/HenryChiao/THE_META_PROMPT/discussions)

For questions, feedback, or collaboration inquiries, please open an issue on GitHub or participate in community discussions.

---

## Acknowledgments

This project builds upon research in meta-prompting frameworks and prompt engineering methodologies from the AI research community. Special recognition to contributors of structured prompting techniques and agent architecture patterns that informed these templates.

## Related Resources

### Research Papers
- Meta-Prompting: Enhancing Language Models with Task-Agnostic Scaffolding
- Prompt Engineering for Large Language Models: A Survey
- Constitutional AI: Harmlessness from AI Feedback

### Community Resources
- [Anthropic Prompt Library](https://docs.anthropic.com/claude/prompt-library)
- [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
- [LangChain Prompt Templates](https://python.langchain.com/docs/modules/model_io/prompts/)

### Complementary Tools
- [DSPy](https://github.com/stanfordnlp/dspy): Programming framework for LM pipelines
- [Guidance](https://github.com/guidance-ai/guidance): Structured generation library
- [LangChain](https://github.com/langchain-ai/langchain): Agent development framework
