1. Zettelkasten memory for Agents
2. What is Zettelkasten method and why you should care about it?
	1. example of importance of linking notes (maybe example of CNN or idea of user likes black coffee, user has acid reflux, acid reflux should also connect to black coffee)
	2. particular method of note taking where atomic notes are connected with links
	3. my connection with Zettelkasten (obsidian pic)
3. Why Agents using Zettelkasten method is a good idea? (bean cheating meme)
	1. Why Agents need memory? (ghajini pic)
	2. Current memory management systems
		1. RAG
		2. other memory systems
	3. Shortcomings of current memory systems
		1. the new memory is not being influenced by the old ones and vice versa
	4. how Zettelkasten solves this
		1. connect separate notes (link generation)
		2. incorporate new info into existing memory (memory evolution)
	5. transition(sword giving meme)
4. What type of problem are we trying to solve (the datasets) (pic of swordman in front of peasants, knights etc)
	1. example of each type of questions (singlehop, multihop etc)
	2. Example of dialsim
5. How Agents would use Zettelkasten? (pic of swordman using a sword wrong)
	1. note construction (KGX creation)
	2. link generation 
	3. memory evolution
	4. Retrieval
6. Results
	1. Comparison table
	2. implementation details
	3. performance analysis
7. Why this method works?
	1. clustering in vector representation
	2. why LG useful (ablation study)
	3. why ME useful
	4. scaling analysis
8. Conclusion
	1. impact
	2. limitations
9. my comments on the paper
	1. Why no comparison with mem0?
	2. Does not publish the cost of making the memories
	3. Why ablation study one sided? 
	4. Why hyperparameter k is tuned for each dataset?
	5. Minor queries:
		1. PS2 not outputting links
		2. How atomicity of memories is checked (embedding input limit)
		3. why k,g,x are differentiated?