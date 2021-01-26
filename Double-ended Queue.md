# Double-Ended Queue

Deque or Double-ended Queue is a generalized version of Queue that allows insert and delete at both ends

Operations on Deque:
Mainly the following four basic operations are performed on queue:

- `insertFront()`: Adds an item at the front of Deque.
- `insertLast()`: Adds an item at the rear of Deque.
- `deleteFront()`: Deletes an item from front of Deque.
- `deleteLast()`: Deletes an item from rear of Deque.

In addition to above operations, following operations are also supported
- `getFront()`: Gets the front item from queue.
- `getRear()`: Gets the last item from queue.
- `isEmpty()`: Checks whether Deque is empty or not.
- `isFull()`: Checks whether Deque is full or not.

## Applications
Since Deque supports both stack and queue operations, it can be used as both. The Deque data structure supports clockwise and anticlockwise rotations in O(1) time which can be useful in certain applications.
Also, the problems where elements need to be removed and or added both ends can be efficiently solved using Deque.

## Deque in Python
deque provides `O(1)` time complexity for append and pop operations as compared to `O(n)` in lists.

deque operations:
- `append()` :- This function is used to insert the value in its argument to the right end of deque.
- `appendleft()` :- This function is used to insert the value in its argument to the left end of deque.
- `pop()` :- This function is used to delete an argument from the right end of deque.
- `popleft()` :- This function is used to delete an argument from the left end of deque.
- `index(ele, beg, end)` :- This function returns the first index of the value mentioned in arguments, starting searching from beg till end index.
- `insert(i, a)` :- This function inserts the value mentioned in arguments(a) at index(i) specified in arguments.
- `remove()` :- This function removes the first occurrence of value mentioned in arguments.
- `count()` :- This function counts the number of occurrences of value mentioned in arguments.
- `extend(iterable)` :- This function is used to add multiple values at the right end of deque. The argument passed is an iterable.
- `extendleft(iterable)` :- This function is used to add multiple values at the left end of deque. The argument passed is an iterable. Order is reversed as a result of left appends.
- `reverse()` :- This function is used to reverse order of deque elements.
- `rotate()` :- This function rotates the deque by the number specified in arguments. If the number specified is negative, rotation occurs to left. Else rotation is to right.
