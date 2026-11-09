## A-Mem Agentic Memory for LLM Agents
#paper
link: https://arxiv.org/pdf/2502.12110
[[Presentation outline AMem]]
### Abstract
[[LLM]] require [[Memory System]] to store and retrieve knowledge. Current [[Memory System]] use fixed operations and structures which limit adaptability across diverse tasks. This paper proposes a novel [[Memory System]] that follows Zettelkasten method which dynamically links memories and enables memory evolution, solving the adaptability issue.
### Introduction
[[LLM]] still needs [[Memory System]] to provide long-term interaction ability with external environment. Existing [[Memory System]]: [[Mem0]] that follows principles of [[RAG]], while providing structured organization, rely on predefined schemas and relationships that limit their adaptability. This inability to forge innovative connections or patterns results in failure to generalize across new environments and maintain long term interactions.
This paper introduces a novel [[Memory System]] that enables dynamic memory structuring through autonomous and flexible [[Memory System]] for [[Agent]].
This enables:
1. autonomous generation of contextual descriptions (Semantic attributes)
2. dynamic establishment of memory connections (link generation)
3. intelligent evolution of existing memories (memory evolution)
It provides testing data to compare performance across 6 models using 6 different metrics that shows significant improvements. [[T-SNE]] visualization also included to illustrate the structured organization of [[A-MEM]].

### Related Work
#### Memory for LLM Agents
Current [[Memory System]]:
- [[MemGPT]]
- [[LoCoMo]]
- [[ReadAgent]]
- [[MemoryBank]]
These are the systems that were tested against [[A-MEM]]. 
#### [[RAG]]: Retrieval Augmented Generation
The process includes: indexing documents into chunks, retrieving relevant chunks based on semantic similarity, augmenting LLM's prompt into the retrieved context for generation. [[Mem0]] was not compared against it. 
This [[Memory System]] has its agency (uses the LLM's capability) during the retrieval phase whereas [[A-MEM]] has its agency during the storage and evolution phase.
### Methodology
The whole memory is stored as $\mathcal M=\set{m_1...m_n}\forall m_i=\set{c_i, t_i, K_i, G_i, X_i, e_i, L_i}$
- $m$ is each atomic note
- $c$ is the original content
- $t$ is the timestamp
- $K$ is keywords (LLM Generated)
- $G$ is tags (LLM Generated)
- $X$ is context description (LLM Generated)
- $e$ is embeddings created by [[Sentence Embedding]]
- $L=\set{m_a...m_b}$ is the list of links to other memories.
Prompts:
- $Ps1$ is the prompt to generate the semantic attributes
- $Ps2$ is the prompt to generate the semantic links between new memory and existing memories
- $Ps3$ is the prompt to generate the 

4 phases
#### 1. Note Construction
For each new input content $c,t$, $$K, G, X \gets LLM(c, t, Ps1)$$ $$e=f_{enc}[concat(c,K,G,X)]$$


#### 2. Link Generation
1. Calculate similarity score for each existing memory: $$s_{i,j}=\frac{e_i\cdot e_j}{|e_i||e_j|}$$
2. Find max k value memories. This acts as a filter to increase efficiency while maintaining relevance. $$\mathcal M_{near}^i=\set{m_j:rank(s_{i,j})\le k} $$
3. Generate semantic links between new memory and existing memories. This allows nuanced understanding, identify subtle patterns, causal relationships and conceptual connections$$L\gets LLM(m_i,\mathcal M_{near}^i, Ps2) $$
#### 3. Memory Evolution
The novel step for [[A-MEM]]. Each memory in $\mathcal M_{near}^i$ is determined if it is updated because of the new memory or not. Only $K,G,X$ are updated if so. $$m_j*\gets LLM(m_i,\mathcal M_{near}^i, Ps3)$$
#### 4. Retrieve Relative Memory
For prompt $q$
1. it is embedded $$e_q=f_{enc}[q]$$
2. Calculate similarity score for each existing memory: $$s_{q,j}=\frac{e_q\cdot e_j}{|e_q||e_j|}$$
3. Find max k value memories. This acts as a filter to increase efficiency while maintaining relevance. $$\mathcal M_{near}^q=\set{m_j:rank(s_{q,j})\le k} $$
4. $\mathcal M_{near}^q$ is returned
### Experiment
#### Dataset and Evaluation
For testing, the LoCoMo dataset was used which has 35 sessions averaging over 9k tokens. It has diverse question types:
1. single hop questions from single session
2. multi-hop questions from multiple session
3. temporal reasoning testing time related information
4. open knowledge questions requiring integration of knowledge question with external knowledge
5. adversarial questions assessing model's ability to identify unanswerable queries.
#### Implementation Details
The hyperparameter value of k is used as 10 and ==🔴adjusting this parameter for specific categories==. For text embedding, all-minilm-16-v2 model is used.
#### Empirical Results
Great but some are too close for the randomness from LLM. The error rates are not given. 
Cost efficiency Analysis: 
Much less tokens used during retrieval. 
==🔴The cost of adding new memories is not given.==
#### Ablation Study
Link Generation(LG) and Memory Evaluation(ME) are the main parts. LG without ME does not work well. ==🔴ME without LG was not tested==.
#### Scaling Analysis
All compared [[Memory System]] have Data complexity: O(N). The (K,G,X, L) do not take much data. 
#### Memory Analysis
In the T-SNE Visualization using embeddings, the clustering is more organized. Since the embedding used is same as the one used in [[A-MEM]], of course it is going to be more organized there. There is no measurement of structuredness and baseline is from what is not known.
### Conclusion
### Limitations
1. Quality of linking heavily depends on the quality of LLM. (LLM may hallucinate).
2. Future work can be exploring the multimodal information.