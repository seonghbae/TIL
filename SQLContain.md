# MYSQL LIKE 함수
- 특정 문자열을 포함하는 데이터를 검색합니다.
- `SELECT [컬럼명] FROM [테이블명] WHERE [컬럼명] LIKE '특정문자열'`
    - `'특정문자열%'` : 특정문자열로 시작
    - `'%특정문자열'` : 특정문자열로 끝
    - `'%특정문자열%'` : 특정문자열 포함
    - `'특정문자열?'` : 특정문자열+한글자

# 출처
https://gap85.tistory.com/entry/SQL-%ED%8A%B9%EC%A0%95-%EB%AC%B8%EC%9E%90%EA%B0%80-%ED%8F%AC%ED%95%A8%EB%90%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B2%80%EC%83%89