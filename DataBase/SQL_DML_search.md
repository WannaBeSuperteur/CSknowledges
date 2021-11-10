reference: https://terms.naver.com/list.naver?cid=58430&categoryId=58430&so=st4.asc (visited on Nov 10 2021)

## 데이터 검색
 * 기본 연산자 (Microsoft Excel과 유사)
   * ```=```, ```<>```: 같음, 다름
   * ```<```, ```>```, ```<=```, ```>=```: 작음, 큼, 작거나 같음, 크거나 같음
   * ```AND```, ```OR```, ```NOT```: 모든 조건 만족, 1개 이상의 조건 만족, 조건 불만족
 * 조건을 이용한 기본 검색
```
SELECT [DISTINCT] attributeName1, attributeName2, ..., attributeNameK
FROM tableName1, tableName2, ..., tableNameL
WHERE condition1, condition2, ..., conditionM
```
 * LIKE 키워드를 이용한 검색
   * ```%```: 0글자 이상의 문자열
   * ```_```: 1글자의 문자열
   * ```attributeName LIKE 'X%'```: ```attributeName``` 속성의 값이 ```X```로 시작하는 문자열임
   * ```attributeName LIKE '%X'```: ```attributeName``` 속성의 값이 ```X```로 끝나는 문자열임
   * ```attributeName LIKE '%X%'```: ```attributeName``` 속성의 값이 ```X```를 포함하는 문자열임
 * IS NULL 키워드를 이용한 검색
   * ```attributeName IS NULL```: ```attributeName``` 속성의 값이 ```NULL```임
   * ```attributeName IS NOT NULL```: ```attributeName``` 속성의 값이 ```NULL```이 아님
 * 정렬
   * ```ORDER BY attributeName1 ASC, attributeName2 DESC, attributeName3 DESC```: 1순위로 ```attributeName1``` 속성을 기준으로 **오름차순**, 2순위로 ```attributeName2``` 속성을 기준으로 **내림차순**, 3순위로 ```attributeName3``` 속성을 기준으로 **내림차순** 정렬
```
SELECT ...
FROM ...
WHERE ...
[ORDER BY attributeName1 ASC, attributeName2 DESC, attributeName3 DESC]
```

## 고급 데이터 검색
### 집계 함수 COUNT, MAX, MIN, SUM, AVG
 * ```COUNT(attributeName)```: ```attributeName``` 속성 값이 있는 레코드의 개수
 * ```COUNT(DISTINCT(attributeName))```: **중복되지 않는** ```attributeName``` 속성 값이 있는 레코드의 개수
 * ```MAX(attributeName)```: ```attributeName``` 속성 값의 최댓값
 * ```MIN(attributeName)```: ```attributeName``` 속성 값의 최솟값
 * ```SUM(attributeName)```: ```attributeName``` 속성 값의 합계
 * ```AVG(attributeName)```: ```attributeName``` 속성 값의 평균
```
SELECT COUNT | MAX | MIN | SUM | AVG(attributeName)
FROM ...
WHERE ...
```

### GROUP BY, HAVING
 * ```GROUP BY attributeName HAVING condition```: ```attributeName``` 속성값이 같은 튜플을 모아서 그룹 생성 및 그룹별로 ```condition```을 조건으로 하여 검색
 * ```GROUP BY attributeName1, attributeName2 HAVING condition```: ```attributeName1```, ```attributeName2``` 속성값이 모두 같은 튜플을 모아서 그룹 생성 및 그룹별로 ```condition```을 조건으로 하여 검색
```
SELECT ...
FROM ...
WHERE ...
[GROUP BY attributeName1, attributeName2, attributeName3 HAVING condition]
```

### 여러 테이블의 조인 검색
 * ```tableName1```, ```tableName2``` 테이블에서 ```tableName1.attributeName1```(```tableName1``` 테이블의 ```attributeName1``` 속성의 값) 및 ```tableName2.attributeName2```(```tableName2``` 테이블의 ```attributeName2``` 속성의 값)을 가져온다.
 * 이때, ```condition``` 조건에 맞는 레코드만 가져온다.
 * ```tableName1.primaryKey = tableName2.foreignKey``` 조건을 통해 두 테이블의 서로 연관된 속성끼리 join한다. 즉, ```tableName1```의 기본키와 그것을 참조하는 ```tableName2```의 외래키의 값이 서로 같다는 조건을 이용한다.
   * 또는 가능한 경우, ```tableName2```의 기본키와 그것을 참조하는 ```tableName1```의 외래키의 값이 서로 같다는 조건을 이용해도 된다. 
```
SELECT tableName1.attributeName1, tableName2.attributeName2
FROM tableName1, tableName2
WHERE condition AND tableName1.primaryKey = tableName2.foreignKey
```
