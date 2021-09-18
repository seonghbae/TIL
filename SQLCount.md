# MYSQL COUNT 함수
- SELECT 쿼리로 반환된 결과의 개수를 반환합니다.
    `COUNT(필드/문자열/조건문)`

- 특정 컬럼에서 데이터당 개수 세기

    ```sql
    SELECT 테이블1.컬럼1, COUNT(테이블1.컬럼2) AS COUNT
    FROM 테이블1
    GROUP BY 테이블1.컬럼2
    ```

- 중복 제거하기 : `COUNT(DISTINCT 테이블1.컬럼)`
- 중복 제거 조건 : `COUNT(DISTINCT (CASE WHEN 조건 THEN 반환 값 END))`

# 출처
https://chobopark.tistory.com/117