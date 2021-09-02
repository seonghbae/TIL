# SQL 두 개 이상의 테이블 사용
- 단순 조인

    ```sql
    SELECT 테이블1.컬럼, 테이블2.컬럼
    FROM 테이블1, 테이블2
    WHERE 조건;
    ```

- NATURAL join

    ```sql
    SELECT 테이블1.컬럼, 테이블2.컬럼
    FROM 테이블1
    NATURAL JOIN 테이블2
    WHERE 조건;
    ```

- USING : 몇 개의 컬럼 이름이 일치하고 데이터 타입이 다른 경우 하나의 컬럼을 기준으로 검색하는 문법입니다.

    ```sql
    SELECT 테이블1.컬럼, 테이블2.컬럼
    FROM 테이블1
    JOIN 테이블2
    USING (컬럼);
    ```

- alias 사용

    ```sql
    SELECT 테이블1약어.컬럼, 테이블2약어.컬럼
    FROM 테이블1 테이블1약어
    JOIN 테이블2 테이블2약어
    USING (컬럼);
    ```

- FULL(Two_way) OUTER join : 행이 조인 조건을 만족하지 않을 경우 해당 행이 쿼리 결과에 나타나지 않으며 조인 시킬 값이 없는 조인 측에 OUTER 조인 연산자 (+)를 위치시킵니다. 

    ```sql
    SELECT 테이블1.컬럼, 테이블2.컬럼
    FROM 테이블1, 테이블2
    WHERE 조건(+); --table1.colmn=table2.column(+);
    ```

# 출처
https://blog.daum.net/question0921/40