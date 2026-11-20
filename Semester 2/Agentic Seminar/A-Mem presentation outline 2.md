https://www.semanticscholar.org/paper/A-MEM%3A-Agentic-Memory-for-LLM-Agents-Xu-Liang/1f35a15fe9df43d24ec6ea551ec6c9766c17eccf


1. A-MEM: Agentic Memory for LLM Agents
2. Author, citations, venue etc
3. Why this paper?
   one of the first papers that connected new memories. Personal connection with Zettelkasten method.
4. Outline
5. The problem: 
	   Keeping every memory in context is expensive and slow. Therefore there is a need for a relevant memory storage and retrieval system.
6. Existing solution: 
	1. RAG: Quick primer with an example
	2. Other memory system
		1. Mem0
		2. MemoryBank
		3. Readagent
		4. MemGPT
	3. Shortcomings of these memory systems: static, reliance on predefined relationships, limits adaptability, unable to forge innovative connections
7. Inspiration: 
	   Use the Zettelkasten method to store memory. 
	1. What is Zettelkasten method and why you (your agent) should care about it?
		1. memory as a sequence vs memory as a graph 
		2. Importance of linking notes (with example)
		3. delegating compute form read time to write time
	2. Why this may be a good idea?
		1. Finding relevant information becomes much easier. Adaptive, able to forge innovative connections
		2. Difference between existing and A-Mem
8. Methodology
	1. note construction (KGX creation) 
		1. example
		2. problem: $c_i$ is not well defined, encoder has token limit, No ablation shows which of KGX matters, could have been combined.
	2. link generation 
		1. example
		2. problem: Shipped $P_{s2}$ only determines if the new memory should be evolved or not. it is not a link generating prompt.
	3. memory evolution
		1. example
		2. good: the old memories are updated/strengthened/pruned/ no change dynamically
	4. Retrieval 
		1. example:
		2. problem: cosine retrieval is not optimal, we want answers, not memories closest to questions (should rerank). does not use L (links) directly for retrieval. 
9. Testing
	1. Datasets
		1. example of each type of questions (singlehop, multihop etc)
		2. Example of dialsim
	2. Results
		1. Implementation details
		   problem: 
			1. the models are old and have very small context windows. 
			2. parameter k is adjusted for specific categories (This is illegal)
		2. Evaluation:
			1. F1 score
			2. Bleu score
			3. problem: answer equivalence is not checked (not semantic)
		3. Comparison table
		   problem:
			1. some differences are not significant (too small gap)
			2. single run (no error bars)
			3. comparison with mem0 is not present
			4. comparison with proper baseline (no memory) not present
			5. comparison with full memory in context not present
		4. Performance Analysis
			1. Cost Efficiency
				1. Retrieval cost reduced 
				2. The memory generation cost is not shown
			2. Memory Usage (linear memory scaling)
			3. Retrieval time analysis
				1. write time not shown
	3. Why is it working?
		1. Memory analysis: Clustering in vector representation
		   problem: not making sense. clusters artifact of visualization, no quantitative measure
		2. Why LG important (Ablation study)
		3. why ME important (not studied)
10. Conclusion
	1. Impact: 
		1. This is one of the first papers to link memories
		2. citation count
		3. pave way for more advanced memory systems
	2. Limitations
		1. heavily dependant on the quality of the LLM that creates the memories
		2. any misinformation added by LLM propagates
		3. no versioning, correction, rollback mechanisms
11. My thoughts:
	1. the idea is novel and good. it is now a standard practice in memory systems to create connections between memories
	2. The code that came with the paper gives the true methodology and not the paper
	3. None of the critiques are for the idea, only the methodology and representation.
12. Questions?