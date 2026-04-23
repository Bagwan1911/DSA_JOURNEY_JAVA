# 📚 DSA Notes — Arrays

> **Date:** 23 April 2026  
> **Topic:** Arrays (Basics to Important Concepts)

---

## 🔷 Array kya hota hai?

Array ek collection hota hai **same type ke elements** ka,
jo **contiguous memory** mein store hote hain.

```java
int[] arr = {10, 20, 30, 40, 50};
//            0   1   2   3   4  ← index
```

---

## 🔷 Key Properties

- Index **0 se start** hota hai
- **Random access** possible hai — arr[2] directly milta hai
- Size **fixed** hoti hai declare karte waqt
- Same data type store hoti hai

---

## 🔷 Time Complexity

| Operation       | Time  |
|-----------------|-------|
| Access (index)  | O(1)  |
| Search          | O(n)  |
| Insert (end)    | O(n)  |
| Insert (middle) | O(n)  |
| Delete          | O(n)  |

---

## 🔷 Common Operations (Java)

```java
int[] arr = {10, 20, 30, 40, 50};

// Access
System.out.println(arr[2]);       // 30

// Length
System.out.println(arr.length);   // 5

// Update
arr[1] = 99;

// Traverse
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}

// For-each loop
for (int x : arr) {
    System.out.println(x);
}

// Sort
Arrays.sort(arr);

// Copy
int[] copy = Arrays.copyOf(arr, arr.length);
```

---

## 🔷 Important Patterns (Interview mein aate hain)

### 1. Two Pointer
Dono ends se aana start karo — sorted arrays mein use hota hai.
```java
int left = 0, right = arr.length - 1;
while (left < right) {
    // kuch karo
    left++;
    right--;
}
```

### 2. Sliding Window
Fixed size ka window slide karte ho array pe.
```java
int windowSum = 0;
for (int i = 0; i < k; i++) windowSum += arr[i];

for (int i = k; i < arr.length; i++) {
    windowSum += arr[i] - arr[i - k];
}
```

### 3. Prefix Sum
Har point tak ka sum pehle calculate kar lo.
```java
int[] prefix = new int[arr.length];
prefix[0] = arr[0];
for (int i = 1; i < arr.length; i++) {
    prefix[i] = prefix[i - 1] + arr[i];
}
```

---

## 🔷 Practice Problems (LeetCode)

| #  | Problem                          | Difficulty |
|----|----------------------------------|------------|
| 1  | Two Sum                          | Easy       |
| 2  | Best Time to Buy and Sell Stock  | Easy       |
| 3  | Maximum Subarray (Kadane's)      | Medium     |
| 4  | Product of Array Except Self     | Medium     |
| 5  | Container With Most Water        | Medium     |

---

## ✅ Aaj ka Summary

- Array = contiguous memory, O(1) access
- Two Pointer, Sliding Window, Prefix Sum — ye teen patterns yaad rakhna
- LeetCode pe **Two Sum** se shuru karo

---