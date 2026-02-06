# THE_META_PROMPT

Structured meta-level prompts for building high-reliability AI agents and precision instruction systems.

## Overview

- **Purpose**: Provide battle-tested meta prompts that transform general-purpose LLMs into specialized reasoning agents
- **Target**: Prompt engineers, AI researchers, and developers building agent frameworks or complex LLM workflows
- **Status**: Production-ready (v1.0)

## Quick Start

1. Clone repository
   ```bash
   git clone https://github.com/HenryChiao/THE_META_PROMPT.git
   cd THE_META_PROMPT
   ```

2. Select prompt file matching your use case (see Architecture)

3. Load content into system message:
   
```plaintext
   System: [Paste content from selected .md file]
   User: [Your task-specific context]
   ```

Architecture

Module	File	Description	Use Case	
Meta Agent	`THE_META_AGENT_PROMPT.md`	Core meta-agent with reasoning framework	General-purpose agent construction	
Meta Agent CN	`THE_META_AGENT_PROMPT_CN.md`	Chinese localization of core prompt	Chinese language workflows	
Academic	`THE_ACADEMIC.md`	Research-oriented reasoning structure	Academic analysis, literature review, hypothesis testing	

Installation

No dependencies required. Repository contains standalone markdown files compatible with any LLM interface (OpenAI API, Claude, local models).

Requirements:
- LLM with system message support (GPT-4, Claude 3, Llama 2/3, etc.)
- Markdown viewer or text editor

Development

File Organization
All prompts follow hierarchical instruction structure:
1. Role definition
2. Capability constraints
3. Workflow protocols
4. Output specifications

Modification Guidelines
- Maintain explicit reasoning step requirements
- Preserve XML/structured output tags where present
- Test changes across multiple LLM providers for consistency

Documentation

Each `.md` file is self-documenting with embedded usage instructions:

- `THE_META_AGENT_PROMPT.md`: Agent architecture, tool use patterns, error recovery
- `THE_META_AGENT_PROMPT_CN.md`: Chinese language reasoning optimization, cultural context adaptation
- `THE_ACADEMIC.md`: Citation handling, source evaluation, research methodology compliance

Contributing

Submit pull requests for:
- Prompt clarity improvements
- Additional language localizations
- Domain-specific variants (legal, medical, engineering)
- Edge case handling refinements

Format: Maintain existing markdown structure with clear section headers.

License

MIT License
