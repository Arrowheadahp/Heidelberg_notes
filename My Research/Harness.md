Harness is the deterministic part of the [[Agent]]. This is the scaffolding that makes the [[LLM]] run. It has multiple parts having their own requirements.
[Anatomy of an Agent Harness](https://www.langchain.com/blog/the-anatomy-of-an-agent-harness)

The idea is that the harness can 
1. Execute code using shell or others
2. Access real-time knowledge using browser capabilities
3. Tool Execution

![[Pasted image 20261007234437.png]]
### System prompts
This is the soul.md, claude.md or the agents.md files that are given to every prompt that tells the LLM how to approach the given prompt
### Tools, Skills, MCPs
### Bundled Infrastructure
### Orchestration Logic
### Hooks/Middleware for deterministic execution

[^1]: 
