# MYSQL CASE문
- WHEN과 THEN은 한쌍dlehl, 다수가 존재할 수 있습니다.
- ELSE가 존재하면 모든 조건에 해당하지 않는 경우에 반환 값을 설정할 수 있으며 ELSE가 존재하지 않고, 조건에 맞지 않아서 반환 값이 없으면 NULL를 반환합니다.
- 예제
    ```sql
    CASE
	    WHEN 조건
	    THEN 반환 값
	    WHEN 조건
	    THEN 반환 값
	    ELSE WHEN 조건에 해당 안되는 경우 반환 값
    END
    ```

# 출처
https://extbrain.tistory.com/46