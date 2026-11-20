1. A-MEM: Agentic Memory for LLM Agents
2. Author, citations, venue etc
3. Why this paper?
   one of the first papers that connected new memories. Personal connection with Zettelkasten method 
4. Outline
5. The problem: 
	   Keeping every memory in context is expensive and slow. Therefore there is a need for a relevant memory storage and retrieval system.
6. Existing solution: 
	1. RAG with an example
	2. Other memory systems
	3. Shortcomings of these memory systems: static, reliance on predefined relationships, limits adaptability, unable to forge innovative connections
7. Hypothesis: 
	   Use the Zettelkasten method to store memory. 
	1. What is Zettelkasten method and why you should care about it?
	   Importance of linking notes (with example)
	2. Why this may be a good idea?
		1. Finding relevant information becomes much easier. Adaptive, able to forge innovative connections
		2. Difference between existing and A-Mem
8. Methodology
	1. note construction (KGX creation) 
		1. example
		2. problem: $c_i$ is not well defined, encoder has token limit, K, G, X has no individual need.
	2. link generation 
		1. example
		2. problem:  $P_{s2}$ only determines if the new memory should be evolved or not
	3. memory evolution
		1. example
		2. good: the old memories are updated/strengthened/pruned/ no change dynamically
	4. Retrieval 
		1. example:
		2. problem: cosine retrieval is not optimal, we want answers, not memories closest to questions (should rerank). does not talk about using L (links) for retrieval. 
9. Testing
	1. Datasets
		1. example of each type of questions (singlehop, multihop etc)
		2. Example of dialsim
	2. Results
		1. Implementation details
		   problem: 
			1. the models are old and bad
			2. parameter k is adjusted for specific categories (This is illegal)
		2. Evaluation:
			1. F1 score
			2. Bleu score
			3. problem: (not semantic)
		3. Comparison table
		   problem:
			1. some differences are not significant
			2. comparison with mem0 is not present
		4. 