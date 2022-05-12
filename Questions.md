- 자바 메모리 영역의 구조는?
  - 메서드영역  : static/전역 변수, 클래스 정보
  - 스택       : 지역 변수, 메서드
  - 힙         : 동적으로 할당된 객체가 저장되고, 가비지 컬렉션에 의해 관리됨

- 추상 클래스와 인터페이스의 차이는?
  - 추상 클래스  : 클래스 내 추상 메서드가 하나 이상 포함되거나 abstract로 정의된 클래스
  - 인터페이스   : 모든 메서드가 추상 메서드인 경우

- DML, DDL, DCL, TCL은?
  - DML(Data Manipulation Language)   : SELECT, INSERT, UPDATE, DELETE / 조회, 데이터 변형
  - DDL(Data Definition Language)     : CREATE, ALTER, DROP, RENAME, TRUNCATE / 데이터 구조 정의
  - DCL(Data Control Language)        : GRANT, REVOKE / 권한
  - TCL(Transaction Control Language) : COMMIT, ROLLBACK, SAVEPOINT / DML에 의해 조작된 결과를 트랜잭션별로 제어

- ORM, JPA, Hibernate의 차이는?
  - ORM         : Object와 DB테이블을 매핑하여 데이터를 객체화하는 기술
  - JPA         : RDBMS를 사용해야 하는 방법이 정의된 인터페이스
  - Hibernate   : JPA를 구현한 구현체

- 자바의 리플렉션이란?
  - 구체적인 클래스 타입을 알지 못해도 클래스의 메서드, 타입, 변수들에 접근할 수 있도록 해주는 자바 API
  - 런타임 시점에 특정 클래스를 실행해야 하는 경우에 사용

- String, StringBuffer, StringBuilder의 차이는?
  - String        : 불변 | read 시 빠른 성능 | thread-safe
  - StringBuffer  : 가변 | 단일쓰레드에서 write시 빠른 성능 | thread-safe
  - StringBuilder : 가변 | 다중쓰레드에서 write시에 사용 | not thread-safe

- AOP란?
  - OOP만을 따라서는 제거할 수 없는 중복 코드를 해결하기 위함
  - 여러 클래스에 걸쳐 중복된 코드(관심사)를 비즈니스 로직에서 분리하여 재사용

- Spring MVC 동작 구조
  1. 사용자의 요청을 **DispatcherServlet**이 수신하여 HandlerMapping에 위임
  2. **HandlerMapping**이 적합한 Controller를 탐색
  3. **Controller**에서 Service, DAO, Repository 등을 통해 요청을 처리하여 반환
  4. **ViewResolver**에서 view를 반환
