# Last Recently Used (LRU) Cache

A Least Recently Used Cache organizes items in order of use, allowing you to quickly identify which item hasn't been used the longest amount of time. LRU caache is often implemented using a queue (implemented by doubly linked list) and a hash map.

Pros:
- Super fast accesses - `O(1)` get operation
- Super fast updates - `O(1)` put operation
Cons:
- Space heavy - LRU tracks `n` items using a linked list of length `n` and a hashmap holding `n` items. `O(n)` but still 2 data structures.

## Get algorithm
Look up item in hashmap
- If hit, item is in hashmap and in cache. Find the linked list node of the item and move it to head of the linked list.
- If miss, return nothing.

## Put algorithm
Look up item in hashmap
- If hit, item is in hashmap and in cache.
    - Find the linked list node of the item and move it to head of the linked list.
    - Update item's value with new value.
- If miss, load item into cache
    - Create new linked list node and add to head of the linked list.
    - If cache is full, evict the tail node and remove it from hashmap.
    - Add item to hashmap.
