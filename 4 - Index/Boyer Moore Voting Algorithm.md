Finds all elements that appear more than ⌊n / k⌋ times.

### 🔑 Key Idea
- At most **k − 1** elements can appear more than ⌊n / k⌋ times.

### 🧠 Algorithm Steps

#### 1. Candidate Selection
- Maintain up to **k − 1** candidates with counts.
- For each number:
  - If it matches a candidate → **increment count**
  - Else if any count is 0 → **assign as new candidate with count 1**
  - Else → **decrement all counts**

#### 2. Verification
- Reset counts.
- Count actual occurrences of candidates.
- Add to result if **count > ⌊n / k⌋**

### ⏱️ Complexity
- **Time:** O(n)  
- **Space:** O(k)