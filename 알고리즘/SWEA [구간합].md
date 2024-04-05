# SWEA [구간합]
```python
T = int(input())    #테스트 케이스를 받는다.

for tc in range(1, T+1):    #테스트 케이스 수만큼 반복
    N, M = map(int, input().split())    #N(정수의 개수), M(구간의 개수)
    nums = list(map(int, input().split()))  #N개의 숫자를 리스트로 받는다.
    total_sum = []      #구간마다의 합을 넣어놓기 위해 빈 리스트 생성
    for i in range(N-M+1):  #구간마다 반복
        total_sum.append(sum(nums[i:i+M]))  #구간의 합을 리스트에 추가
    print(f'#{tc} {max(total_sum) - min(total_sum)}')
```
