Improving on [[Rollout Algorithm]] to get focus on promising branches. MCTS also does backup of the estimations.

- Per iteration:
	- Select:  from the root and descend using the existing policy
	- Expand: Add one new node
	- Simulate: Rollout from it to the end
	- Backup

After the budget, pick the action $$ A\gets \arg \max_a N(s_0, a)$$
- The policy already uses Q during search
- Promising moves keep attracting simulations so high N is a robust signal
- High Q on few visits may just be lucky

Then move on:
- Execute the action A
- Observe s', r from environment
- ==Reuse==  the subtree under the move taken as the new root then replan from s'.

