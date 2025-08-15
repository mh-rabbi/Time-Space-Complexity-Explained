
# Understanding Algorithms and Big O Notation

## What is an Algorithm?

Before we talk about **Big O**, it's important to first understand what exactly an **algorithm** is, especially in the context of platforms like **LeetCode**.

An **algorithm** can be seen as a recipe for a computer to follow — a set of **step-by-step instructions** to solve a problem.

Algorithms take an **input** and produce an **output** — the answer to a question regarding the input.

**Example:**  
Say you have a non-empty array of positive integers called `nums`, and you want to answer:

> What is the largest number in `nums`?

**Algorithm:**
1. Create a variable `maxNum` and initialize it to `0`.
2. Iterate over each element `num` in `nums`.
3. If `num` is greater than `maxNum`, update `maxNum = num`.
4. Output `maxNum`.

These instructions, when followed, will solve the problem. You can now implement them in code.

---

## Requirements for Algorithms (LeetCode Context)

- **Deterministic**: Given the same input, the algorithm should always produce the same output. No randomness.
- **Correct for all valid inputs**:  
  Example — The above algorithm assumes `nums` is a **non-empty array of positive integers**. If negative numbers are included, initializing `maxNum = 0` could fail. Instead, initialize `maxNum` to the **first element**.

---

## What is Big O?

**Big O Notation** describes the **computational complexity** of an algorithm.

There are two main types:

1. **Time Complexity** — How the runtime grows with input size.
2. **Space Complexity** — How memory usage grows with input size.

---

### Time Complexity
As input size grows, **how much longer** does the algorithm take?

---

### Space Complexity
As input size grows, **how much more memory** does the algorithm use?

---

## How Complexity Works

Complexity is expressed as a **function** where variables represent input-dependent values.

**Common variable:**  
- `n` — length of an array or string.

Example: In the "find largest number" example:
- `n` = length of `nums`.

---

**Why not track integer size?**  
In theory, bigger integers take more time, but in practice, we treat all integers the same.

---

**Examples of Complexity Notations:**

- `O(n)`
- `O(n^2)`
- `O(2^n)`
- `O(log n)`
- `O(n * m)` → `m` could be length of another array.

---

## Calculating Complexity

Time complexity is **not** exact operation counting — it measures **growth rate** relative to input size.

Example: Finding largest number in `nums`:
- Runs **n** comparisons → `O(n)` time complexity.

---

## Rules for Big O

### 1. Ignore constants
```

O(9999999n) = O(8n) = O(n) = O(500n)

```

Example:  
Two algorithms:
- A: `n` operations
- B: `5n` operations

Both grow **linearly** → **O(n)**.

---

### 2. Focus on the dominant term
```

O(2^n + n^2 − 500n) → O(2^n)

````

As `n → ∞`, smaller terms become insignificant.

---

### 3. Constant Complexity `O(1)`
- Runtime is independent of input size.
- Example: Accessing an element in an array by index.

---

### Best / Average / Worst Case
- Usually worst case is reported.
- Best case is **never** the one to mention in interviews unless asked.

---

## Analyzing Time Complexity — Examples

### Example 1
```java
for (int num: arr) {
    print(num);
}
````

* Time complexity: **O(n)**

---

### Example 2

```java
for (int num: arr) {
    for (int i = 0; i < 500000; i++) {
        print(num);
    }
}
```

* Time complexity: **O(n)** (but practically slower)

---

### Example 3

```java
for (int num: arr) {
    for (int num2: arr) {
        print(num * num2);
    }
}
```

* Time complexity: **O(n²)**

---

### Example 4

```java
for (int num: arr) print(num);
for (int num: arr) print(num);
for (int num: arr2) print(num);
```

* Time complexity: **O(n + m)**

---

### Example 5

```java
for (int i = 0; i < arr.length; i++) {
    for (int j = i; j < arr.length; j++) {
        print(arr[i] + arr[j]);
    }
}
```

* Time complexity: **O(n²)**

---

## Logarithmic Time — `O(log n)`

A logarithm is the **inverse of exponents**.
Base is usually 2.

---

**Example: Binary Search**

* Start with `n` elements.
* Each step halves the search space:

```
n → n/2 → n/4 → n/8 → ...
```

* Time complexity: **O(log n)**

---

**`O(n log n)`**

* Common in efficient sorting algorithms (Merge Sort, Heap Sort, Quick Sort average case).

---

## Space Complexity — Examples

We **do not** count:

* Input storage
* Output storage (unless explicitly asked)

---

### Example 1

```java
for (int num: arr) {
    print(num);
}
```

* Space: **O(1)**

---

### Example 2

```java
Array doubledNums = new int[n];
for (int num: arr) {
    doubledNums.add(num * 2);
}
```

* Space: **O(n)**

---

### Example 3

```java
Array nums = new int[n/100];
for (int i = 0; i < n/100; i++) {
    nums.add(arr[i]);
}
```

* Space: **O(n)** (constants ignored)

---

### Example 4

```java
int[][] grid = new int[n][m];
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        grid[i][j] = arr[i] * arr2[j];
    }
}
```

* Space: **O(n \* m)**

---

## Summary

* **Algorithms**: Step-by-step instructions to solve a problem.
* **Big O**: Describes **growth rate** of runtime or memory use.
* **Time Complexity**: How runtime changes with input size.
* **Space Complexity**: How memory usage changes with input size.
* **Rules**: Ignore constants, keep dominant term, focus on worst case.
* **Common Complexities**:

  * Constant — `O(1)`
  * Linear — `O(n)`
  * Quadratic — `O(n²)`
  * Logarithmic — `O(log n)`
  * Linearithmic — `O(n log n)`
  * Exponential — `O(2^n)`

```

---

```
