*this document is written by MOU(a.k.a MARKDOWN editor)*

# Introduction to Aritificial Intelligence

**Student**, Taekmin Kim(T04902206, tantara.tm@gmail.com)


## HW1 Pacmam Search(~3/12)

*Do Q1 and Q2 in Search Project*

### Files

```
.
+-- README
`-- search.py
```

### Algorithm

#### Depth-First Search

**We** want to find a path from **START**ing point to **GOAL** as soon as possible

1. implement basic dfs algorithm.

2. but use special stack including three elements (current **NODE**, **PATH**, used **NODE**s for **PATH**).

	```
	# search.py#L76
	
	...
		stack = util.Stack()
		stack.push((problem.getStartState(), [], [])) #(STATE, PATH, VISITED)
	```

3. If current **NODE** is **GOAL** on exploring **DFS** tree, this is the answer we want.

	```
	# search.py#L79
	
	...
		while not stack.isEmpty():
	        state, actions, visited = stack.pop()
	
	        if problem.isGoalState(state): #found
	            return actions
	            
	        ... # <- trivial dfs implementation
	```

#### Breadth-First Search

**We** want to find a path from **START**ing point to **GOAL** as soon as possible

1. implement basic bfs algorithm.
2. but use special queue including two elements (current **NODE**, **PATH**).

	```
	# search.py#L92

	...
		queue = util.Queue()
	    queue.push((problem.getStartState(), [])) #(STATE, PATH)
	```

3. If current NODE is GOAL on exploring BFS tree, this is the answer we want.

	```
	# search.py#L95
	
	...
	    visited = []
	    while not queue.isEmpty():
	        state, actions = queue.pop()
	
	        if problem.isGoalState(state):
	            return actions

       		... # <- trivial bfs implementation
	```
	
#### TEST ###

```
# python autograder.py
```

**ALL passed** for Q1, Q2

```
Provisional grades
==================
Question q1: 3/3
Question q2: 3/3
```