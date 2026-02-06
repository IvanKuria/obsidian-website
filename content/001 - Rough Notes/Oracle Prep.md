- based off reddit posts [1](https://www.reddit.com/r/csMajors/comments/1q7ossi/oracle_swe_intern_interview_advice/), [2](https://www.reddit.com/r/csMajors/comments/1pojgwo/oracle_oci_swe_intern_firstround/), they tend to ask leetcode easy/mediums specifically in strings, stack, bst, and linked lists so that's what i need to really prep for in the next week.(maybe converting decimal to binary)
- brush up on OOP(inheritance, encapsulation, polymorphism, etc...) and what that looks like in java and python

# Oracle AI / SWE Intern Interview – 1 Week Prep Plan

**Assumption:** Interview in ~7 days  
**Daily commitment:** ~5 hours  
**Goal:** Be strong in **RAG fundamentals**, **applied system design**, and **articulation**, not ML theory.

---

## High-Level Strategy

You do **not** need to:
- Master ML theory
- Read all of *Designing Data-Intensive Applications*
- Learn every RAG framework

You **do** need to:
1. Explain RAG end-to-end clearly
2. Reason about simple AI system design
3. Tie everything back to your IBM experience
4. Speak confidently about tradeoffs

> Clarity > breadth > buzzwords

---

## Daily Structure (Recommended)

- **2h** – YouTube (watch + notes)
- **1.5h** – Reading (selective)
- **1h** – Talk out loud / write explanations
- **0.5h** – Review + tighten answers

⚠️ Talking out loud is critical.

---

## Day 1–2: RAG Fundamentals (Non-Negotiable)

### Goal
Be able to explain RAG **clearly and calmly** without buzzwords.

---

### YouTube (Watch in Order)

1. **Harrison Chase – “RAG Explained”**  
   Search: `Harrison Chase RAG explained`

2. **AssemblyAI – “How ChatGPT Retrieval Works”**

3. **Pinecone or Weaviate – “Vector Databases Explained”**

Focus on **flow**, not tools.

---

### Must-Be-Able-To Explain

> A RAG system ingests documents, chunks them, embeds them into a vector database, retrieves relevant chunks at query time, and injects them into the prompt so the LLM answers grounded in source data.

Breakdown:
- Ingestion
- Chunking (size tradeoffs)
- Embeddings
- Vector search
- Prompt construction
- Generation
- Evaluation

---

### Reading (Skim Only)

**O’Reilly – Data Engineering Book**
- Data ingestion
- Batch vs streaming
- Data quality

Skip heavy infra chapters.

---

## Day 3: RAG Failure Modes & Evaluation (High Signal)

### YouTube

1. **“RAG Failure Modes”** (LangChain / LlamaIndex talks)
2. **“Evaluating RAG Systems”** (Weaviate / Pinecone)

---

### Topics to Internalize

- Hallucinations
- Irrelevant retrieval
- Stale documents
- Latency

---

### Strong Talking Points

- Better chunking
- Metadata filtering
- Hybrid search (keyword + vector)
- Golden question evaluation
- Confidence thresholds / fallback responses

---

## Day 4: Light System Design (Beginner-Friendly)

### Mindset

They are **not** asking:
> “Design Facebook”

They *are* asking:
> “How would you build an AI assistant for customers?”

---

### YouTube

1. **Gaurav Sen – System Design for Beginners**
   - Watch only first 2–3 videos

2. **“Design an AI Assistant” walkthrough (any modern video)**

Ignore:
- Sharding
- CAP theorem
- Scaling math

Focus on:
- Components
- Data flow
- Tradeoffs

---

### Practice Design (Out Loud)

**Design an AI assistant for Oracle Cloud customers**

Include:
- Chat UI (frontend)
- Backend API
- RAG pipeline
- Vector database
- LLM
- Logging & monitoring
- Security (customer data isolation)

---

## Day 5: Map Everything to IBM Experience (Huge Advantage)

### Write This Down

- What problem you solved
- How data flowed
- What went wrong
- What you’d do differently today

---

### Practice 2-Min Explanation

They will ask:
> “Tell me about the AI assistant you worked on at IBM.”

You want:
- Structured
- Calm
- No rambling

---

## Day 6: Mock Interview + Gap Filling

### Answer These Out Loud

- What is RAG?
- How would you reduce hallucinations?
- How would you design an AI assistant for customers?
- What tradeoffs did you face at IBM?

Record yourself if possible.

---

### Review

- Where you ramble
- Where you’re vague
- Tighten explanations

---

## Day 7: Light Review + Confidence

- Rewatch 1–2 key videos
- Skim notes
- No cramming
- Sleep well

Confidence matters.

---

## What NOT to Do

- ❌ Don’t try to master DDIA
- ❌ Don’t memorize frameworks
- ❌ Don’t grind LeetCode
- ❌ Don’t panic about system design

---

## What a Strong Answer Sounds Like

> “At a high level, here’s how I’d approach it… here’s the tradeoff… here’s what I’d improve…”

## What a Weak Answer Sounds Like

> “I’d probably use LangChain and embeddings and transformers…”

---

## Final Reminder

This interview is about **applied reasoning**, not academic depth.

You are polishing — not catching up from zero.