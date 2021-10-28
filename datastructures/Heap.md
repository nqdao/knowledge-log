# Heap

Heap is a special case of balanced binary tree data structure where the root-node key is compared with its children and arranged accordingly.

Min Heap - the value of the root node is less tahn or equal to either of its children.

Max Heap - the value of the root node is greater than or equal to either of its children.

How is Max Heap is represented?

A Max heap is typically represented as an array. The root element will be at `Arr[0]`. Below table shows indexes of other nodes for the `i`th node, i.e., `Arr[i]`:
- `Arr[(i-1)/2]` Returns the parent node.
- `Arr[(2*i)+1]` Returns the left child node.
- `Arr[(2*i)+2]` Returns the right child node.

## Operations on Max Heap
- `getMax()`: It returns the root element of Max Heap. Time Complexity of this operation is `O(1)`.
- `extractMax()`: Removes the maximum element from MaxHeap. Time Complexity of this Operation is `O(Log n)` as this operation needs to maintain the heap property (by calling heapify()) after removing root.
- `insert()`: Inserting a new key takes `O(Log n)` time. We add a new key at the end of the tree. If new key is smaller than its parent, then we don’t need to do anything. Otherwise, we need to traverse up to fix the violated heap property.

## Max Heap Construction Algorithm
1. Create a new node at the end of heap
2. Assign new value to the node
3. Compare the value of this child node to its parent
4. If value of parent is less than child, swap them. (if value of parent is greater than child for Min Heap)
5. Repeat 3 & 4 until heap property holds.

## Max Heap Deletion Algorithm
1. Remove root node
2. Move the last element of last level to root
3. Starting from root node, compare the value of node with its children.
4. If value of parent is less than child, swap them (if value of parent is greater than child for Min Heap)
5. repeat 3 & 4 until heap property holds.

## Heapify
To heapify subtree rooted at index i, n is size of heap

```python3
def heapify(arr: List[int], n: int, i: int):
    largest = i  # Initialize largest as root
    l = 2 * i + 1     # left = 2*i + 1
    r = 2 * i + 2     # right = 2*i + 2

    # See if left child of root exists and is
    # greater than root
    if l < n and arr[largest] < arr[l]:
        largest = l

    # See if right child of root exists and is
    # greater than root
    if r < n and arr[largest] < arr[r]:
        largest = r

    # Change root, if needed
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]  # swap

        # Heapify the root.
        heapify(arr, n, largest)
```
