# 실험군 G-B: 관측 없는 구조 유지 실험

# Experiment Group G-B: Structure Without Measurement

## 실험 목적

## Objective

양자 회로가 외부 관측 없이 내부에서 구조를 선택하고 유지할 수 있음을 보이며, 그 구조가 정해진 기저 상태로만 국한됨을 검증한다.\
This experiment demonstrates that a quantum circuit can internally select and maintain a structural state without measurement, and verifies that the resulting structure is confined strictly to designated basis states.

---

## 실험 회로 설계

## Circuit Design

- **회로 구성**: 2 큐빗 자기 선택 및 구조 복제 회로\
  **Circuit**: 2-qubit self-selection and structural replication

  - 게이트: H(0) → CX(0, 1)\
    Gates: H(0) → CX(0, 1)
  - 타겟 상태: \(|\psi\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)\)\
    Target state: \(|\psi\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)\)

- **실험 조건**:\
  **Experimental Conditions:**

  - **관측 없음**: 상태벡터만 저장\
    No measurement: statevector saved only
  - **구조 검증용 회로**: 측정 포함\
    Structure verification circuit: includes measurement

---

## 실행 환경

## Execution Environment

- Qiskit 1.0.2
- Aer Simulator (`aer_simulator`)
- Shots: 1024 (측정 회로)

---

## 1. 상태벡터 출력 (비관측 핵심 구조)

## 1. Statevector Output (Unobserved Core Structure)

```python
qc = QuantumCircuit(2)
qc.h(0)
qc.cx(0, 1)
qc.save_statevector()
```

```
Statevector: [0.7071+0.j, 0+0.j, 0+0.j, 0.7071+0.j]
```

> 이는 \(|00\rangle\)과 \(|11\rangle\)에만 진폭이 존재하며, 자기 선택된 상태가 구조적으로 복제되었고, 관측 없이 구조가 내부에 유지되었음을 나타낸다.\
> This confirms that only \(|00\rangle\) and \(|11\rangle\) have amplitude, showing that the self-selected state has been structurally copied and retained without measurement.

---

## 2. 검증 회로 결과 (측정 기반)

## 2. External Verification Circuit (Measured)

```python
qc = QuantumCircuit(2, 2)
qc.h(0)
qc.cx(0, 1)
qc.measure([0, 1], [0, 1])
```

```
Counts: {'00': 519, '11': 505}
```

> 결과는 \(|00\rangle\)과 \(|11\rangle\)만이 측정되었으며, 이는 구조가 외부 관측에서도 안정적으로 유지됨을 보여준다.\
> Only \(|00\rangle\) and \(|11\rangle\) were measured, confirming structural stability even under external observation.



---

## 구조적 해석 및 의의  
## Structural Interpretation and Significance

> 이 회로는 결과를 미리 정해두거나 외부에서 조정한 것이 아니다. 구조는 단지 가능한 분기 범위를 정의하며, 구체적인 선택은 회로 내부의 중첩과 복제 연산에 의해 결정된다. 본 실험은 이 구조가 관측 없이도 지속되며, 측정 시 동일하게 재현된다는 점을 보이는 데에 목적이 있다. 따라서 이 실험은 결과를 보여주는 것이 아니라, **그 결과를 가능하게 만든 구조의 존재를 검증하는 것**이다.  
> This circuit does not predetermine outcomes or manipulate them externally. Instead, it defines a structural range within which outcomes may emerge, with the actual selection determined by superposition and controlled operations internal to the circuit. The purpose of this experiment is to demonstrate that this structure persists without measurement and is consistently reproduced under observation. Therefore, the experiment does not aim to present outcomes but to verify the existence of the structural conditions that make those outcomes possible.


## Structural Interpretation and Significance

- 상태벡터는 관측 없이도 구조가 선택되고 유지되었음을 증명한다.\
  The statevector confirms that structure was selected and preserved without measurement.
- 측정 기반 결과는 동일 구조가 외부 관측 상황에서도 일관되게 재현됨을 보여준다.\
  The measurement-based result shows the same structure is consistently reproduced under observation.

> 이는 회로 내부의 구조가 관측의 유무와 무관하게 실재함을 실험적으로 입증하며, 구조적 자기 선택과 유지력이 양자 회로 내에서 독립적으로 성립할 수 있음을 보여준다.\
> This experimentally demonstrates that circuit-internal structure exists independently of observation and that self-selection and structural persistence can operate autonomously within quantum systems.

