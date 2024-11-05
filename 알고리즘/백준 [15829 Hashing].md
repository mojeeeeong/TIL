# 백준 [15829 Hashing]
```
# 문자(알파벳)를 숫자로 바꿔주어 계산만 면면 된다고 생각함!
# ord(문자) -> 아스키코드 값
# chr(아스키코드 값) -> 문자

import sys

N = int(sys.stdin.readline())
alpha = sys.stdin.readline()

ans = 0

for i in range(N):
    ans += (ord(alpha[i]) - ord('a') + 1) * (31 ** i)

print(ans % 1234567891)
```
