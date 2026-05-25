   final for n episodes: $$v_\pi(s) = \frac{1}{n}\sum_{i=1}^n G_1(s)$$Algorithm:
- Generate an episode with policy $\pi$.
- for each state that appears in the episode:
	- let G be the [[Return]] after the first visit to state s.
	- Append G to Returns\[s\]
- $V[s] \gets average[Returns[s]]$

for fixed policy $\pi$, $v(s)$ converges as $n\to\infty$  