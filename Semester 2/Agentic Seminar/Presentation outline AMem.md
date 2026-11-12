1. What is Zettelkasten method
	1. example of importance of linking (maybe example of CNN)
	2. particular method of note taking where atomic notes are connected with links
	3. my connection with Zettelkasten (obsidian)
2. Why Agents using Zettelkasten method is a good idea?
	1. Why Agents need memory?
	2. Current memory management systems
	3. Shortcomings of current memory systems
	4. how Zettelkasten solves this
3. How Agents would use Zettelkasten?
	1. note construction
	2. link generation
	3. memory evolution
	4. Retrieval
4. What type of problem are we trying to solve (the datasets)
	1. example of each type of questions (singlehop, multihop etc)
	2. Example of dialsim
5. Results
	1. Comparison table
	2. implementation details
	3. performance analysis
6. Why this method works?
	1. clustering in vector representation
	2. why LG useful (ablation study)
	3. why ME useful
	4. scaling analysis
7. Conclusion
	1. impact
	2. limitations
8. my comments on the paper
	1. Why no comparison with mem0?
	2. Does not publish the cost of making the memories
	3. Why ablation study one sided? 
	4. Why hyperparameter k is tuned for each dataset?
	5. Minor problems:
		1. PS2 not outputting links
		2. How atomicity of memories is checked (embedding input limit)
		3. why k,g,x are differentiated?