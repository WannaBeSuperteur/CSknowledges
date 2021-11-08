reference: https://terms.naver.com/list.naver?cid=58430&categoryId=58430&so=st4.asc (visited on Nov 08 2021)

## 관계 대수
관계 대수 (relational algebra): 릴레이션의 처리 과정을 기술하는 언어, 즉 연산자들의 집합
 * 피연산자는 릴레이션, 즉 관계 대수는 릴레이션을 연산함
 * 연산의 결과도 릴레이션 (즉 closure)

## 관계 대수의 연산자
 * 합집합 (R ∪ S): 릴레이션 R, S의 합집합을 반환
 * 교집합 (R ∩ S): 릴레이션 R, S의 교집합을 반환
 * 차집합 (R - S): 릴레이션 R, S의 차집합을 반환
 * 카티션 곱 (R x S): 릴레이션 R의 각 튜플과 S의 각 튜플을 모두 서로 연결한 새로운 튜플의 집합을 반환
   * 교환법칙 성립: R x S = S x R
   * 결합법칙 성립: (R x S) x T = R x (S x T)
   * 결과 릴레이션의 차수: (R의 차수) + (S의 차수)
   * 결과 릴레이션의 카디널리티: (R의 카디널리티) * (S의 카디널리티)
 * select (σ<sub>condition</sub>(R)): 릴레이션 R에서 조건을 만족하는 튜플의 집합을 반환
 * project (π<sub>(attribute1,attribute2,...)</sub>(R)): 릴레이션 R에서 선택한 속성만을 반환
 * join (R ▷◁ S): 두 릴레이션이 공통으로 갖는 속성인 조인 속성(join attribute)를 이용하여 두 릴레이션을 조합한 결과를 반환
 * division (R ÷ S): 릴레이션 S의 모든 튜플에 대해 각각 대응되는 튜플이 있는 R의 튜플(단, S의 해당 속성 제외)의 집합을 반환
   * 릴레이션 S의 모든 속성에 대해, 릴레이션 R에 해당 속성과 같은 도메인을 갖는 속성이 있어야 함
