# Lambda Function

A lambda function is a small anonymou7s function. A lambda function can take any number of arguments, but can only have one expression.

## Syntax
```
lambda <arguments> : <expression>
```

Example:
Add 10 to argument `a`, and return the result:
```python3
x = lambda a : a + 10
print(x(5)) # 15
```

Multiply argument `a` by argument `b` and return result:
```python3
x = lambda a, b : a * b
print(x(5, 6))
```

## Why Use Lambda Functions?
The power of lambda is better shown when you use them as an anonymous function inside another function.

Example: [Finding K closest points from origin](https://leetcode.com/problems/k-closest-points-to-origin/)
```python3
# sort by key = euclidean distance
class Solution:
    def kClosest(self, points: List[List[int]], K: int) -> List[List[int]]:
        points.sort(key = lambda p: p[0]**2 + p[1]**2)
        return points[:K]
```
