# 📚 DSA Notes — Types of Searching Algorithms

> **Date:** 9 May 2026
> **Topic:** Searching Algorithms (Important Types)

---

# 🔷 Searching Algorithm kya hota hai?

Searching ka matlab hota hai kisi data structure mein ek specific element ko find karna.

Example:

```text
Array = [10, 20, 30, 40, 50]

Target = 30
```

Check karna:

```text
30 present hai ya nahi?
Kis index par hai?
```

---

# 🔷 Important Types of Searching

| # | Searching Type       | Sorted Required | Time Complexity |
| - | -------------------- | --------------- | --------------- |
| 1 | Linear Search        | ❌ No            | O(n)            |
| 2 | Binary Search        | ✅ Yes           | O(log n)        |
| 3 | Jump Search          | ✅ Yes           | O(√n)           |
| 4 | Interpolation Search | ✅ Yes           | O(log log n)    |
| 5 | Exponential Search   | ✅ Yes           | O(log n)        |
| 6 | Ternary Search       | ✅ Yes           | O(log₃ n)       |

---

# 🔷 1. Linear Search

## 📌 Concept

Start se end tak ek ek element check karo.

```text
[4, 2, 7, 1, 9]
```

Simple but slow.
Jaise government office ki manual file checking.

---

## ✅ Java Code

```java
for (int i = 0; i < arr.length; i++) {

    if (arr[i] == target) {
        return i;
    }
}
```

---

## ✅ Best Use

* Small arrays
* Unsorted arrays

---

# 🔷 2. Binary Search

## 📌 Concept

Middle element check karo aur array ko half mein divide karo.

```text
[1, 3, 5, 7, 9, 11]
```

---

## ✅ Important

Array sorted hona chahiye.

---

## ✅ Java Code

```java
while (low <= high) {

    int mid = low + (high - low) / 2;

    if (arr[mid] == target) {
        return mid;
    }

    else if (target < arr[mid]) {
        high = mid - 1;
    }

    else {
        low = mid + 1;
    }
}
```

---

## ✅ Best Use

* Large sorted arrays
* Fast searching

---

# 🔷 3. Jump Search

## 📌 Concept

Array ko fixed blocks mein jump karo.

Example:

```text
Jump size = √n
```

Pehle jump:

```text
0 → 3 → 6 → 9
```

Phir block ke andar linear search.

Humans bhi life mein aise hi karte hain.
Pehle bade jumps, phir damage control.

---

## ✅ Time Complexity

```text
O(√n)
```

---

## ✅ Best Use

* Sorted arrays
* Binary search possible na ho

---

# 🔷 4. Interpolation Search

## 📌 Concept

Binary Search jaisa hi hai but smarter mid choose karta hai.

Formula:

```text
mid = low + ((target - arr[low]) * (high - low))
               / (arr[high] - arr[low])
```

---

## ✅ Best Use

* Uniformly distributed sorted data

Example:

```text
[10, 20, 30, 40, 50]
```

---

## ✅ Complexity

| Case  | Time         |
| ----- | ------------ |
| Best  | O(log log n) |
| Worst | O(n)         |

---

# 🔷 5. Exponential Search

## 📌 Concept

Pehle range find karo using powers of 2.

```text
1 → 2 → 4 → 8 → 16
```

Phir Binary Search apply karo.

---

## ✅ Best Use

* Infinite sized arrays
* Very large datasets

---

## ✅ Steps

1. Range find karo
2. Binary Search lagao

---

# 🔷 6. Ternary Search

## 📌 Concept

Binary Search mein 2 parts bante hain.
Ternary Search mein 3 parts bante hain.

```text
mid1
mid2
```

---

## ✅ Complexity

```text
O(log₃ n)
```

---

## ✅ Best Use

* Mathematical optimization problems
* Unimodal functions

---

# 🔷 Linear vs Binary Search

| Feature         | Linear Search | Binary Search |
| --------------- | ------------- | ------------- |
| Sorted Required | ❌ No          | ✅ Yes         |
| Speed           | Slow          | Fast          |
| Complexity      | O(n)          | O(log n)      |
| Implementation  | Easy          | Medium        |

---

# 🔷 Important Interview Patterns

| Pattern                | Algorithm             |
| ---------------------- | --------------------- |
| Basic searching        | Linear Search         |
| Sorted array searching | Binary Search         |
| Infinite array         | Exponential Search    |
| Optimization problems  | Binary/Ternary Search |
| Uniform data searching | Interpolation Search  |

---

# 🔷 Practice Problems (LeetCode)

| # | Problem                        | Difficulty |
| - | ------------------------------ | ---------- |
| 1 | Binary Search                  | Easy       |
| 2 | Search Insert Position         | Easy       |
| 3 | Search in Rotated Sorted Array | Medium     |
| 4 | First and Last Position        | Medium     |
| 5 | Find Peak Element              | Medium     |

---

# ✅ Aaj ka Summary

* Searching ka matlab element find karna
* Linear Search simple hai but slow
* Binary Search fast hai but sorted array chahiye
* Jump, Interpolation, Exponential advanced searching techniques hain
* Interview mein mostly Binary Search dominate karta hai
* Binary Search ka pattern master kar lo, aadhi DSA anxiety khatam ho jaati hai

---
