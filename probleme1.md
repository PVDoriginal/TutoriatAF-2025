# Lista de probleme 1 

## DFS 
Parcurgerea DFS a unui graf.
[Link problema](https://www.pbinfo.ro/probleme/539/dfs). 

<details>

<summary>Solutie Python</summary>

```python
file = open("dfs.in")
out = open("dfs.out", "w")

def dfs(a):
    visited[a] = True
    out.write(str(a + 1) + " ")

    for b in sorted(graf[a]):
        if not visited[b]:
            dfs(b)

n, m, x = map(int, file.readline().split())

graf = [[] for _ in range(n)]
visited = [False for _ in range(n)]

for _ in range(m):
    a, b = map(int, file.readline().split())

    graf[a - 1].append(b - 1)
    graf[b - 1].append(a - 1)

dfs(x - 1)

```

</details>

## BFS 
Parcurgerea BFS a unui graf.
[Link problema](https://www.pbinfo.ro/probleme/19/bfs). 

<details>

<summary>Solutie Python</summary>

```python
file = open("BFS.in")
out = open("BFS.out","w")

n, m, x = map(int, file.readline().split())

graf = [[] for _ in range(n)]
visited = [False for _ in range(n)]

for _ in range(m):
    a, b = map(int, file.readline().split())

    graf[a - 1].append(b - 1)
    graf[b - 1].append(a - 1)

queue = [x - 1]
visited[x - 1] = True

while queue:
    a = queue.pop(0)
    out.write(str(a + 1) + " ")

    for b in sorted(graf[a]):
        if not visited[b]:
            queue.append(b)
            visited[b] = True

```

</details>

## Arbore
Determinarea unei liste de parinti dintr-un graf aciclic 
[Link problema](https://www.pbinfo.ro/probleme/636/arbore). 

<details>

<summary>Solutie Python</summary>

```python
file = open("arbore.in")
out = open("arbore.out", "w")

def find_parents(a):
    for b in sorted(graf[a]):
        if parents[b] == -1:
            parents[b] = a + 1
            find_parents(b)

n, k = map(int, file.readline().split())

graf = [[] for _ in range(n)]

for _ in range(n - 1):
    a, b = map(int, file.readline().split())

    graf[a - 1].append(b - 1)
    graf[b - 1].append(a - 1)

parents = [-1 for _ in range(n)]
parents[k - 1] = 0

find_parents(k - 1)

for i in parents:
    out.write(str(i) + " ")
```

</details>
