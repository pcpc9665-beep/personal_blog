# 📋 Pre-Project Research Framework

## 🔹 Track 1: Evaluating a General Project Idea
*Ask these questions to define the scope, feasibility, and architecture of a standard software or hardware project.*

### 1. Core Problem & Value
- [ ] **What specific problem does this project solve?** (Is it a pain point for you, or is it for a target audience?)
- [ ] **Who is the end user?** (Myself, a specific niche of people, or the general public?)
- [ ] **Has this been built before?** (If yes, what will make my version different or better? If it's a clone, what am I trying to learn from it?)

### 2. Technical Scope & Architecture
- [ ] **What is the absolute Minimum Viable Product (MVP)?** (What are the 2-3 core features that *must* work for this project to be useful?)
- [ ] **What is my Tech Stack?** (What frontend, backend, and database technologies will I use? Am I using tools I know, or learning something new?)
- [ ] **How will data flow through the application?** (Where is data created, how is it processed, and where is it stored?)

### 3. Constraints & Definition of Done
- [ ] **What are my biggest technical unknowns?** (What feature have I never built before that could block my progress?)
- [ ] **What is my timeline?** (How many hours per week can I realistically dedicate, and when do I want to finish Version 1?)
- [ ] **What does "Done" look like?** (What is the exact checklist of features that signifies the project is complete?)

***

## 🤖 Track 2: Evaluating an AI-Specific Project
*Ask these deeper questions if your project relies on Machine Learning, Large Language Models (LLMs), computer vision, or data science.*

### 1. Data & Feasibility
- [ ] **Why does this project need AI?** (Can this problem be solved faster and cheaper with traditional coding, rules, or if/else logic?)
- [ ] **Where will the data come from?** (Do I have an existing dataset, will I scrape it, or will I rely on a pre-trained model's internal knowledge?)
- [ ] **What is the data privacy risk?** (Will users be inputting sensitive data that shouldn't be sent to public third-party AI APIs?)

### 2. AI Architecture & Integration
- [ ] **What level of AI am I building?** 
  * *Level 1:* Wrapper (Using an API like OpenAI/Anthropic via prompting)
  * *Level 2:* RAG (Retrieval-Augmented Generation linking an LLM to a custom vector database)
  * *Level 3:* Fine-Tuning (Training an existing model on specific niche data)
  * *Level 4:* Custom Model (Training an architecture from scratch)
- [ ] **How will I handle AI inconsistencies?** (How will the app handle "hallucinations," wrong answers, or unexpected outputs without breaking the system?)
- [ ] **What are the token or hosting costs?** (If using APIs or renting GPUs, how much will it cost to run this project during development and after launch?)

### 3. Evaluation & Guardrails
- [ ] **How will I measure accuracy?** (How do I test if the AI is actually performing well?)
- [ ] **What safety guardrails are required?** (How do I prevent the AI from generating inappropriate content or system prompts from being leaked via prompt injection?)
