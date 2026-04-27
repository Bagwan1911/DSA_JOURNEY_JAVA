# 📚 DSA Notes — Stack & Queue

> **Date:** 27 April 2026  
> **Topic:** Stack & Queue (Basics to Important Concepts)

---

## 🔷 Stack kya hota hai?

Stack ek **LIFO** (Last In First Out) data structure hai.
Jaise plates ka stack — jo sabse upar rakhi hai, wahi pehle niklegi.

```
push(10) --> push(20) --> push(30)

TOP -->  [ 30 ]
         [ 20 ]
         [ 10 ]
```

---

## 🔷 Stack — Common Operations (Java)

```java
import java.util.Stack;

Stack<Integer> stack = new Stack<>();

// Push — element daalo
stack.push(10);
stack.push(20);
stack.push(30);

// Pop — top element nikalo
System.out.println(stack.pop());     // 30

// Peek — top dekho, nikalo nahi
System.out.println(stack.peek());    // 20

// isEmpty check
System.out.println(stack.isEmpty()); // false

// Size
System.out.println(stack.size());    // 2
```

---

## 🔷 Queue kya hota hai?

Queue ek **FIFO** (First In First Out) data structure hai.
Jaise line mein khade log — jo pehle aaya, wahi pehle bahar jayega.

```
enqueue(10) --> enqueue(20) --> enqueue(30)

FRONT --> [ 10 ] [ 20 ] [ 30 ] <-- REAR
```

---

## 🔷 Queue — Common Operations (Java)

```java
import java.util.LinkedList;
import java.util.Queue;

Queue<Integer> queue = new LinkedList<>();

// Enqueue — element daalo
queue.offer(10);
queue.offer(20);
queue.offer(30);

// Dequeue — front element nikalo
System.out.println(queue.poll());    // 10

// Peek — front dekho, nikalo nahi
System.out.println(queue.peek());    // 20

// isEmpty check
System.out.println(queue.isEmpty()); // false

// Size
System.out.println(queue.size());    // 2
```

---

## 🔷 Time Complexity

| Operation  | Stack | Queue |
|------------|-------|-------|
| Push/Offer | O(1)  | O(1)  |
| Pop/Poll   | O(1)  | O(1)  |
| Peek       | O(1)  | O(1)  |
| Search     | O(n)  | O(n)  |

---

## 🔷 Important Patterns (Interview mein aate hain)

### 1. Valid Parentheses (Stack)
```java
// Check karo brackets sahi hain ya nahi — (), {}, []
Stack<Character> stack = new Stack<>();
String s = "{[()]}";

for (char c : s.toCharArray()) {
    if (c == '(' || c == '{' || c == '[') {
        stack.push(c);
    } else {
        if (stack.isEmpty()) return false;
        char top = stack.pop();
        if (c == ')' && top != '(') return false;
        if (c == '}' && top != '{') return false;
        if (c == ']' && top != '[') return false;
    }
}
return stack.isEmpty();
```

### 2. Reverse a String using Stack
```java
Stack<Character> stack = new Stack<>();
String s = "hello";

for (char c : s.toCharArray()) stack.push(c);

StringBuilder sb = new StringBuilder();
while (!stack.isEmpty()) sb.append(stack.pop());

System.out.println(sb.toString()); // olleh
```

### 3. BFS using Queue
```java
// Graph/Tree traversal level by level
Queue<Integer> queue = new LinkedList<>();
queue.offer(root);

while (!queue.isEmpty()) {
    int node = queue.poll();
    System.out.println(node);
    // add children to queue
}
```

---

## 🔷 Stack vs Queue — Kab use karein?

| Stack                        | Queue                        |
|------------------------------|------------------------------|
| Undo/Redo operations         | BFS traversal                |
| Bracket matching             | Scheduling / ordering        |
| Recursion internally         | Printer queue jaise problems |
| Backtracking problems        | Level order traversal        |

---

## 🔷 Practice Problems (LeetCode)

| #  | Problem                              | Difficulty |
|----|--------------------------------------|------------|
| 1  | Valid Parentheses                    | Easy       |
| 2  | Implement Queue using Stacks         | Easy       |
| 3  | Implement Stack using Queues         | Easy       |
| 4  | Min Stack                            | Medium     |
| 5  | Next Greater Element                 | Medium     |

---

## ✅ Aaj ka Summary

- Stack = LIFO, Queue = FIFO — ye yaad rakhna
- Stack mein `push`, `pop`, `peek` — Queue mein `offer`, `poll`, `peek`
- **Valid Parentheses** — Stack ka classic interview problem
- **BFS** ke liye Queue use hoti hai
- LeetCode pe **Valid Parentheses** se shuru karo

---
