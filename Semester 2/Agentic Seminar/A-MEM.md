## A-Mem Agentic Memory for LLM Agents
#paper
link: https://arxiv.org/pdf/2502.12110

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
