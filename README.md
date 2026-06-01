# 🚀 LRU Cache Implementation in C++

An efficient implementation of the **Least Recently Used (LRU) Cache** using **HashMap (unordered_map)** and **Doubly Linked List** to achieve **O(1)** time complexity for both `get()` and `put()` operations.

This is one of the most frequently asked System Design and Data Structure interview problems in companies like Amazon, Microsoft, Google, Meta, Adobe, and Walmart.

---

## 📌 Problem Statement

Design a data structure that follows the constraints of an **LRU Cache**.

Implement the following operations:

### get(key)
- Returns the value of the key if it exists.
- Returns `-1` if the key is not present.
- Marks the accessed key as the **Most Recently Used (MRU)**.

### put(key, value)
- Inserts a new key-value pair.
- Updates the value if the key already exists.
- If the cache reaches its capacity, removes the **Least Recently Used (LRU)** item before inserting a new one.

---

## 🏗️ Approach

The cache is implemented using:

### 1️⃣ HashMap (`unordered_map`)
Stores key-node mappings for direct access.

```cpp
unordered_map<int, Node*> cache;
```

Provides O(1) lookup time.

### 2️⃣ Doubly Linked List

Maintains the order of usage.

```text
HEAD <-> Most Recently Used Nodes <-> Least Recently Used Node <-> TAIL
```

- Head side → Most Recently Used (MRU)
- Tail side → Least Recently Used (LRU)

---

## ⚡ How It Works

### GET Operation

1. Check if key exists in HashMap.
2. If not found, return `-1`.
3. Remove node from current position.
4. Move node to the front (MRU position).
5. Return the value.

### PUT Operation

1. If key already exists:
   - Remove existing node.
   - Update value.
2. If cache is full:
   - Remove the LRU node (node before tail).
3. Insert the new node at the front.
4. Update HashMap.

---

## 📊 Example

### Capacity = 2

```text
put(1,10)

HEAD <-> [1,10] <-> TAIL
```

```text
put(2,20)

HEAD <-> [2,20] <-> [1,10] <-> TAIL
```

```text
get(1)

HEAD <-> [1,10] <-> [2,20] <-> TAIL
```

```text
put(3,30)
```

Cache is full.

Least Recently Used node:

```text
[2,20]
```

After eviction:

```text
HEAD <-> [3,30] <-> [1,10] <-> TAIL
```

---

## ⏱️ Complexity Analysis

| Operation | Time Complexity |
|------------|----------------|
| get() | O(1) |
| put() | O(1) |
| addNode() | O(1) |
| delNode() | O(1) |

### Space Complexity

```text
O(capacity)
```

---

## 🧠 Key Concepts Used

- Hashing
- Doubly Linked List
- Cache Eviction Policies
- O(1) Optimization
- System Design Fundamentals
- Data Structure Design

---

## 🎯 Interview Questions Covered

- Design an LRU Cache.
- Why use a Doubly Linked List?
- Why combine HashMap and Linked List?
- Difference between LRU and LFU Cache.
- How to make LRU Cache thread-safe?
- Real-world applications of LRU Cache.
- How does cache eviction work?

---

## 🌍 Real-World Applications

- Browser Cache
- Operating System Page Replacement
- Database Buffer Management
- Redis Cache Eviction
- CDN Content Caching
- API Response Caching
- Memory Management Systems

---

## 🛠️ Technologies Used

- C++
- STL
- unordered_map
- Doubly Linked List

---

## 📂 Project Structure

```text
LRU_Cache/
│
├── LRU_Cache.cpp
└── README.md
```

---

## ⭐ Features

✅ O(1) Get Operation  
✅ O(1) Put Operation  
✅ Efficient Memory Usage  
✅ Interview-Friendly Implementation  
✅ System Design Concept Demonstration  

---

## 👨‍💻 Author

**Tapan Ray**
