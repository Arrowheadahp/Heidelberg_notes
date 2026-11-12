## Unified Software Engineering Benchmark
There was a need for a set of automated software engineering tasks which can be used to test all purpose AI software engineers. 
The benchmarks that previously exists check only specific things. [[USE-Bench]] combines 4 such specialized benchmarks under the same unified interface for agentic interaction with unified benchmark under single API.
1. [[SWE-Bench]] verified: Bug fixing, feature editing
2. SWT: Validation
3. [[REPOCOD]]: Code Generation
4. [[REPOTEST]]: Test coverage

![[Pasted image 20261112082332.png]]

Even though each part of the process is being benchmarked individually, they can be combined to test more complex Software Engineering tasks. 
Ex: incomplete fix = 
1. test the code and find failing tests
2. generate fix for failing tasks
3. test fixed code for more failing tests
4. generate fixed code which passes all tests