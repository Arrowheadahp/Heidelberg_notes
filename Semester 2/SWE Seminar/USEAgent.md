## Unified Software Engineering Agent
### Inception:
[[USEAgent]] or Unified Software Engineering Agent is a novel agent that is created to tackle all problems that Software Engineers face. 
This is created to be the Second step in the development of AI Software Engineer. The first step (Existing agents) was the creation of the individual agents for single tasks. 
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
### Idea
To create the a Software Engineering Agent to be unified, it needs to be versatile. So the fixed workflow will not work. The idea is to have a ==Meta-Agent==, a reasoning LLM agent to orchestrate various ==Actions==. Together they create the [[USEAgent]].
#### Characteristics of USEAgent
1. **Orchestration by Meta-Agent**: 
   This is done by having the Meta-Agent orchestrate all the actions using [[ReAct]] loop. It invokes action, observes changes, reasons about the output, decides on next action. Therefore runtime orchestration is adaptable to different tasks, states and errors.
2. **Modularity of Actions**: 
   Some agents like [[CodeActAgent]] and Jules give the flexibility of executing any command with a console but these are too hard to control and less interpretable. But [[USEAgent]] has more coarse granularity of actions each encapsulating 1 unit of work. ==Each action receives only the outcomes it is supposed to achieve, not how it achieves them.==
3. **Memory Management**: 
   There are 3 types of memory defined:
	1. Short term: presented to Meta-Agent
	2. Consensus memory: To be added to Task State. This is to be read and modified by the actions.
	3. Long Term: [[RAG]] or similar [[Memory System]]
### Creation
[[USEAgent]] was created from the open source agent [[AutoCodeRover]] but since it followed a fixed workflow, it was not generalizable. The phases in the [[AutoCodeRover]] has been repurposed into the actions in the [[USEAgent]]. 
#### Actions
![[Pasted image 20261114005327.png]]

- TestRetreival and ExecuteTests are new additions to the actions
- Finish (Terminate) is also new and invoked to finish the 