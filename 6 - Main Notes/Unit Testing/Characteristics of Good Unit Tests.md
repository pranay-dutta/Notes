### 🚫 No Tests are Better than Bad Tests

> **Bad tests** waste time, give false confidence, and break often.
---
### 📌 What Makes a **Good Test**?

A **good test** is:  🛠 **Maintainable**,  🧱 **Robust**  ✅ **Trustworthy**

---
### 🛠  **Maintainable Tests**

- Have a **clear and descriptive name**
- Test a **single behavior or scenario**
- Are **small** (ideally **< 10 lines**)
- Use meaningful **variables** and **constants**
- Are **well-formatted** and easy to read

---
### 🧱 **Robust Tests**

- Are **resilient** to changes in implementation
- Focus on **testing behavior**, not internal details
	- ❗ Avoid **tight assertion** to specific code structure
    - ✔️ Prefer broad assertions of outcomes over specific values unless necessary

---
### ✅ **Trustworthy Tests**

- In simple terms **tests** that we can **trust**
- Produce **reliable results**: no **false positives** or **false negatives**
- Are **deterministic** — not dependent on:
    - Random data
    - Global state
    - External services (without mocks/stubs)
	
→ [[Unit testing in JavaScript]]