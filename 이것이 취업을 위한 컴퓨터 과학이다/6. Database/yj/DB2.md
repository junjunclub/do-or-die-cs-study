## Part 4. 효율적 쿼리

* **JOIN**

  * **INNER JOIN** : 두 테이블에서 조건에 맞는 교집합만 반환
  * **OUTER JOIN** : 조건에 맞지 않아도 한쪽 테이블의 데이터를 모두 반환 (LEFT, RIGHT, FULL)
  * **SELF JOIN** : 같은 테이블을 조인
  * **CROSS JOIN** : 가능한 모든 조합을 반환 (Cartesian product)

* **서브쿼리 (Subquery)**

  * 쿼리 안에 포함된 또 다른 SELECT
  * 단일 행 반환(=, >, <), 다중 행 반환(IN, ANY, ALL), 다중 컬럼 반환(EXISTS)

* **뷰(View)**

  * 실제 데이터를 저장하지 않고, SELECT 결과를 논리적으로 보여주는 가상 테이블
  * 장점: 복잡한 쿼리 단순화, 보안 강화(민감 데이터 숨김)
  * 단점: 성능 저하 가능 (특히 중첩 뷰)

* **인덱스(Index)**

  * 검색 성능 최적화 도구 (책의 목차 vs 전체 페이지 뒤지는 것)
  * **B-Tree 인덱스**: 대부분의 DBMS 기본
  * **Hash 인덱스**: 동등 비교 검색에 유리
  * 장점: 조회 속도 향상
  * 단점: 쓰기(INSERT/UPDATE/DELETE) 성능 저하, 공간 차지

---

## Part 5. 데이터베이스 설계

* **ER 다이어그램(Entity Relationship Diagram)**

  * **엔티티(Entity)**: 데이터베이스에서 관리해야 할 객체 (학생, 과목, 주문 등)
  * **속성(Attribute)**: 엔티티의 특징 (이름, 학번, 가격 등)
  * **관계(Relationship)**: 엔티티 간 연결 (학생 ↔ 수강 ↔ 과목)

* **정규화 (Normalization)**

  * 데이터 중복과 이상(Anomaly: 삽입, 갱신, 삭제 이상) 제거
  * 제1정규형(1NF): 모든 속성은 원자값만 가진다 (반복 그룹 제거)
  * 제2정규형(2NF): 부분 함수 종속 제거 (기본키 전체에 종속되도록)
  * 제3정규형(3NF): 이행적 함수 종속 제거 (비키 속성이 다른 비키 속성에 종속되면 제거)
  * BCNF: 모든 결정자가 후보키가 되도록 보장

* **반정규화(Denormalization)**

  * 성능 최적화를 위해 의도적으로 정규화를 깨뜨림 (예: 조인을 줄이기 위해 데이터 중복 허용)

---

## Part 6. NoSQL
  * 대규모 트래픽, 빅데이터 환경에서 RDBMS의 수직 확장 한계 → 수평 확장 가능한 DB 필요
  * 스키마가 고정된 RDBMS 대신 **유연한 스키마** 필요

* **특징**

  * Schema-less (스키마 유연성)
  * 수평 확장 (Scale-out) 용이
  * CAP 이론: Consistency(일관성), Availability(가용성), Partition tolerance(분할 내성) → 세 가지를 모두 만족할 수 없음

* **종류**

  * **Key-Value Store**: Redis, DynamoDB → 캐시, 세션 관리에 적합
  * **Document Store**: MongoDB, CouchDB → JSON 기반, 복잡한 구조 저장 가능
  * **Column Store**: Cassandra, HBase → 대규모 데이터 분석, 분산 처리 적합
  * **Graph Store**: Neo4j → 노드-엣지 구조, SNS/추천 시스템에 강점

* **RDBMS vs NoSQL**

  | 항목   | RDBMS           | NoSQL            |
  | ---- | --------------- | ---------------- |
  | 구조   | 고정된 스키마         | 유연한 스키마          |
  | 확장성  | 수직 확장(Scale-up) | 수평 확장(Scale-out) |
  | 트랜잭션 | ACID 보장         | BASE 지향(일관성 완화)  |
  | 활용   | 전통적 비즈니스 데이터    | 빅데이터, 실시간 분석, 캐시 |

### 예상 질문

1. 인덱스를 사용하면 어떤 경우에 성능이 떨어질 수 있는가?
2. 뷰를 쓰는 이유와 단점은?
3. 정규화의 목적은?
4. 정규화가 지나치면 발생할 수 있는 문제는?
5. CAP 이론이란 무엇인가?
6. NoSQL이 RDBMS보다 유리한 상황은 언제인가?
