# 실행군 G-D': 관찰자 통제 실행

# Experiment Group G-D': Observer-Controlled Experiment

## 실행 목적

## Objective

관찰자(observer)의 가입 유무에 따라 구조의 자기 반복성이 유지되거나 변화하는지를 확인한다. 관찰이 느낌 또는 결과 찾기 행위를 넘어, 구조 자체를 지속 또는 재현하는 **피드백 기능**을 지니는지를 검사한다.\
This experiment investigates whether the presence or absence of an observer influences the persistence of structural recurrence. It aims to test whether observation functions as a feedback mechanism that sustains or reproduces structures, rather than merely reading outcomes.

---

## 실행 회로 설계

## Circuit Design

- **회로 구성**: H(0) → CX(0, 1)\
  **Circuit**: H(0) → CX(0, 1) with measurement

- 동일 회로를 연속 10번 실행\
  Execute identical circuit 10 times in sequence

- 역할 협수: 측정 유무 및 훈후 구조 반복 동향\
  Key variable: presence of observation and its effect on structural recurrence

---

## 실행 조건

## Experimental Conditions

- **[조건 A] 관찰자 가입 있음 (With Observation)**\
  각 실행 후 결과를 기록 및 저장\
  Record and retain the results after each execution

- **[조건 B] 관찰자 가입 없음 (Without Observation)**\
  결과를 표출하지 않고 바로 포기\
  Discard results immediately without retaining or visualizing

---

## 실행 환경

## Execution Environment

- Qiskit 1.0.2
- Aer Simulator (`aer_simulator`)
- Shots: 1000 per circuit x 10 executions

---

## 1. 가입 조건 반복 실행 결과

## 1. Repeated Trial Results under Observer Presence

### Trial 1

- Result: `{'00': 494, '11': 506}`

![Trial 1](result_1.png)

### Trial 2

- Result: `{'00': 504, '11': 496}`

![Trial 2](result_2.png)

### Trial 3

- Result: `{'00': 503, '11': 497}`

![Trial 3](result_3.png)

---

## 2. 무가입 조건 실행 결과

## 2. Result under No Observation

- Result: `{'00': 492, '11': 508}`

![Unobserved](gdp_unobserved.png)

---

## 구조적 해석 및 의의

## Structural Interpretation and Significance

> 관찰 유무에 관계없이 구조 반복이 기준 회로 구성 내에서 자동적으로 복제되었다.\
> Structure recurrence was preserved autonomously within the baseline circuit regardless of observer presence.

- 여러 번의 실행에서 결과 분포가 정확하게 중첩\
  Repeated trials showed tightly clustered results between |00⟩ and |11⟩

- 관찰 유무가 구조 반복에 영향을 주지 않았음\
  Observer presence had no significant impact on structural recurrence

- 관찰자가 피드백의 요건이 아니었을 것을 시작적 결과로 지시\
  Suggests that the observer was not a necessary condition for feedback-based persistence

> 따라서 이 구조 반복은 여분한 자신 복제(자기 유지)로 포함되어 있는지, 혹은 초기 구조 객체의 도치 반복인지를 구분할 최종 검사가 필요하다.\
> It remains to be clarified whether this structural recurrence reflects true self-replication or merely reproduction of an initially imposed structure.

---

## 추가 구조 분석

## Additional Structural Analysis

> 이 회로는 얽힘 상태 (|00⟩ + |11⟩)/√2 를 생성하지만, 측정 결과는 항상 00 또는 11 중 하나로만 붕괴되었다. 중첩 상태인 01, 10은 전혀 나타나지 않았다.\
> Although the circuit generates the entangled state (|00⟩ + |11⟩)/√2, measurement results always collapse to either 00 or 11. Intermediate superpositions such as 01 and 10 were never observed.

- 이는 회로 구조가 **결과 선택지를 사전에 제한**하고 있음을 보여준다.\
  This indicates that the circuit structurally constrains the outcome space in advance.

- 결과의 반복은 자기 유지적 구조 때문이 아니라, **구조적 선택지 봉쇄로 인한 결정적 반복**일 가능성이 있다.\
  The recurrence may stem not from self-sustaining behavior but from deterministically limited choices inherent in the structure.

