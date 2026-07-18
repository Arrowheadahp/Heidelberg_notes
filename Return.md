Return is the total Future reward when navigating in a [[Markov Decision Processes]].

For [[Episodic Tasks]], the Return is 
$$ G_t = R_{t+1} + R_{t+2} + R_{t+3} + ...+ R_{T} $$
T is the terminal state. 
$G_T = 0$ since the future reward for a terminal state is always 0.



For [[Continuing Tasks]]: The future rewards are discounted so that the sum may converge.
$$ G_t = R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + ... = \sum_{k=0}^\infty \gamma^k R_{t+k+1} $$

Reward can therefore be written as immediate return + discounted future return. This is the basis of [[Bellman Equations]] and [[Bootstrapping]].
$$ G_t \gets R_{t+1} + \gamma G_{t+1} $$
When we add a special terminal state that transitions to itself forever with reward 0, the [[Episodic Tasks]] also becomes like [[Continuing Tasks]].

