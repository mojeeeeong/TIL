# SWEA [풍선팡2]
```python
'''
처음 풀었을 때는 어떤 식을 해야할지 잘 몰라서 우선 방향을 아예 정해서 작성했다.
'''

T = int(input())    # 테스트 케이스 수를 받는다.

for tc in range(1, T+1):    # 테스트 케이스
    N, M = map(int, input().split())    # N x M 개
    balloon = [list(map(int, input().split())) for _ in range(N)]   # 풍선을 N x M 로 받는다.
    
    max_value = 0   # 합의 최대를 받기 위해

    dr = [-1, 1 ,0 ,0] # 상 하 좌 우
    dc = [0, 0, -1, 1]

    for r in range(N):  # 행을 반복
        for c in range(M):  # 열을 반복
            now_value = 0   # 현재 더한 값을 받기 위해
            now_value += balloon[r][c]  # 해당 행과 열에 있는 값을 더한다.
            up = r + dr[0]      #위쪽 아래쪽 왼쪽 오른쪽 인덱스를 만든다.
            down = r + dr[1]
            left = c + dc[2]
            right = c + dc[3]
            if 0 <= up < N:                     # 위 아래 왼 오른 각각 맵 안에 존재하면 현재 값에 더해라
                now_value += balloon[up][c]
            if 0 <= down < N:
                now_value += balloon[down][c]
            if 0 <= left < M:
                now_value += balloon[r][left]
            if 0 <= right < M:
                now_value += balloon[r][right]
            max_value = max(now_value, max_value)   # 현재 값과 최댓값을 비교해서 큰 값을 최댓값으로
    
    print(f'#{tc} {max_value}')
```
행과 열을 반복할 때 조금 줄일 수 있는 방법이 없을까 생각하고                        
조금 정리를 해보았다..
```python
T = int(input())    # 테스트 케이스 수를 받는다.

for tc in range(1, T+1):    # 테스트 케이스
    N, M = map(int, input().split())    # N x M 개
    balloon = [list(map(int, input().split())) for _ in range(N)]   # 풍선을 N x M 로 받는다.
    
    max_value = 0   # 합의 최대를 받기 위해

    dr = [-1, 1 ,0 ,0] # 상 하 좌 우
    dc = [0, 0, -1, 1]

    for r in range(N):  # 행을 반복
        for c in range(M):  # 열을 반복
            now_value = 0   # 현재 값을 받기 위해
            now_value += balloon[r][c]  #해당 행과 열에 있는 값을 더한다.
            for d in range(4):  # 방향을 사용한다.
                nr, nc = r + dr[d], c + dc[d]   # 우선 nr, nc를 구해본다.
                if 0 <= nr < N and dr[d] != 0:  # 구한 값이 맵 안에 있고 dr[d]가 0이면 nr과 r이 겹치기 때문에 한 번 더 더해지므로 빼고
                    now_value += balloon[nr][c]
                if 0 <= nc < M and dc[d] != 0:
                    now_value += balloon[r][nc]
                max_value = max(now_value, max_value)
    
    print(f'#{tc} {max_value}')
```
분명 더 좋은 방법이 있을 것 같은데...                  
나는 아직은 잘 모르겠다...              
수업을 들어보면서 다시 또 생각해봐야겠다!!!
