# 트리

## 트리 순회

일반적인 그래프를 순회하는 알고리즘을 트리의 노드를 순회할 때도 적용할 수 있다.
하지만 트리 순회가 일반적인 그래프의 순회보다 구현하기 쉬운데, 트리에는 사이클이 없고 각 노드로 가는 방법이 유일하기 때문이다.

```cpp
void dfs(int s, int e) {
    // 노드 s를 처리한다.
    for(auto u : adj[s]) [
        if(u != e) dfs(u, s);
    ]
}

// 동적계획법
void dfs(int s, int e) {
    count [s] = 1;
    for(auto u : adj[s]) {
        if(u == e) continue;
        dfs(u, s);
        count[s] += count[u];
    }
}
```

## 이진트리 순회

- 전위 순회(DLR): 먼저 루트 노드를 처리한 뒤, 왼쪽 서브트리를 순회한 다음, 루트 노드를 처리한다.
- 중위 순회(LDR): 먼저 왼쪽 서브트리를 순회하고 루트 노드를 처리한 다음 오른쪽 서브트리를 순회한다.
- 후위 순회(LRD): 먼저 왼쪽 서브트리를 순회하고, 오른쪽 서브트리를 순회한 다음, 루트노드를 처리한다.

## 지름 계산하기

트리의 지름은 두 노드간 경로의 길이 중 최댓값이다.

DP를 사용하여 계산할 수도 있고, DFS를 사용하여 계산할 수도 있다.