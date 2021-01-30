# Sentinel Node

Sentinel node simplifies the implementation of linked lists. A sentinel node is a dummy node that goes to the front of a linked list. In doubly linked list, the sentinel node points to the first and last elements of the list.
Benefits:
- We no longer have to keep separate pointers for head and tail of the list.
- We do not have to worry about updating the head and tail pointers.
- Prepend list can be done by inserting after a sentinel node.
- Append list can be done by inserting before a sentinel node.

Example:
```python
class Node:
    def __init__(self, key, val):
        self.key = key
        self.value = val
        self.freq = 1
        self.prev = None
        self.next = None

class DLinkedList:
    def __init__(self):
        self.sentinel = Node(None, None)
        self.sentinel.next = self.sentinel
        self.sentinel.prev = self.sentinel
        self.size = 0

    def __len__(self):
        return self.size

    def prepend(self, node):
        # prepend the node to the head of the linked list
        node.next = self.sentinel.next
        node.prev = self.sentinel
        node.next.prev = node
        self.sentinel.next = node
        self.size += 1

    def append(self, node):
        # append the node to the tail of the linked list
        node.prev = self.sentinel.prev
        node.next = self.sentinel
        node.prev.next = node
        self.sentinel.prev = node
        self.size += 1

    def pop(self, node=None):
        # Remove node from linked list (default to tail node if no node provided)
        if self.size == 0:
            return

        if not node:
            node = self.sentinel.prev # pop tail node

        node.prev.next = node.next
        node.next.prev = node.prev
        self.size -= 1

        return node
```
