# zip 내장 함수
- iterable 객체를 인자로 받고 각 객체가 담고 있는 원소의 터플 형태로 iterator를 반환
    ```python
    numbers = [1, 2, 3]
    letters = ["A", "B", "C"]
    for pair in zip(numbers, letters):
        print(pair)
    ```

# join 함수
- '구분자'.join(리스트)로 리스트 사이에 구분자를 넣어 하나의 문자열로 합침