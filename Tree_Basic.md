# 📚 DSA Notes — Trees (Basics)

> **Date:** 16 MAY 2026  
> **Topic:** Trees (Basics to Important Concepts)

---

## 🔷 Tree kya hota hai?

Tree ek **hierarchical data structure** hai jisme ek root node hota hai
aur usse connected child nodes hote hain — bilkul family tree ki tarah!

```
        10          <-- Root
       /  \
      20   30       <-- Children
     / \     \
    40  50   60     <-- Leaf Nodes
```

---

## 🔷 Important Terms

| Term        | Meaning                                      |
|-------------|----------------------------------------------|
| Root        | Sabse upar wala node                         |
| Parent      | Jiske child nodes hain                       |
| Child       | Kisi node ke neeche wale nodes               |
| Leaf        | Jiske koi child nahi hain                    |
| Height      | Root se sabse neeche tak ki depth            |
| Depth       | Root se us node tak ki distance              |

---

## 🔷 Node kaise banta hai? (Java)

```java
class Node {
    int data;
    Node left;
    Node right;

    Node(int data) {
        this.data = data;
        this.left = null;
        this.right = null;
    }
}
```

---

## 🔷 Binary Tree kya hota hai?

Jisme har node ke **max 2 children** hote hain — left aur right.

```
        1
       / \
      2   3
     / \
    4   5
```

---

## 🔷 Tree Traversals (Bahut important!)

### 1. Inorder — Left, Root, Right
```java
void inorder(Node root) {
    if (root == null) return;
    inorder(root.left);
    System.out.print(root.data + " ");
    inorder(root.right);
}
// Output: 4 2 5 1 3
```

### 2. Preorder — Root, Left, Right
```java
void preorder(Node root) {
    if (root == null) return;
    System.out.print(root.data + " ");
    preorder(root.left);
    preorder(root.right);
}
// Output: 1 2 4 5 3
```

### 3. Postorder — Left, Right, Root
```java
void postorder(Node root) {
    if (root == null) return;
    postorder(root.left);
    postorder(root.right);
    System.out.print(root.data + " ");
}
// Output: 4 5 2 3 1
```

### 4. Level Order (BFS) — Level by level
```java
void levelOrder(Node root) {
    if (root == null) return;
    Queue<Node> queue = new LinkedList<>();
    queue.offer(root);

    while (!queue.isEmpty()) {
        Node node = queue.poll();
        System.out.print(node.data + " ");
        if (node.left != null) queue.offer(node.left);
        if (node.right != null) queue.offer(node.right);
    }
}
// Output: 1 2 3 4 5
```

---

## 🔷 Important Operations

```java
// Height of tree
int height(Node root) {
    if (root == null) return 0;
    return 1 + Math.max(height(root.left), height(root.right));
}

// Count total nodes
int countNodes(Node root) {
    if (root == null) return 0;
    return 1 + countNodes(root.left) + countNodes(root.right);
}

// Search a value
boolean search(Node root, int key) {
    if (root == null) return false;
    if (root.data == key) return true;
    return search(root.left, key) || search(root.right, key);
}
```

---

## 🔷 Time Complexity

| Operation   | Average | Worst  |
|-------------|---------|--------|
| Search      | O(log n)| O(n)   |
| Insert      | O(log n)| O(n)   |
| Delete      | O(log n)| O(n)   |
| Traversal   | O(n)    | O(n)   |

---

## 🔷 Practice Problems (LeetCode)

| #  | Problem                              | Difficulty |
|----|--------------------------------------|------------|
| 1  | Maximum Depth of Binary Tree         | Easy       |
| 2  | Invert Binary Tree                   | Easy       |
| 3  | Symmetric Tree                       | Easy       |
| 4  | Binary Tree Level Order Traversal    | Medium     |
| 5  | Diameter of Binary Tree              | Easy       |

---

## ✅ Aaj ka Summary

- Tree = hierarchical structure, Root se start hota hai
- **4 traversals** yaad rakhna — Inorder, Preorder, Postorder, Level Order
- Level Order ke liye **Queue** use hoti hai
- Height aur Count — recursion se easily solve hote hain
- LeetCode pe **Maximum Depth of Binary Tree** se shuru karo

---
