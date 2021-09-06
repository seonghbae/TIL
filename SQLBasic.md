# SQL 기본
```sql
SELECT 컬럼명
FROM 테이블명
WHERE 테이블 조건
GROUP BY 컬럼명
HAVING 그룹 조건
ORDER BY 컬럼명
```
접근 순서
1. FROM : 테이블을 가장 먼저 확인합니다.
2. WHERE : 테이블에서 주어진 조건에 맞는 데이터를 추출합니다.
3. GROUP BY : 추출한 데이터에서 공통적인 데이터를 묶어 그룹을 만듭니다.
4. HAVING : 그룹 중 주어진조건에 맞는 그룹을 추출합니다.
5. SELECT : 추출된 데이터를 조회합니다.
6. ORDER BY : 추출된 데이터를 정렬합니다. (SELECT에서 만들어진 alias는 여기서만 사용 가능합니다.)

# 조건문
- IF : `IF(조건문, 참일 때의 값, 거짓일 때의 값)`
- IFNULL(MYSQL) : `IFNULL(column_name, 값이 NULL일 경우 대체할 값)`
- ISNULL(MSSQL) : `ISNULL(column_name, 값이 NULL일 경우 대체할 값)`
- CASE WHEN : `CASE value 혹은 조건 WHEN value1 THEN result1 WHEN value2 THEN result2 … [ELSE else_result] END`

    ```sql
    SELECT
	    CASE
		    WHEN permission_type_id = 1
		    THEN '관리자'
		    WHEN permission_type_id = 2
		    THEN '판매자'
		    ELSE '일반 유저'
    END	
    ```
- NVL(ORACLE) : `NVL(column_name, 값이 NULL일 경우 대체할 값)`

# 출처
https://data-make.tistory.com/23
https://velog.io/@pm1100tm/MySQL-%EC%A1%B0%EA%B1%B4%EB%AC%B8-%EC%A0%95%EB%A6%AC