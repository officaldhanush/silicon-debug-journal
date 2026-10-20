# Day 2: Controllability & Override Mechanisms

## 💡 Concept Learned
**Controllability** is the ability to force internal nodes of a circuit to specific known states ($0$ or $1$) using built-in debug mechanisms (like override switches or MUXes) without relying on external environmental factors.

---

## 🛠️ DFD Detective Checklist
- [x] **Identify Controllability Gap:** Recognized that waiting for real-world conditions (like overheating) is too slow for factory testing.
- [x] **Evaluate Functional Workarounds:** Analyzed changing sensor thresholds to trigger a state change.
- [x] **Apply DFD Hardware Override:** Introduced the concept of a MUX/Override switch to inject direct test values safely.

---

## 🧩 The Puzzle
An internal alarm system needs to be tested at room temperature without physically heating up the chip to trigger the temperature sensor.

---

## 🎯 My Answer & Reasoning
* **My Approach:** Adjusting the sensor threshold so it triggers at room temperature (25°C) to automatically output a 1.
* **DFD Pro Critique:** While this forces the test signal, a true DFD engineer uses a dedicated **override switch (MUX)** before the logic gate. This allows testing both 0 and 1 instantly without depending on sensor calibration accuracy.
