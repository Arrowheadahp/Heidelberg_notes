The idea is to prioritise the state actions where there is a large change by maintaining a priority queue of state action pairs $(S_t, A_t)$ according to $$R_{t+1} + \gamma \max_a (Q(S_{t+1}, a)) - Q(S_t, A_t) $$
After updating one pair, examine its predecessors and push the important predecessors into the queue

### Algorithm
- Initialize 
	- Q(s, a)
	- Model(s, a)
	- `PQueue = []`
- Loop forever:
	- $S\gets$ current non terminal state
	- $A \gets \pi(S)$
	- execute $A$ and observe $R, S'$
	- $Model[S, A]\gets (R, S')$
	- $P\gets R + \gamma \max_a (Q(S', a)) - Q(S, A)$
	- if $P>\theta$ :
		- Insert $(S, A)$ into PQueue with priority P
	- Loop till PQueue is empty:
		- $S,A \gets PQueue.pop()$
		- $R, S' \gets Model(S,A)$
		- $Q(S, A) \gets Q(S, A) + \alpha(R + \gamma \max_a (Q(S', a)) - Q(S, A))$
		- for all S'', A'' predicted to lead to S, A:
			- $R\gets$ predicted reward
			- $P\gets R + \gamma \max_a (Q(S', a)) - Q(S, A)$
			- if $P>\theta$ :
				- Insert $(S, A)$ into PQueue with priority P