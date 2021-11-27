reference: https://terms.naver.com/list.naver?cid=58430&categoryId=58430&so=st4.asc (visited on Nov 27 2021)

## 데이터 삽입
```tableName``` 테이블에 ```attribute1, attribute2, ..., attributeN``` 속성들의 값이 ```value1, value2, ..., valueN```인 튜플 삽입:
```
INSERT INTO tableName(attribute1, attribute2, ..., attributeN)
VALUES (value1, value2, ..., valueN)
```

## 데이터 수정
```tableName``` 테이블의 ```condition``` 조건에 맞는 모든 튜플에 대해, ```attribute1, attribute2, ..., attributeN``` 속성들의 값을 각각  ```value1, value2, ..., valueN```로 바꾸는 SQL문:
```
UPDATE tableName
SET attribute1=value1, attribute2=value2, ..., attributeN=valueN
WHERE condition
```
* 단, ```WHERE condition```은 조건이 없는 경우 생략할 수 있다.

## 데이터 삭제
```tableName``` 테이블의 ```condition``` 조건에 맞는 모든 튜플을 삭제하는 SQL문:
```
DELETE FROM tableName
WHERE condition
```
