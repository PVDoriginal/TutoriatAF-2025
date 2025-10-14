# Lista de probleme 1 

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
