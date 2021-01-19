# Priority Queue

Priority Queue is an extension of `queue` with following properties:
- Every item has a priority associated with it.
- An element with high priority is dequeued before an element with lower priority.
- If two elements have the same priority, they are served according to their order in the queue.

Operations:
- `insert(item, priority)`: Inserts an item with given priority.
- `getHighestPriority()`: Returns the highest priority item.
- `deleteHighestPriority()`: Removes the highest priority item.

Implementation:
Heap is generally preferred for priority queue because heaps provide better performance than array or linked list.
In a Binary Heap:
- `getHighestPriority()` has `O(1)` time
- `insert()` has `O(logn)` time
- `deleteHighestPriority()` has `O(logn)` time

Typical Applications:
- CPU Scheduling
- Dijkstra's shortest path algorithm, Prim's Minimum Spanning Tree
- Any queue applications that require priority

Example:

[Merge K sorted lists](https://leetcode.com/problems/merge-k-sorted-lists/)
```python
from Queue import PriorityQueue

class Solution(object):
    def mergeKLists(self, lists):
        """
        :type lists: List[ListNode]
        :rtype: ListNode
        """
        head = point = ListNode(0)
        q = PriorityQueue()
        for l in lists:
            if l:
                q.put((l.val, l))
        while not q.empty():
            val, node = q.get()
            point.next = ListNode(val)
            point = point.next
            node = node.next
            if node:
                q.put((node.val, node))
        return head.next
```
