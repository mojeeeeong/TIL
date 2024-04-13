# SWEA [달팽이 숫자]
```python
T = int(input())    # 테스트 케이스 받는다.

dr = [0, 1, 0, -1]  # 우 하 좌 상
dc = [1, 0, -1, 0]

for tc in range(1, T+1):
    N = int(input())

    arr = [[0] * N for _ in range(N)]
    r, c, d = 0, 0, 0   # 행, 열, 방향

    for num in range(1, N ** 2 + 1):
        arr[r][c] = num     # 해당 위치에 숫자 넣는다.

        nr = r + dr[d]  # 게산 하는 건 문제가 안된다. 우선 계산을 해보자
        nc = c + dc[d]

        if nr < 0 or nr >= N or nc < 0 or nc >= N or arr[nr][nc] != 0:  # 여기서가 문제!! 맵을 넘어가면 안되고 다음 숫자를 넣을 곳에 숫자가 0이 아니면 안된다.
            d = (d + 1) % 4     # 만약 맵을 벗어나고 숫자가 0이 아니라면 방향 바꿔주자
            nr = r + dr[d]      # 바꾼 방향으로 다시 계산해주자
            nc = c + dc[d]

        r, c = nr, nc

    print(f'#{tc}')
    for i in range(N):
        print(*arr[i])
```
