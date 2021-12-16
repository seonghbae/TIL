# sqrt(ans)의 ceil 값 계산
- 처음으로 mid보다 큰 제곱수가 나오면 그 수 출력
    ```cpp
    for(int i=0; i<=2000; i++) {
        if(i*i>=ans) {
            cout << i;
            return;
        }
    }
    ```

# 비트 활용
- select | need == select, select & need == need : need를 select가 모두 커버