# Project Name: Quantum Walks and Monte Carlo

## Team Name: The Walking Qubits

### Members:
1. **Name**: Ashna Yadav    |   **WISER Enrollment ID**: gst-G2T7G514NBhDM97
2. **Name**: Sayed Parsa Gharavi Neisiani   |   **WISER Enrollment ID**: gst-nd40bHA4EghH4n6

---

## Summary

### Task 1 – Familiarising with the Concept

- We started the project by reading the paper and supplementary material, focusing on:
  - **Quantum Walks** – a quantum equivalent to classical random walks, where the direction of the walker is determined by quantum superposition and interference.
  - **Monte Carlo Method** – a type of algorithm that relies on repeated random sampling, governed by probability and statistics.
  - **Why Quantum?** – While classical simulations are readily available, quantum implementations exploit parallelism and interference. This allows for quicker generation of more complex distributions, which can be difficult to simulate classically.

- All findings were compiled into a 2-page report.

---

### Task 2 – Moderately Generalising Gaussian Distribution from n Levels

- We began by implementing a basic **2-level QGB** (Quantum Galton Board). We created 2 versions, one based on the paper summarised in Task 1 (identifiable with SWAP gates implemented), and one based on what we knew about quantum computation & probabilities previously (without SWAP gates).

**How it works:**
- A coin(or ball) qubit determines the walker's movement (left or right).
- A **Hadamard gate** creates equal superposition—similar to flipping a fair coin.
- **Controlled shift operations** move the walker register based on the coin state.
- After enough steps, **interference patterns** emerge to form a probability distribution.

**Scaling to n levels:**
- After completing the 2-level implementation, we observed a repetitive pattern of `coin toss + shift`.
- This was generalized into a function with `n` as a variable.
- The function automatically designs the circuit layout for any `n`, maintaining logical consistency.

**Output:**
- Running the circuit with enough shots yields a histogram resembling a **Gaussian distribution**.

---

### Task 3 – Generating Other Distributions

#### 1. Exponential Distribution

**Plan:**
- Use a **biased/fine-grained QGB**, replacing the Hadamard gate with an **Rx(theta)** or **Ry(theta)** to simulate a biased coin.
- Add **reset gates** after each peg/stage to control interference.
- Add a **final correcting CNOT** to remove unwanted correlations.

**Key Challenge:**
- Tuning theta (rotation angle) and lambda (decay rate) to match an ideal exponential curve.
- Multiple iterations were run with different parameters until the histogram resembled an exponential distribution.

#### 2. Quantum Walk Distribution

**Concept:**
- Rather than biasing the coin, we manipulated **phases and interference patterns** of the walker.
- Goal: Final histogram has **higher edge probabilities**, consistent with constructive interference (typical of quantum walks).
- This involved careful use of **rotation gates** and **phase shifts** to break the symmetry of the Gaussian.

---

### Issues Faced

- **Parameter Finding**: Small changes in theta or lambda caused large differences in results and variance from expected outcomes.
- **Circuit Visualization**: As `n` increases, circuit complexity grows. This made debugging difficult via the Qiskit Circuit Drawer.
- **Distribution Accuracy**: Some runs showed noise or distortions, requiring fine-tuned parameters and high shot counts.

---

### Outcomes

- Successfully built a **scalable n-level Gaussian QGB**.
- Modified the QGB to produce **exponential** and **quantum walk-style** distributions.
- Gained awareness of trade-offs in using gates, biasing actions, and resetting states to shape distributions.

> This project demonstrates how quantum circuits can shape outputs to form various statistical patterns, paving the way for quantum simulations, probabilistic modeling, variational algorithms, and quantum machine learning.

---

###  Project Presentation Deck


