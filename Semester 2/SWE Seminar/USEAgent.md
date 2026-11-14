## Unified Software Engineering Agent
### Inception:
[[USEAgent]] or Unified Software Engineering Agent is a novel agent that is created to tackle all problems that Software Engineers face. 
This is created to be the Second step in the development of AI Software Engineer. The first step (Existing agents) was the creation of the individual agents for single tasks. 
### Idea
To create the a Software Engineering Agent to be unified, it needs to be versatile. So the fixed workflow will not work. The idea is to have a ==Meta-Agent==, a reasoning LLM agent that will orchestrate various ==Actions==. Together they create the [[USEAgent]].
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
- Finish (Terminate) is also new and invoked to finish the run
These actions can be invoked multiple times.
#### Task State
This is the consensus memory among the actions.$$S=\set{L_c,L_t,R_{exec},DS}$$
- $L_c\to$ relevant code locations
- $L_t\to$ test locations
- $R_{exec}\to$ execution results
- $DS\to$ diff stored (modifications to program code and test code)
#### Meta-Agent
This orchestrates the actions and chooses which one to take using 
1. Current Task State
2. Overall Task Description
3. Output from previous task
At the beginning the Meta-Agent chooses an action from the task description and an empty task state and iteratively chooses an action to execute. Each action invoked modifies the task state and returns it back to the Meta-Agent. This creates the [[ReAct]] loop. After finding a satisfying solution, the Finish action is taken and the solution is output. If it reaches a pre-defined limit of iteration, it ends and outputs one of the candidates from the diff store.