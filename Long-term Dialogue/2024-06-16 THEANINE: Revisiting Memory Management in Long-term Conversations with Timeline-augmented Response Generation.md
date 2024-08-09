# Abstract
- memory-augmented response generation in the era of LLMs
- THEANINE, a framework that augments LLMs’ response generation with memory timelines
- TeaFarm, a counterfactual-driven question-answering pipeline addressing the limitation of G-Eval in long-term conversations
  - 내가 아는 response generation task가 아닌가?
 
# Introduction
- LLM의 Large windows attention을 써도 최근 utterance의 영향이 큼
- 대안
  - condense past conversation summarization &rarr; argument response generation
    - 문제: growing span of memories can hinder the quality of memory retrieval
    - updating older memory 해도 information loss
- 제안
  - THEANINE
    - a framework of timeline-augmented c hain-of-thought reasoning for response generation in long-term conversations.
    - graph structure
    - Phase 1: memories are linked based on how they relate to each other
      - LLM을 이용한 dynamically link memory, based on the temporal and cause-effect commonsense relations
    - Phase 2: retrieve whole memory timeline
    - Phase 3: response generation
      - LLM의 CoT reasoning ability 사용
- Contribution
  - THEANINE: 이전 대화 referring 잘함
  - Teafarm: counterfactual driven question answering pipeline
  - TeaBag: MSC, CC를 이용해 만든 데이터셋

# Methodologies
## Memory Graph Construction (Phase I)
![image](https://github.com/user-attachments/assets/d06b63e6-020a-4fba-9818-7bdaf0900854)
### Phase I-1: Identifying associative memories for memory linking

### Phase I-2: Relation-aware memory linking

- “how does an event affect the other?” or “why did this person make that change?”
- chronological order
- cause-effect commonsense relation, along with their temporal order
  - HinderedBy, Cause, Want, and 4 more
- 새로운 memory가 들어오면 LLM은 relation을 assign 함.
-  
## Timeline Retrieval and Timeline Refinement (Phase II)

## 2.3 Timeline-augmented Response Generation (Phase III)
