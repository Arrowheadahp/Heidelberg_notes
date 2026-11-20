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
		2. problem: 
	4. Retrieval 
		1. example:
		2. problem: cosine retrieval is not optimal. does not talk about using L (links) for retrieval. 