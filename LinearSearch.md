# 📚 DSA Notes — Linear Search

> **Date:** 1 May 2026
> **Topic:** Linear Search (Basics to Important Concepts)

---

## 🔷 Linear Search kya hota hai?

Linear Search ek simple searching algorithm hai jisme hum array ko **start se end tak ek ek karke check** karte hain.

Koi fancy divide-and-conquer drama nahi. Bas seedha scan. Jaise tum apni life decisions karte ho… step by step, bina optimization ke.

```
Array: [4, 2, 7, 1, 9]

Target = 7

Check karo:
4 ❌
2 ❌
7 ✅ (mil gaya)
```

---

## 🔷 Linear Search ka Logic

1. Array ke first element se start karo
2. Har element ko target se compare karo
3. Agar match mil gaya → index return karo
4. Agar end tak nahi mila → -1 return karo

---

## 🔷 Linear Search — Java Code

```java
public class LinearSearch {

    public static int linearSearch(int[] arr, int target) {

        for (int i = 0; i < arr.length; i++) {

            if (arr[i] == target) {
                return i;
            }
        }

        return -1;
    }

    public static void main(String[] args) {

        int[] arr = {4, 2, 7, 1, 9};

        int result = linearSearch(arr, 7);

        System.out.println(result); // 2
    }
}
```

---

## 🔷 Dry Run Example

```text
Array = [4, 2, 7, 1, 9]
Target = 1
```

### Step 1

```text
i = 0 → arr[0] = 4 ❌
```

### Step 2

```text
i = 1 → arr[1] = 2 ❌
```

### Step 3

```text
i = 2 → arr[2] = 7 ❌
```

### Step 4

```text
i = 3 → arr[3] = 1 ✅
```

Target mil gaya → index = 3

---

## 🔷 Time Complexity

| Case       | Complexity |
| ---------- | ---------- |
| Best Case  | O(1)       |
| Worst Case | O(n)       |
| Average    | O(n)       |

Translation: worst case mein pura array dekhna padega. Patience naam ki cheez honi chahiye.

---

## 🔷 Important Conditions

### ✅ Sorted hone ki zarurat nahi

```text
[4, 1, 9, 2, 7] ✔️
```

Binary Search ka attitude nahi hai isme. Ye sabke saath kaam karta hai.

---

## 🔷 Variations

### 1. Search in String

```java
String str = "hello";

for (int i = 0; i < str.length(); i++) {
    if (str.charAt(i) == 'e') {
        System.out.println(i); // 1
    }
}
```

---

### 2. Find Maximum Element

```java
int max = arr[0];

for (int i = 1; i < arr.length; i++) {
    if (arr[i] > max) {
        max = arr[i];
    }
}
```

---

### 3. Count Occurrences

```java
int count = 0;

for (int num : arr) {
    if (num == target) {
        count++;
    }
}
```

---

## 🔷 Common Mistakes

### ❌ Loop boundary galat

```java
for (int i = 0; i <= arr.length; i++) // ❌ error
```

### ✅ Correct

```java
for (int i = 0; i < arr.length; i++)
```

---

### ❌ Return bhool jana

Aadhe log code likh ke return hi nahi karte. Compiler tumhara dard nahi samjhega.

---

## 🔷 Linear Search — Kab use karein?

| Situation                         | Use Linear Search? |
| --------------------------------- | ------------------ |
| Small dataset                     | ✅ Yes              |
| Unsorted array                    | ✅ Yes              |
| Simple implementation chahiye     | ✅ Yes              |
| Large dataset (efficient chahiye) | ❌ No               |

---

## 🔷 Linear Search vs Binary Search

| Feature         | Linear Search | Binary Search |
| --------------- | ------------- | ------------- |
| Sorted required | ❌ No          | ✅ Yes         |
| Time Complexity | O(n)          | O(log n)      |
| Implementation  | Easy          | Medium        |
| Speed           | Slow          | Fast          |

---

## 🔷 Practice Problems (LeetCode)

| # | Problem                | Difficulty |
| - | ---------------------- | ---------- |
| 1 | Find Target in Array   | Easy       |
| 2 | Search in String       | Easy       |
| 3 | Count Occurrences      | Easy       |
| 4 | Find Maximum/Minimum   | Easy       |
| 5 | First Unique Character | Easy       |

---

## ✅ Aaj ka Summary

* Linear Search = simple sequential search
* Sorted hone ki zarurat nahi
* Time Complexity = **O(n)**
* Small ya unsorted data ke liye best hai
* Coding easy hai, bas dhyan se loop likho
* Start karo basic problems se, phir optimize karna seekho
