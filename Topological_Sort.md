# Topological Sort (Kahn's Algorithm)

Topological sorting for Directed Acyclic Graph (DAG) is a linear ordering of vertices such that for every directed edge `uv`, vertex `u` comes before `v` in the ordering. Topological Sorting for a graph is not possible if the graph is not a DAG.

## Implementation
Kahn's Algorithm:

1. Compute indegree (number of incoming edges) for each vertex in DAG and initialize visited node = 0.
2. Pick all vertices with indegree = 0 and add them to queue.
3. Dequeue a vertex from queue:
    1. Increment count of visited by 1.
    2. Decrease indegree by 1 for all its neighbors.
    3. If indegree of neighboring nodes reaches 0, add them to queue.
4. Repeat step 3 until queue is empty.

```python
def topologicalSorting(edge_list, vertex_list):
    adj_list = {v: [] for v in vertex_list}
    indegree = {}
    for src, dest in edge_list:
        adj_list[dest].append(src)
        indegree[dest] = indegree.get(dest, 0) + 1

    queue = deque([v for v in vertex_list if v not in indegree])
    topological_sorted = []
    while queue:
        v = queue.popleft()
        topological_sorted.append(v)

        for neighbor in adj_list[v]:
            indegree[neighbor] -= 1

            if indegree[neighbor] == 0:
                queue.append(neighbor)

    return topological_sorted
```
