# Day 1: The Black Box & Observability

## 💡 Concept Learned
Design for Debug (DFD) is about adding **observability** (the ability to see internal signals) and **controllability** (the ability to set internal signals) to a system so we can isolate hardware failures quickly without destructive physical probing.

---

## 🛠️ DFD Detective Checklist
- [x] **Identify the Black Box:** Recognized that internal nodes are hidden from direct observation.
- [x] **Apply Divide & Conquer:** Used a midpoint probe location to cut potential failure points in half.
- [x] **Evaluate Observability:** Verified what information a single test point reveals about upstream and downstream logic.

---

## 🧩 The Puzzle
In a chain of 3 components (`Input` $\rightarrow$ `A` $\rightarrow$ `B` $\rightarrow$ `C` $\rightarrow$ `Output`), the signal fails to reach `Output`. I am allowed to check only **ONE** internal node first.

---

## 🎯 My Answer & Reasoning
* **Where I probed first:** Between Component B and Component C.
* **My Reason:** If the signal passes through A and B successfully to reach this point, then Component C must be the broken component preventing the output. If no signal reaches here, Component C is eliminated as the cause, narrowing the fault down to A or B.