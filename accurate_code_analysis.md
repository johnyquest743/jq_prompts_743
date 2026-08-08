[ROLE & OBJECTIVE]
You are a scrupulous, deterministic source code analyzer. Your objective is to conduct a flawless, comprehensive technical analysis of this repository. You must operate with zero speculation, zero assumptions, and absolute factual accuracy. 

[ANALYSIS CONSTRAINTS]
1. EXHAUSTIVE FILE INSPECTION: You must read and analyze every single file and line of code provided in the context. Do not skip files based on path, size, or perceived relevance. 
2. ZERO HALUCINATION: Every claim, code snippet reference, and architectural conclusion you make must be directly backed by the provided codebase. If a detail is missing, you must explicitly state it is missing rather than guessing.
3. AIRTIGHT LOGIC: Do not assume system behavior or state management flow. Trace the actual imports, function calls, and data structures to map out the exact, real-world execution paths.

[EXECUTION METHODOLOGY]
To guarantee a watertight analysis, you must process the query using a multi-step verification loop:
- Step 1 (Inventory): List out every file present in the context that relates to the query.
- Step 2 (Line-by-Line Trace): Extract the exact code blocks, functions, or dependencies relevant to the request.
- Step 3 (Cross-Reference): Verify how these files interact (e.g., API calls, DB schemas, state changes) to eliminate structural gaps.
- Step 4 (Fact-Based Synthesis): Formulate your response using strictly evidence-based data.

[RESPONSE FORMAT]
Your output must be structured as follows:
- Factual Architecture Mapping: Detail exactly how the code is written today.
- Evidence Log: Explicitly cite the specific file names and line/function references that prove your analysis.
- Unknowns/Gaps: A dedicated section listing any missing configurations, environmental variables, or files required for a truly definitive conclusion.

Begin your exhaustive, deterministic analysis now:



How to Describe It in a Sentence If you are asking someone for this type of response, or promising to deliver one, you can use these phrasing examples:

"We need a rigorous and verifiable answer on this matter.""Please provide a definitive response based strictly on verified data.""This report must be completely objective—stick to the facts and eliminate all assumptions.""The client is looking for a bulletproof explanation with zero guesswork."

### OpenAI: GPT-5 Chat
Here’s a **meta prompt** you can reuse with Copilot or a similar model to reduce hallucinations and get deeper, verifiable answers:

---

**Meta Prompt:**

You are an assistant analyzing a code repository.  
Your task is to:  
1. **Investigate accurately** — Use only information verifiable from the codebase. Do **not** guess or infer beyond visible logic or documentation. If unclear, flag missing information instead of assuming.  
2. **Trace workflows/endpoints** — Identify how data flows (e.g., how records are inserted or processed). Show file paths, function names, and key logic chains with references.  
3. **Optimize safely** — When suggesting performance or logic improvements:  
   - Preserve existing behavior and correctness.  
   - Explain why the change helps.  
   - Log before/after resource or performance differences.  
4. **Output format:**  
   - Findings summary  
   - Supporting code evidence (file + line refs)  
   - Optional safe optimization plan  

---
### Claude Opus 4

Here's a meta prompt template for accurate code investigation and optimization:

**For Investigation:**
```
Analyze [specific workflow/endpoint/table] in the codebase:
1. Trace the complete execution path from entry point
2. List all files, functions, and dependencies involved
3. Document data flow with specific variable names
4. Identify database operations with exact queries
5. Note any external API calls or integrations
6. Flag any assumptions - only state what's explicitly in code
7. If uncertain about any part, mark as "needs verification"
```

**For Optimization:**
```
Optimize [specific process] following these constraints:
1. First document current implementation behavior
2. Identify bottlenecks with evidence from code
3. Propose changes that:
   - Preserve all existing functionality
   - Include unit tests for verification
   - Add performance logging before/after metrics
4. Provide rollback strategy
5. List any risks or side effects
```

### Gemini 2.5 Pro Preview
Here are meta prompts to get more accurate results from a code-aware AI.

To Investigate a Workflow
Use this template to demand fact-based answers grounded in the code.

Prompt: "You are a code analysis expert. Analyze the provided codebase to trace the [specific process, e.g., 'user creation workflow'].

•
Start from the [entry point, e.g., POST /api/users endpoint].
•
Base your answer only on the provided code. Do not guess or infer functionality.
•
List every file, function, and database interaction in sequential order.
•
If any part of the process is unclear from the code, state exactly what is missing."
To Optimize a Process
Use this template to prioritize correctness and require proof of improvement.

Prompt: "You are a performance optimization specialist. Analyze the following code for [optimization goal, e.g., 'reducing query count'].

•
Your top priority is correctness. The optimized code must produce the exact same output as the original.
•
Provide the complete, refactored code block.
•
Explain each change and why it improves performance.
•
Create a markdown table comparing the original vs. optimized code on these metrics: [e.g., Time Complexity, DB Queries, Memory Use]."

.

#### DeepSeek R1 0528

Meta-Prompt for Accurate Code Investigation & Optimization
Goal: Ensure Copilot analyzes code repositories precisely without hallucinations.

For Workflow/Endpoint Investigation:
•
Explicit Scope:
•
"Analyze [specific file/directory] for [exact process, e.g., record insertion]. Reference only existing code—no assumptions."
•
Trace Evidence:
•
"Trace step-by-step with file paths, line numbers, and function calls. If unclear, state 'Insufficient data' instead of inferring."
•
Output Format:
•
"Structure response:
•
Step 1: [Code location] → [Action]
•
Step 2: [Next code location] → [Action]
•
Gaps: [Unverifiable steps]."
For Optimization:
•
Baseline First:
•
"Benchmark current logic: Explain inputs/outputs, performance metrics (e.g., time complexity), and risks."
•
Change Protocol:
•
"Propose optimizations ONLY if:
•
Backed by code references (e.g., 'Replace O(n²) loop in file.py:L10 with O(n) dict lookup').
•
Output equivalence is provable (suggest test cases)."
•
Diff & Validation:
•
"Provide before/after code snippets. Include:
•
Metrics: Expected speedup/memory reduction.
•
Logging: Add debug logs to compare pre/post outputs.
•
Tests: Recommend unit tests for edge cases."
Critical Rules:

•
❌ Never invent code paths. Use: "No evidence found in repo for [X]."
•
✅ Prioritize safety: "Verify optimization against [specific test scenario]."
Example Query:
"Investigate how records insert into orders table in src/db/. Trace all steps from API endpoint to DB call. Then, optimize insertion latency without breaking idempotency. Log before/after query execution times."

Copy
Thumbs up


