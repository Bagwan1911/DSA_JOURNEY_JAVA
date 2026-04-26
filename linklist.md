# 📚 DSA Notes — LinkedList

> **Date:** 26 April 2026  
> **Topic:** LinkedList (Basics to Important Concepts)

---

## 🔷 LinkedList kya hota hai?

LinkedList ek **linear data structure** hai jisme elements (nodes) **pointers** ke through connected hote hain.
Array ki tarah contiguous memory nahi hoti — har node kahi bhi memory mein ho sakta hai.

```
[10 | next] --> [20 | next] --> [30 | next] --> null
  Head
```

---

## 🔷 Node kaise banta hai? (Java)

```java
class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}
```

---

## 🔷 Array vs LinkedList

| Feature            | Array  | LinkedList |
|--------------------|--------|------------|
| Access by index    | O(1)   | O(n)       |
| Insert at start    | O(n)   | O(1)       |
| Insert at end      | O(1)   | O(n)       |
| Delete             | O(n)   | O(1)*      |
| Memory             | Fixed  | Dynamic    |

---

## 🔷 Types of LinkedList

1. **Singly LinkedList** — ek direction, next pointer
2. **Doubly LinkedList** — dono direction, next + prev pointer
3. **Circular LinkedList** — last node head se connected

---

## 🔷 Common Operations (Java)

```java
class LinkedList {
    Node head;

    // Insert at end
    void insertEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }
        temp.next = newNode;
    }

    // Insert at start
    void insertStart(int data) {
        Node newNode = new Node(data);
        newNode.next = head;
        head = newNode;
    }

    // Delete a node by value
    void delete(int data) {
        if (head == null) return;
        if (head.data == data) {
            head = head.next;
            return;
        }
        Node temp = head;
        while (temp.next != null && temp.next.data != data) {
            temp = temp.next;
        }
        if (temp.next != null) {
            temp.next = temp.next.next;
        }
    }

    // Print list
    void print() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " --> ");
            temp = temp.next;
        }
        System.out.println("null");
    }
}
```

---

## 🔷 Important Patterns (Interview mein aate hain)

### 1. Reverse a LinkedList
```java
Node prev = null;
Node curr = head;
while (curr != null) {
    Node nextNode = curr.next;
    curr.next = prev;
    prev = curr;
    curr = nextNode;
}
head = prev;
```

### 2. Floyd's Cycle Detection (Fast & Slow Pointer)
```java
// Loop hai ya nahi check karo
Node slow = head, fast = head;
while (fast != null && fast.next != null) {
    slow = slow.next;
    fast = fast.next.next;
    if (slow == fast) {
        System.out.println("Cycle detected!");
        break;
    }
}
```

### 3. Middle of LinkedList
```java
Node slow = head, fast = head;
while (fast != null && fast.next != null) {
    slow = slow.next;
    fast = fast.next.next;
}
// slow = middle node
System.out.println("Middle: " + slow.data);
```

---

## 🔷 Practice Problems (LeetCode)

| #  | Problem                              | Difficulty |
|----|--------------------------------------|------------|
| 1  | Reverse Linked List                  | Easy       |
| 2  | Middle of the Linked List            | Easy       |
| 3  | Linked List Cycle                    | Easy       |
| 4  | Merge Two Sorted Lists               | Easy       |
| 5  | Remove Nth Node From End of List     | Medium     |

---

## ✅ Aaj ka Summary

- LinkedList mein har node ke paas data + next pointer hota hai
- Array se better hai jab frequent insert/delete ho
- **Fast & Slow pointer** — cycle detection aur middle find karne ke liye
- LeetCode pe **Reverse Linked List** se shuru karo

---
