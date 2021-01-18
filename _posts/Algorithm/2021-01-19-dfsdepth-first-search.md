---
title: DFS(Depth First Search) 깊이우선탐색
category: Algorithm
New field 2: Python
---

{% highlight python linenos %}
graph = [
    [],
    [2,3,8],
    [1,7],
    [1,4],
    [3,5],
    [3,4],
    [7],
    [2,6,8],
    [1,7]

]

visited = [False] * 9

def dfs(graph,v,visited):
    visited[v] = True
    print(v,end=' ')
    for i in graph[v]:
        if not visited[i]:
            dfs(graph,i,visited)
        
dfs(graph,1,visited)

{% endhighlight %}
