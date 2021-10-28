# Mergesort

Mergesort is a **divide and conquer** algorithm. It divides the input array into two halves, calls itself for the two halves, and then merges the two sorted halves. The `merge()` function is used for merging two halves. The `merge(arr, l, m, r)` is a key process that assumes that `arr[l..m]` and `arr[m+1..r]` are sorted and merges the two sorted sub-arrays into one.

![Example](images/mergesort_example.png)

## Complexities
- Time Complexity: O(n log n). Mergesort always divides the array into two halvs and take linear time to merge two halves.
- Space Complexity: O(n)

## Applications
- Sorting linked list in O(n log n) time. Mergesort accesses data sequentially and does not need random access.
- [Inversion Count Problem](https://www.geeksforgeeks.org/counting-inversions/)
- [External Sorting](https://en.wikipedia.org/wiki/External_sorting)

## Example Code

```python3
# Python program for implementation of MergeSort
def mergeSort(arr: List[int]):
    if len(arr) > 1:

         # Finding the mid of the array
        mid = len(arr)//2

        # Dividing the array elements
        L = arr[:mid]

        # into 2 halves
        R = arr[mid:]

        # Sorting the first half
        mergeSort(L)

        # Sorting the second half
        mergeSort(R)

        i = j = k = 0

        # Copy data to temp arrays L[] and R[]
        while i < len(L) and j < len(R):
            if L[i] < R[j]:
                arr[k] = L[i]
                i += 1
            else:
                arr[k] = R[j]
                j += 1
            k += 1

        # Checking if any element was left
        while i < len(L):
            arr[k] = L[i]
            i += 1
            k += 1

        while j < len(R):
            arr[k] = R[j]
            j += 1
            k += 1
```
