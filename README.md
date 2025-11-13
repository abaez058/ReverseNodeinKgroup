# 🧩 Reverse Nodes in k-Group

## 📘 Problem Description
Given the head of a linked list, reverse the nodes of the list in groups of size `k` and return the modified list.  
If the number of nodes is not a multiple of `k`, the remaining nodes at the end should remain in their original order.

This solution corresponds to **LeetCode Problem #25 – Reverse Nodes in k-Group**.

---

## 🧠 Example

**Input:**
head = [1,2,3,4,5], k = 2

makefile
Copy code

**Output:**
[2,1,4,3,5]

python
Copy code

**Explanation:**
- The first group `[1,2]` is reversed → `[2,1]`
- The second group `[3,4]` is reversed → `[4,3]`
- The last node `[5]` remains unchanged (since there are fewer than `k=2` nodes left)

---

## 💡 Approach

1. **Find the kth node ahead:**  
   The helper function `get_kth(curr, k)` moves `k` steps ahead from the current node.  
   If fewer than `k` nodes remain, it returns `None` to indicate no more groups can be reversed.

2. **Reverse each k-group:**  
   Once a valid `kth` node is found, reverse the nodes between `group_prev.next` and `kth.next` using standard linked list reversal logic.

3. **Reconnect the reversed group:**  
   After reversing, connect the reversed portion back into the main list and move `group_prev` to the end of the newly reversed segment.

4. **Repeat until there are no full groups left.**

---
