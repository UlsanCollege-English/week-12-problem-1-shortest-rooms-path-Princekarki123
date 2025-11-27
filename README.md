[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/25DAuULc)
# hw01 – Finding Shortest Rooms Path with BFS

## Story

You are in a science museum with many rooms.  
Each room is connected by doors. All doors are “equal”: walking through any door takes the same time.

You want to help visitors find a **shortest sequence of rooms** from a **start room** to a **target room**.

We will model the museum as a **graph** and use **Breadth-First Search (BFS)**.

---

## Task

Write a function:

```python
bfs_shortest_path(graph, start, goal)
```

`graph`: a dictionary: `room -> list of neighbouring rooms`

`start`: starting room name (string)

`goal`: target room name (string)

## Return:

- A list of rooms from start to goal that uses the fewest doors (edges), or

- An empty list [] if there is no path, or if start or goal is not in graph.

## Constraints
- `graph` has at most 100 rooms.

- Room names are strings without spaces (e.g. `"Hall1"`, `"LabA"`).

- All doors are unweighted (same cost).

- Use BFS (queue-based, layer-by-layer search).

- Expected time complexity: O(V + E), where

    - `V` = number of rooms (nodes)

    - `E` = number of doors (edges)

## 8 Steps of Coding – Scaffold (hw01)
Use these steps in your comments and on paper.

1. Read & Understand

    - Write 1–2 sentences (in your own words) about the problem.

1. Re-phrase

    - Write a simple English version, for example:

        - “Find a path with the fewest edges from start to goal.”

1. Identify Input / Output / Variables

    - List:

        - Inputs: graph, start, goal
        
        - Output: path list
    
        - Main data structures: queue, visited, parent

1. Break Down the Problem

    - Plan BFS:
    
        - How will you pick the next room?
        
        - How will you avoid visiting rooms twice?
        
        - How will you remember the path?
    
1. Pseudocode

    - Write high-level steps (no Python yet) in comments.

1. Write the Code (Hint)

    - Translate your pseudocode into Python.

    - You can use collections.deque for the queue.

1. Debug (Hint)

    - Test by hand on a tiny graph.
    
    - Check path when start == goal and when no path exists.

1. Optimize (Hint)

    - Think: does your algorithm visit each room/door at most a few times?

    - Can you explain why it is O(V + E)?

## Hints (not full solutions)

1. ark rooms as visited as soon as you enqueue them.

1. Use a parent dictionary: parent[child_room] = previous_room.

1. After BFS finishes, rebuild the path by walking backward from goal to start using parent, then reverse the list.

## How to Run Tests
```python -m pytest -q```



## FAQ
Q1: Do I read from input() or use function arguments?
A1: Use the function arguments. The tests will call bfs_shortest_path(graph, start, goal) directly.

Q2: Can I change the function name or parameters?
A2: No. Tests import bfs_shortest_path from main.py. Keep the name and parameters the same.

Q3: What Big-O time is expected?
A3: O(V + E) using BFS with a queue. A slow method (e.g. trying all paths) may time out on big tests.

Q4: What if there are many shortest paths?
A4: You may return any one shortest path. Tests check length and validity, not the exact sequence.

Q5: What happens if start or goal is missing from graph?
A5: Return an empty list []. The tests expect this.

Q6: How do I read pytest failures?
A6: Look at:

- The test name (e.g. test_disconnected_graph_returns_empty_path)

- The “Expected” vs “Got” lines
- This tells you which case failed and what your function returned.

Q7: How is grading done?
A7: We mainly check:

- All tests pass.

- Code is clear and uses BFS (no brute force).

- You follow the 8 Steps in comments or notes.