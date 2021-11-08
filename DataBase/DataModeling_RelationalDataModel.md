reference: https://terms.naver.com/list.naver?cid=58430&categoryId=58430&so=st4.asc (visited on Nov 08 2021)

## 관계 데이터 모델
관계 데이터 모델은 한 개체에 대한 데이터를 표(relation, 릴레이션)에 저장한다.

## 릴레이션의 특성
 * 튜플의 유일성: 한 릴레이션에는 서로 같은 튜플이 존재할 수 없음
 * 튜플의 무순서, 속성의 무순서: 한 릴레이션에서 튜플 및 속성들의 순서는 무의미함
 * 속성의 원자성: 속성 값으로 더 이상 분해 불가능한 원자 값만 사용 가능

## 관계 데이터 모델의 용어
 * 속성 (attribute): 릴레이션의 열
 * 튜플 (tuple): 릴레이션의 행
 * 도메인 (domain): 1개의 속성이 가질 수 있는 모든 값의 집합
   * 관계 데이터 모델에서는 더 이상 분해 불가능한 원자 값만 사용 가능
 * 차수 (degree): 속성의 개수
 * 카디널리티 (cardinality): 튜플의 개수
   * 튜플이 추가/삭제될 수 있으므로 차수와 달리 dynamic함

## 릴레이션 및 DB의 스키마와 인스턴스
 * 릴레이션 스키마 (relation schema): 릴레이션의 이름과 그 릴레이션의 모든 속성의 이름으로 정의하는, 릴레이션의 논리적 구조
   * relationName(attributeName_1, ..., attributeName_n)
 * 릴레이션 인스턴스 (relation instance): 특정 시점에 릴레이션에 존재하는 튜플의 집합
 * 데이터베이스 스키마 (DataBase schema): DB를 구성하는 릴레이션들의 스키마의 집합
   * 릴레이션 스키마의 집합임
 * 데이터베이스 인스턴스 (DataBase instance): 특정 시점에서 DB에 저장된 데이터 내용의 전체 집합
   * 릴레이션 인스턴스의 집합임

## key의 종류
 * 슈퍼키(super key): 유일성을 만족시키는 속성 또는 그 집합
 * 후보키(candidate key): 유일성과 최소성을 동시에 만족시키는 속성 또는 그 집합
 * 기본키(primary key): 후보키 중 기본적으로 사용할 키로 선택된 키
 * 대체키(alternate key): 기본키가 아닌 후보키
 * 외래키(foreign key): 어떤 릴레이션의, 다른 릴레이션의 기본키가 되는 속성 또는 그 집합

## 관계 데이터 모델의 제약
 * 개체 무결성 제약조건(entity integrity constraint): 기본키를 구성하는 모든 속성은 null 값을 가질 수 없음
   * 기본키 구성 속성 중 일부가 null 값이면 유일성 판단이 불가능하기 때문
 * 참조 무결성 제약조건(referential integrity constraint): 외래키는 참조할 수 있는 값만을 가져야 함
   * 외래키가 자신이 참조하는 다른 릴레이션의 기본키에 없는 값을 가지면 두 릴레이션을 연관시킬 수 없기 때문
