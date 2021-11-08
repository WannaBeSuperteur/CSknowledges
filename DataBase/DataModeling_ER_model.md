reference: https://terms.naver.com/list.naver?cid=58430&categoryId=58430&so=st4.asc (visited on Nov 08 2021)

## 개체-관계 모델이란?
 * 개체-관계 모델: 현실 세계를 개체(entity)와 그 개체들 간의 관계(relationship)를 이용하여 개념적 구조로 표현하는 방법
 * 개체-관계 다이어그램(Entity-Relationship Diagram, or E-R Diagram): 현실 세계를 개체-관계 모델을 통해 모델링한 것을 그림으로 나타낸 것

## 개체 (entity)
개체 (entity): 현실 세계에서 구별되는 모든 것
 * 개체 이름(entity name): 다른 개체들과 구별되는 이름
 * 속성(attribute): 각 개체가 가지고 있는 고유한 속성 (예: 이름, 성별, 나이)
   * 파일 구조에서의 필드(field)에 해당
 * 개체 타입(entity type): 개체를 고유의 이름과 속성들로 정의한 것
   * 파일 구조에서 record type에 해당
 * 개체 인스턴스(entity instance): 개체의 속성이 값을 가짐으로써 실체화된 것 (예: <홍길동, 남, 30>)
   * 파일 구조에서 record instance에 해당

## 속성 (attribute)
속성 (attribute): 각 개체가 가지고 있는 고유한 속성
 * 자체만으로는 의미가 없고, 관련된 속성을 모아서 개체를 구성할 때 의미 표현 가능
 * 속성의 분류:
   * 속성값의 개수: 단일 값 / 다중 값 속성
   * 의미 분해 가능성: 단순 / 복합 속성
   * 유도 속성(derived attribute): 다른 속성의 값에서 유도되어 결정되는 속성 (예: 서류 점수, 코딩테스트 점수, 면접 점수 -> 합격 여부)
   * 널 속성(null attribute): Null 값이 허용되는 속성
   * 키 속성(key attribute): 각각의 개체 인스턴스들을 식별하기 위해 사용되므로, 모든 개체 인스턴스끼리 그 값이 서로 달라야 함
     * 단일 속성만으로는 안 되고 여러 개의 속성을 조합했을 때 key attribute가 되는 경우도 있음

## 관계 (relationship)
관계 (relationship): 개체끼리 맺고 있는 의미 있는 연관성, 즉 correspondence, mapping에 해당
 * 유형: 1:1, 1:N, M:N
 * 관계의 참여 특성: 개체 A와 B 사이의 어떤 관계에 대해,
   * 전체 참여: 개체 A의 모든 인스턴스가 반드시 참여해야 함
   * 부분 참여: 개체 A의 인스턴스 중 일부만 참여해도 됨

## E-R 다이어그램
개체-관계 모델을 이용해 개체, 속성, 그 개체들 간의 관계를 그림으로 표현한 것이다.
 * 개체는 직사각형, 속성은 타원, 관계는 마름모꼴로 나타낸다.
 * 키 속성(key attribute)에는 밑줄을 표시한다.
 * 예시: https://dbscthumb-phinf.pstatic.net/4515_000_1/20160715112605320_WHTTUW7B9.jpg/ka26_63_i1.jpg?type=w690_fst&wm=N
