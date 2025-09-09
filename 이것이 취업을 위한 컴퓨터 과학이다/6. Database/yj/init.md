## Part 1. 데이터베이스의 큰 그림

### 1. 데이터베이스와 DBMS

* **데이터베이스(Database)**
  → 여러 사람이 사용할 목적으로 **중복을 최소화하고 체계적으로 관리**되는 데이터 집합.
* **DBMS(Database Management System)**
  → 데이터베이스를 관리하는 소프트웨어. 예: MySQL, Oracle, PostgreSQL

### 2. 파일 시스템 vs 데이터베이스

* **파일 시스템 단점**

  * 데이터 중복, 일관성 깨짐
  * 동시성 제어 어려움 (여러 사용자가 동시에 접근 시 충돌)
  * 검색 비효율 (복잡한 조건 검색 불가)
  * 백업/복구 어려움

* **데이터베이스 장점**

  * 데이터 무결성 보장 (제약조건 활용)
  * 동시성 제어, 트랜잭션 관리
  * SQL 기반 복잡한 검색 가능
  * 복구·백업 체계 제공

### 3. 트랜잭션

* **정의**: 데이터베이스의 상태를 변화시키는 **논리적 작업 단위**
* **특징 (ACID)**

  * **Atomicity**: 전부 수행되거나 전혀 수행되지 않아야 함
  * **Consistency**: 제약조건을 항상 만족
  * **Isolation**: 동시에 실행되는 트랜잭션은 서로 독립
  * **Durability**: Commit 후 결과는 영구 반영

---

## Part 2. RDBMS의 기본

### 1. 관계형 데이터베이스

* **구성**: 테이블(Table), 행(Row), 열(Column)
* 각 테이블은 \*\*개체(Entity)\*\*를 표현, 열은 속성(Attribute), 행은 인스턴스(Instance)

### 2. 무결성 제약 조건

* **Primary Key (기본 키)**

  * 행을 유일하게 식별
  * NULL 불가, 중복 불가
* **Foreign Key (외래 키)**

  * 다른 테이블의 기본 키 참조
  * 테이블 간 관계 표현
  * 참조 무결성 보장
* **Unique**: 중복 불가, NULL 허용 가능
* **Not Null**: 반드시 값이 있어야 함
* **Check**: 값의 범위 제약 (예: 나이 BETWEEN 0 AND 120)

### 3. 테이블 간 관계

* **1:1 관계**: 주민번호 ↔ 개인 정보
* **1\:N 관계**: 고객 ↔ 주문
* **N\:M 관계**: 학생 ↔ 수업 (중간 테이블 필요)

---

## Part 3. SQL (Structured Query Language)

### 1. SQL의 분류

* **DDL (Data Definition Language)**
  → 데이터 구조 정의

  * CREATE, ALTER, DROP, TRUNCATE
  * 실행 즉시 Commit 발생

* **DML (Data Manipulation Language)**
  → 데이터 조작

  * SELECT, INSERT, UPDATE, DELETE
  * 트랜잭션 단위로 Commit/Rollback 가능

* **TCL (Transaction Control Language)**
  → 트랜잭션 제어

  * COMMIT, ROLLBACK, SAVEPOINT

### 2. DDL 예시

```sql
CREATE TABLE 학생 (
  학번 INT PRIMARY KEY,
  이름 VARCHAR(50) NOT NULL,
  나이 INT CHECK (나이 BETWEEN 0 AND 120)
);

ALTER TABLE 학생 ADD COLUMN 학과 VARCHAR(50);
CREATE INDEX idx_이름 ON 학생(이름);
```

### 3. DML 예시

```sql
INSERT INTO 학생 VALUES (2023001, '홍길동', 23);
UPDATE 학생 SET 학과='컴퓨터공학' WHERE 학번=2023001;
DELETE FROM 학생 WHERE 학번=2023001;
```

### 4. TCL 예시

```sql
BEGIN;
INSERT INTO 계좌 VALUES ('A', 1000);
INSERT INTO 계좌 VALUES ('B', 500);
COMMIT;

-- 오류 발생 시
ROLLBACK;
```