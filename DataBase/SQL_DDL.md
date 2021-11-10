reference: https://terms.naver.com/list.naver?cid=58430&categoryId=58430&so=st4.asc (visited on Nov 10 2021)

## SQL이란?
SQL (Structured Query Language)은 관계 데이터베이스(Relational DataBase)에서의 표준 질의 언어로 사용되며, 기능에 따라 다음과 같이 분류된다.
 * 데이터 정의어 (DDL, Data Definition Language)
 * 데이터 조작어 (DML, Data Manipulation Language)
 * 데이터 제어어 (DCL, Data Control Language)

## 데이터 정의어 (Data Definition Language)
 * 테이블 생성
```
CREATE TABLE tableName (
  attributeName1 dataType1 [NOT NULL] [DEFAULT defaultValue1]
  attributeName2 dataType2 [NOT NULL] [DEFAULT defaultValue2]
  ...
  attributeNameN dataTypeN [NOT NULL] [DEFAULT defaultValueN]
  [PRIMARY KEY (attributeName1, attributeName2, ..., attributeNameK)]
  [UNIQUE (attributeName1, attributeName2, ..., attributeNameK)]
  [FOREIGN KEY (attributeName1, attributeName2, ..., attributeNameK) REFERENCE refTableName(refAttributeName1, refAttributeName2, ..., refAttributeNameK)]
  [CONSTRAINT constraintName] [CHECK(condition)]
)
```
 * 테이블 삭제
   * CASCADE: 참조하는 다른 테이블을 함께 삭제
   * RESTRICT: 참조하는 다른 테이블은 함께 삭제하지 않음
```
DROP TABLE tableName CASCADE | RESTRICT
```
 * 속성 추가
```
ALTER TABLE tableName
ADD attributeName dataType [NOT NULL] [DEFAULT defaultValue]
```
 * 속성 삭제
   * CASCADE: 연관된 제약 조건 및 참조하는 다른 속성을 함께 삭제
   * RESTRICT: 연관된 제약 조건 및 참조하는 다른 속성은 함께 삭제하지 않음
```
ALTER TABLE tableName
DROP attributeName CASCADE | RESTRICT
```
 * 제약 조건 추가
```
ALTER TABLE tableName
ADD CONSTRAINT constraintName CHECK(condition)
```
 * 제약 조건 삭제
```
ALTER TABLE tableName
DROP CONSTRAINT constraintName
```
