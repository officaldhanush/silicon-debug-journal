# Day 3: The Golden Signature & Failure Isolation

## 💡 Concept Learned
**Golden Signature Analysis** involves comparing the output sequence of a newly manufactured test chip against a **Known Good Die (Golden Reference)**. Any mismatch instantly flags a failure, allowing engineers to pinpoint the exact step and bit line that failed.

---

## 🛠️ DFD Detective Checklist
- [x] **Identify Baseline:** Established the expected output sequence using the Golden Reference.
- [x] **Compare Sequences:** Aligned test chip output step-by-step against the golden signature.
- [x] **Isolate Failure Point:** Pinpointed the exact step (Step 3) and bit position where deviation occurred.

---

## 🧩 The Puzzle
Comparing a 4-bit counter golden signature (`0001` $\rightarrow$ `0010` $\rightarrow$ `0100` $\rightarrow$ `1000`) against a test chip output (`0001` $\rightarrow$ `0010` $\rightarrow$ `0000` $\rightarrow$ `1000`).

---

## 🎯 My Answer & Reasoning
* **Step of Failure:** Step 3.
* **Bit Position:** 3rd bit from the right.
* **My Reason & Refinement:** The test chip output `0000` missed the expected `1` at the 3rd position in Step 3 (Golden was `0100`). This indicates that the 3rd bit failed to transition high and was stuck at `0` for that cycle.
