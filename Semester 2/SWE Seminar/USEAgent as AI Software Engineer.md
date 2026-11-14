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
### Configuring [[CodeActAgent]] for Testing
OpenHands [[CodeActAgent]] is a general purpose agent which utilizes structured controller agent runtime architecture, where AgentController acts as a supervisor. Since it does not rely on task specific workflow, it is versatile. It works similar to [[USEAgent]] but the actions are
- CmdRunAction
- IPythonRunCellAction
- FileEditAction
- AgentFinishAction
The termination condition is also similar to [[USEAgent]]. 
==[[CodeActAgent]] employs similar reasoning framework as [[USEAgent]] but the actions operate on a mush lower level==.
### Research Questions and Results
#### 1. Efficacy of Agentic Systems: 
How well do [[USEAgent]] and [[CodeActAgent]] perform on [[USE-Bench]]?
![[Pasted image 20261114161026.png]]
[[USEAgent]] demonstrates similar efficacy as the [[AutoCodeRover]] in [[SWE-Bench]] verified. It also shows consistent improvement from [[CodeActAgent]]
#### 2. Analysis of plausible patches:
Are the solutions or patches given by the agents memorized or overfitted?

The significant number of results are checked manually and 1.3% is memorized (exact copy of answers) and 10.5% overfitted (suspiciously similar results) to ground truth. This is a reductionin rate of overfitting from previous agents like SpecRover (31%). This reduction is attributed to new action: ExecuteTests. 