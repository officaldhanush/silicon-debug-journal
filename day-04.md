# Day 4: Scan Chains & The Bucket Brigade

## 💡 Concept Learned
A **Scan Chain** links internal registers together into a long shift register during test mode. This allows engineers to stream test patterns *in* (controllability) and shift internal states *out* (observability) without needing physical access to every internal node.

---

## 🛠️ DFD Detective Checklist
- [x] **Understand Serial Shifting:** Recognized how data moves sequentially through a linked chain of registers.
- [x] **Track Bit Streams:** Followed test patterns injected via scan-in lines.
- [x] **Isolate Chain Faults:** Pinpointed where data corruption or stuck states occurred within the shift register.

---

## 🧩 The Puzzle
Shifting a pattern of `1, 0, 1` into a 3-register scan chain (`Reg 1 -> Reg 2 -> Reg 3`), but receiving `1, 0, 0` at the output pin.

---

## 🎯 My Answer & Reasoning
* **Failed Register / Link:** Reg 1.
* **My Reason:** The expected output sequence was `1, 0, 1`, but we received `1, 0, 0`. Since the first bit pushed into the chain has to travel through `Reg 1` -> `Reg 2` -> `Reg 3`, a failure at the very end of the output stream indicates that `Reg 1` failed to capture or pass the initial `1`, causing a `0` to propagate through the rest of the chain.
