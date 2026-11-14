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

The significant number of solutions (218) are checked manually and 1.3% is memorized (exact copy of answers) and 10.5% overfitted (suspiciously similar results) to ground truth. This is a reduction in rate of overfitting from previous agents like SpecRover (31%). This reduction is attributed to new action: ExecuteTests. 
#### 3. Self Configuration: 
Can [[USEAgent]] self configure to give better efficacy on different task types? How good are the new actions?
Yes it is capable of choosing different action patterns for different tasks. 
![[Pasted image 20261114185803.png]]

#### Ablation study: 
How important is the Meta-Agent and an individual action![[Pasted image 20261114190236.png]]

- Disable dynamic is disabling the dynamic decision making and going through a predefined workflow. 
- For individual action, ExecuteTests was removed from the action pool and tested.
#### 4. Open Challenges
What are the challenges that [[USEAgent]] faced while solving the tasks?
1. **Natural Language Ambiguity**:
   When the tasks requires a large amount of code, it generates solutions that are mostly correct. They miss some edge cases that are not specified clearly in the task description. 
   **Solution**: 
	1. Creating more formal artifacts such as specifications and test cases.
	2. Having a human agent interaction schemas to clarify ambiguity
2. **Lack of Backtracking to try different approaches**:
   The agent keeps trying to make small edits to partial patches even though it may not be possible to craft a good solution at that location.
   **Solution:**
	1. Check Execution traces and decide whether to backtrack.
3. **Overfitting Tests:**
   When the solution passes the given tests but the requirements are not met. This is an issue with the benchmark itself and the tests should be generalized.
   Solution:
	1. adding more actions like test amplification and mutation testing.
	2. making the benchmark tests more generalized