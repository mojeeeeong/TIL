# SWEA [5174 subtree]
```python
T = int(input())    # 테스트 케이스 받고

for tc in range(1, T+1):
    E, N = map(int, input().split())    # 간선의 개수와 시작 노드 받는다.
    edges = list(map(int, input().split())) # 부모 자식 노드 번호 쌍을 받는다.

    L = [0] * (E+2) # 0부터 E+1까지 만든다!! 0은 사용하지 않는다.
    R = [0] * (E+2)

    for i in range(E):  # 이진 트리 L과 R을 만들기 위해
        parent = edges[2 * i]
        child = edges[2 * i + 1]

        if L[parent] == 0:
            L[parent] = child
        else:
            R[parent] = child

    ans = 0

    # DFS (재귀)
    def DFS(N):
        global ans
        # 방문
        ans += 1    # 방문하자마자 1을 더해줘야한다. 
        # 탐색
        if L[N]:    # L이 있으면 DFS 재귀 -> 있으면 밑의 if R[N]은 시스템 스택에 쌓이는 건가?
            DFS(L[N])

        if R[N]:
            DFS(R[N])

    DFS(N)

    print(f'#{tc} {ans}')
```
