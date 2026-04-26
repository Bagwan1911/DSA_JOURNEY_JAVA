# 📚 DSA Notes — Strings

> **Date:** 25 April 2026  
> **Topic:** Strings (Basics to Important Concepts)

---

## 🔷 String kya hota hai?

String ek **sequence of characters** hota hai.
Java mein String ek **object** hai aur ye **immutable** hoti hai
(matlab ek baar ban gayi toh change nahi hoti).

```java
String s = "Hello";
//          H e l l o
//          0 1 2 3 4  ← index
```

---

## 🔷 Key Properties

- **Immutable** hai — har baar naya object banta hai
- Index **0 se start** hota hai
- `==` se compare mat karo, **`.equals()`** use karo
- Bahut saare built-in methods available hain

---

## 🔷 Time Complexity

| Operation         | Time  |
|-------------------|-------|
| Access (index)    | O(1)  |
| Search (contains) | O(n)  |
| Concatenation     | O(n)  |
| Length            | O(1)  |
| Substring         | O(n)  |

---

## 🔷 Common Operations (Java)

```java
String s = "hello world";

// Length
System.out.println(s.length());          // 11

// Character access
System.out.println(s.charAt(0));         // h

// Uppercase / Lowercase
System.out.println(s.toUpperCase());     // HELLO WORLD
System.out.println(s.toLowerCase());     // hello world

// Substring
System.out.println(s.substring(6));      // world
System.out.println(s.substring(0, 5));   // hello

// Contains
System.out.println(s.contains("world")); // true

// Replace
System.out.println(s.replace("world", "java")); // hello java

// Split
String[] words = s.split(" ");           // ["hello", "world"]

// Trim (spaces hatao)
String s2 = "  hi  ";
System.out.println(s2.trim());           // "hi"

// Compare
String a = "abc";
String b = "abc";
System.out.println(a.equals(b));         // true ✅
System.out.println(a == b);             // mat karo ❌

// String to char array
char[] ch = s.toCharArray();

// char array to String
String back = new String(ch);
```

---

## 🔷 StringBuilder (Jab String modify karni ho)

```java
// String immutable hai isliye loop mein concatenation slow hoti hai
// StringBuilder use karo — O(1) append

StringBuilder sb = new StringBuilder();
sb.append("Hello");
sb.append(" World");
sb.reverse();
System.out.println(sb.toString());   // dlroW olleH
System.out.println(sb.length());     // 11
```

---

## 🔷 Important Patterns (Interview mein aate hain)

### 1. Two Pointer (Palindrome check)
```java
String s = "racecar";
int left = 0, right = s.length() - 1;
boolean isPalin = true;

while (left < right) {
    if (s.charAt(left) != s.charAt(right)) {
        isPalin = false;
        break;
    }
    left++;
    right--;
}
System.out.println(isPalin); // true
```

### 2. Frequency Count (HashMap)
```java
HashMap<Character, Integer> map = new HashMap<>();
for (char c : s.toCharArray()) {
    map.put(c, map.getOrDefault(c, 0) + 1);
}
```

### 3. Sliding Window (Longest substring)
```java
// Longest substring without repeating characters
HashSet<Character> set = new HashSet<>();
int left = 0, maxLen = 0;

for (int right = 0; right < s.length(); right++) {
    while (set.contains(s.charAt(right))) {
        set.remove(s.charAt(left));
        left++;
    }
    set.add(s.charAt(right));
    maxLen = Math.max(maxLen, right - left + 1);
}
```

---

## 🔷 Practice Problems (LeetCode)

| #  | Problem                                      | Difficulty |
|----|----------------------------------------------|------------|
| 1  | Valid Palindrome                             | Easy       |
| 2  | Reverse String                               | Easy       |
| 3  | Longest Common Prefix                        | Easy       |
| 4  | Longest Substring Without Repeating Chars    | Medium     |
| 5  | Group Anagrams                               | Medium     |

---

## ✅ Aaj ka Summary

- String immutable hai — modify karna ho toh **StringBuilder** use karo
- Compare karna ho toh **`.equals()`** use karo, `==` nahi
- Two Pointer, HashMap Frequency, Sliding Window — ye teen patterns yaad rakhna
- LeetCode pe **Valid Palindrome** se shuru karo

---
