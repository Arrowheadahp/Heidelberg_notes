#paper 
## [[USEAgent]]
## [[USE-Bench]]
### Previous Agents for Software Engineering
Agent parts
1. LLM
	1. Decision making
	2. Content Generation
2. Tools
	1. Interaction with external Environment
	2. Acquire more knowledge
Agents employ reasoning frameworks to orchestrate the LLM and the tool usage and one of the most popular reasoning frameworks is the [[ReAct]] framework. 
#### Comparison of different SE Agents
- Structure and domain knowledge they introduce (Granularity of Tools)
	- [[AutoCodeRover]] uses set of project structure aware tools ex: search_method_in_class
	- OpenHands [[CodeActAgent]] uses basic tools ex: CmdRunAction
	- Google Jules uses same
- Decision Framework (Autonomy of using the tools)
	- [[AutoCodeRover]] and Agentless break the agent execution into phases (workflow based)
	- RepairAgent uses finite state machine (workflow based)
	- [[CodeActAgent]] is versatile (more autonomous)
#### Having a set workflow 
- Pros:
	- Cost effective
	- Domain knowledge and analysis for each phase
	- Interpretable
- Cons: 
	- Not Versatile