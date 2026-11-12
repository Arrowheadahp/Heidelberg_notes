[[Q-Learning]] [[Universal Update Template]] is $$ R_{t+1} + \gamma \max_a Q(S_{t+1}, a)$$
Which can be broken up into 2 steps:
$$
A^* = \arg\max_a(Q(S_{t+1},a))
$$
$$ \max_a Q(S_{t+1},a) = Q(S_{t+1}, A^*)$$
Since $A^*$ may have the bias, we can use a different Q to get the $Q(S_{t+1}, A^*)$. 

The idea is to maintain 2 Qs separately and update them separately and symmetrically use them. This will remove the bias. 
$$
A^* = \arg\max_a(Q_1(S_{t+1},a))
$$
$$ Q_2(S_{t+1}, A^*)$$
The Qs are updated in such a way that $Q_1$'s target becomes $$Q_1 \to  R_{t+1} + \gamma \max_a Q_2(S_{t+1}, a)$$. Same for $Q_2$.$$Q_2 \to  R_{t+1} + \gamma \max_a Q_1(S_{t+1}, a)$$
Only 1 of these happens with probability 0.5

### Pseudocode
- Initialize Q1, Q2 so that terminal states have value 0
- Loop for each episode
	- Initialize S
	- Loop till done
		- Choose A from Q using $\varepsilon$-greedy policy to Q1+Q2
		- Take action A to get R and S'
		- if rand < 0.5:
			- $A^* \gets \arg\max_a Q_1(S',a)$
			- $Q_1[S,A] \gets Q_1[S,A] + \alpha(R + \gamma Q_2(S', A^*)-Q_1[S,A])$
		- else:
			- $A^* \gets \arg\max_a Q_2(S',a)$
			- $Q_2[S,A] \gets Q_2[S,A] + \alpha(R + \gamma Q_1(S', A^*)-Q_2[S,A])$
		- $S\gets S'$

- Initialize Q1, Q2 so that terminal states have value 0
- Loop for each episode
	- Initialize S
	- Loop till done
		```            
		  a = eps_greedy(Q1+Q2, s, epsilon, env.n_actions, rng_local)
		  s_next, r, done = env.step(a)
		  total_r += r
		  if rng_local.random() < 0.5:
			  Q1[s, a] += alpha* (r + gamma* Q2[s_next, np.argmax(Q1[s_next])] - Q1[s, a])
		  else:
			  Q2[s, a] += alpha* (r + gamma* Q1[s_next, np.argmax(Q2[s_next])] - Q2[s, a])
		  s = s_next
		  ```
		  