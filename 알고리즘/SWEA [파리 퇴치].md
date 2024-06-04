# SWEA [파리 퇴치]
```python
for tc in range(1, int(input())+1):
    N, M = map(int, input().split())
    arr = [list(map(int, input().split())) for _ in range(N)]
    max_sum = 0

    for i in range(N-M+1):
        for l in range(N-M+1):
            total_sum = sum(arr[x][y] for x in range(i, i+M) for y in range(l, l+M))
            max_sum = max(max_sum, total_sum)

    print(f'#{tc} {max_sum}')
```
