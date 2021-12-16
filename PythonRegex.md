# 정규표현식
- re.fullmatch() 함수 활용
    ```python
    import sys
    import re
    si = sys.stdin.readline

    p= re.compile('(AAB+|BAB+A)+')
    n = int(si())

    ans = 0
    for _ in range(n):
        m = p.fullmatch(si().strip())
        if m:
            ans += 1
    ```