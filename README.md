# cqcls
Compressed Quantum-Classical Logic Simulator - In Progress
---
## **Project Summary: Compressed Qubit NOR Gate Simulator Inspired by AGC Architecture**

### **Overview**

This project proposes a quantum logic simulation model based on constrained quantum input states, derived from the Apollo Guidance Computer (AGC)’s exclusive use of 3-input NOR gates. By applying structural constraints on quantum inputs, I reduce dimensional requirements and simulate classical NOR logic in a minimal quantum system.

---

### **Key Concepts**

* **AGC Logic Architecture**: The Apollo Guidance Computer used \~5600 3-input NOR gates to implement all digital logic (including AND, OR, XOR) — demonstrating the universality of NOR logic.

* **Quantum Compression via Input Constraints**:
  By constraining paired input qubits to only two valid states — (0,0) and (1,1) — we reduce the total input space from 6 independent bits (64 states) to just 3 effective bits (8 states). This enables NOR simulation using only **3 qubits**.

* **Dual NOR Logic with Symmetry**:
  Two 3-input NOR gates (Gate A and Gate B) receive identical inputs under the constraint $A_i = B_i$. This makes their outputs identical, allowing the system to focus on a **single NOR output** $Y_A$, further simplifying simulation.

---

### **Simulation Output Logic Table**

| A1,B1 | A2,B2 | A3,B3 | Y\_A (NOR) |
| ----- | ----- | ----- | ---------- |
| (0,0) | (0,0) | (0,0) | 1          |
| (0,0) | (0,0) | (1,1) | 0          |
| (0,0) | (1,1) | (0,0) | 0          |
| (0,0) | (1,1) | (1,1) | 0          |
| (1,1) | (0,0) | (0,0) | 0          |
| (1,1) | (0,0) | (1,1) | 0          |
| (1,1) | (1,1) | (0,0) | 0          |
| (1,1) | (1,1) | (1,1) | 0          |

This confirms the expected NOR behavior: the output is 1 only when **all inputs are 0**.

---

### **Contributions**

* Introduced a logic constraint model that maps classical NOR gate design onto quantum-compressed systems
* Demonstrated how symmetric qubit pairing and NOR-only logic closure reduce quantum simulation dimensionality
* Showed how a 3-qubit space suffices to simulate a full 3-input NOR logic system under these constraints
* Outlined a path to extend classical AGC architecture concepts into efficient quantum circuit design

---

### **Next Steps**

1. **Implement Python Logic Simulator**

   * Accept 3 classical bits
   * Apply NOR logic
   * Output logic table
   * Integrate into AGC-style testing environment

2. **Quantum Simulation Framework**

   * Encode each valid input triplet as 3-qubit basis states
   * Define oracle/unitary operator to mark correct NOR output
   * Explore Hamiltonian design to evolve state toward classical NOR outcome

3. **AGC Simulator Integration**

   * Emulate NOR logic as part of a larger AGC gate netlist
   * Potential to simulate AGC NOR gate behavior using constrained-state quantum logic

---

### **Potential Applications**

* Educational quantum-classical logic simulators
* Compact quantum circuit emulators for classical systems
* Historical-computing-inspired quantum architecture models
* Logic compression and dimensionality reduction techniques in hybrid computing

---

### **Reference**

* AGC Simulator, https://www.ibiblio.org/apollo/#gsc.tab=0
* OpenAI, chatgpt.com
