# SWEA [회문]
```python
T = int(input())    # 테스트 케이스를 받는다.

for tc in range(1, T+1):    # 테스트 케이스만큼 반복
    N, M = map(int, input().split())    # NxN의 글자판, M 길이만큼 회문
    arr = [input() for _ in range(N)]   # ['문자열1', '문자열2', '문자열3'...] 이런식으로 받는다.
    for i in range(N):      # 행이 N이니까
        for j in range(N-M+1):  # 길이가 M인 회문구조를 찾기위해 몇 번 반복해야하는가 -> N-M+1 번
            if arr[i][j:j+M] == arr[i][j:j+M][::-1]:    # 각 행의 M 길이에 해당하는 부분 비교
                print(f'#{tc} {arr[i][j:j+M]}')         # 회문 구조면 출력
    
    new_arr = list(map(''.join, zip(*arr)))     # 전치하는데 문자열이라 문자 하나하나 떨어져서 join 메소드 사용해서 해결
    for k in range(N):          # 위와 동일한 방식
        for l in range(N-M+1):
            if new_arr[k][l:l+M] == new_arr[k][l:l+M][::-1]:
                print(f'#{tc} {new_arr[k][l:l+M]}')
```
