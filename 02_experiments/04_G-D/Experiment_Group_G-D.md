# 실험군 G-D: 구조 자기 반복 실험

# Experiment Group G-D: Self-Repetition of Structure

## 실험 목적

## Objective

관측으로 형성된 구조가 외부 조건이나 피드백 없이도 시간적으로 반복될 수 있는지를 실험한다. 이 실험은 양자 회로 내 구조가 일시적 현상이 아닌, **자기 복제 성향을 가지는가**를 검증한다.\
This experiment investigates whether a structure formed by measurement can reappear over time without external conditions or feedback, testing whether quantum circuit structures possess self-replicating tendencies rather than being transient phenomena.

---

## 실험 회로 설계

## Circuit Design

- **회로 구성**: 얽힘 기반 회로 두 개를 연속 실행하며 구조 반복성 여부 확인\
  **Circuit**: Two entanglement-based circuits executed sequentially to check for structural repetition

  - 게이트: H(0) → CX(0, 1) → 측정\
    Gates: H(0) → CX(0, 1) → measure

- **실험 조건**:\
  **Experimental Conditions:**

  - 두 회로는 동일한 조건에서 실행되며, 서로의 결과를 전달받지 않음\
    Both circuits run under identical conditions without sharing results
  - 반복 횟수: 10회 (각 반복마다 회로 두 개 실행)\
    Number of repetitions: 10 (each includes two circuit executions)

---

## 실행 환경

## Execution Environment

- Qiskit 1.0.2
- Aer Simulator (`aer_simulator`)
- Shots: 1024 per circuit

---

## 1. 반복 실험 결과

## 1. Repeated Trial Results

```
Trial 1: 11 → 00
Trial 2: 00 → 11
Trial 3: 11 → 00
Trial 4: 00 → 11
Trial 5: 11 → 11
Trial 6: 00 → 00
Trial 7: 00 → 00
Trial 8: 11 → 00
Trial 9: 11 → 00
Trial 10: 11 → 00

🧾 동일한 결과 반복된 횟수: 3 / 10
```

---

## 구조적 해석 및 의의

## Structural Interpretation and Significance

> 실험 결과, 10회 중 단 3회만이 구조의 자기 반복을 보였다. 그 외 대부분은 1차 회로와 2차 회로의 결과가 반전되거나 불일치하였다. 이는 구조가 **외부 조건 없이 자발적으로 반복되지 않음**을 시사한다.\
> Of the 10 trials, only 3 showed structural self-repetition. In most cases, the first and second circuit results were inverted or inconsistent, suggesting that the structure does not spontaneously repeat without external influence.

- 동일한 얽힘 구조가 항상 `00`, `11` 중 하나를 출력하지만, 그 선택 방향은 시간적으로 일관되지 않음\
  While the entangled structure consistently yields either `00` or `11`, the directional preference does not persist over time

- `11 → 00`, `00 → 11`과 같은 반전이 반복되며, 무작위성과 유사한 경향을 보임\
  The frequent alternation like `11 → 00` and `00 → 11` resembles randomness more than structured memory

- 구조가 기억되거나 복제되는 형태의 자기 보존은 관찰되지 않음\
  No sign of memory or self-preservation of structure has been observed

> 본 실험은 구조가 시간 축을 따라 자발적으로 복제될 가능성에 대한 실험적 접근이었으며, 결과적으로 **얽힘 구조는 유지되나, 그 방향성은 고정되지 않는다**는 점을 입증한다.\
> This experiment approached the possibility of spontaneous structural replication over time. The results indicate that while entangled structures persist, their directional tendencies are not preserved.

---

