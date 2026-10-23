# Day 5: Boundary Scan (JTAG) & Board-Level Debug

## 💡 Concept Learned
**Boundary Scan (JTAG)** places virtual test cells behind every pin of a chip. This allows DFD engineers to test board-level connections between multiple chips without needing physical multimeter probes or test fixtures.

---

## 🛠️ DFD Detective Checklist
- [x] **Understand Board-Level Isolation:** Recognized the challenge of hidden solder pins on circuit boards.
- [x] **Utilize Virtual Test Cells:** Leveraged JTAG boundary scan pins to drive and observe signals remotely.
- [x] **Diagnose Trace Faults:** Evaluated pin-to-pin communication mismatches between interconnected chips.

---

## 🧩 The Puzzle
Testing a trace line between Chip A and Chip B using JTAG. Sending a `1` passes successfully, but sending a `0` from Chip A still results in Chip B reading a `1`.

---

## 🎯 My Answer & Reasoning
* **Diagnosis:** Chip B (or the trace connection) failed to register the driven `0`.
* **My Reason & Refinement:** When Chip A drives a `0`, Chip B should receive a `0`. Because it read a `1` instead, the signal is being forced high—typically indicating a stuck pin, a trace shorted to power ($V_{CC}$), or an active pull-up resistor overriding the low signal.
