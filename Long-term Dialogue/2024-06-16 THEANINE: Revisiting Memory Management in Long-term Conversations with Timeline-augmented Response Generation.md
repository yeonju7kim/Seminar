# 요약
- 메모리를 이용한 response generation
- TeaFarm이라는 어떤 평가 방식
- Motivation: LLM의 Large windows attention을 써도 최근 utterance의 영향이 큼
- 기존: 이전 대화 요약하고 이용, information loss
- 제안: HEANINE
  - COT, graph structure
  - Phase 1: 메모리 연결
    - temporal and cause-effect commonsense relations
  - Phase 2: 전체 메모리 타임라인을 얻음
  - Phase 3: response generation
    - LLM의 CoT reasoning ability 사용
- Contribution
  - THEANINE: 이전 대화 referring 잘함
  - Teafarm: counterfactual driven question answering pipeline
  - TeaBag: MSC, CC를 이용해 만든 데이터셋

# 구체적인 Methodologies
![image](https://github.com/user-attachments/assets/916124ca-80d7-47e6-a57e-e84c552457c2)

### Memory Graph Construction (Phase I)
![image](https://github.com/user-attachments/assets/d06b63e6-020a-4fba-9818-7bdaf0900854)
![image](https://github.com/user-attachments/assets/71db172f-2d25-40e3-83a8-a2501c2269f0)

- 연상 메모리(associative memories): 비슷한 event나 topic들로
- Relation-aware memory linking
  - 사람은 How does an event affect the other? why did this person make that change? 등으로 relation을 판단
  - cause-effect commonsense relation along with their temporal order
    - relation은 HinderedBy, Cause, Want, 4 more
    - 새로운 memory가 들어오면 LLM은 relation을 assign 함.
  
### Timeline Retrieval and Timeline Refinement (Phase II)
![image](https://github.com/user-attachments/assets/1c5ca061-34a8-4a16-ba67-9429cbf7ee48)

- Top-k memory retrieval
- retrieve raw memory timelines
- 

### Timeline-augmented Response Generation (Phase III)
